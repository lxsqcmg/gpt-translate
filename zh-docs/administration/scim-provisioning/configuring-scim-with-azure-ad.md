---
title: "使用 Azure AD 配置 SCIM"
order: 142
updated: 2022-11-30
page_id: "configuring_scim_with_azure_ad"
warning: false
contextual_links:
  - type: section
    name: "前提条件"
  - type: link
    name: "使用 Azure AD 配置 SSO"
    url: "/docs/administration/sso/azure-ad/"
  - type: section
    name: "其他资源"
  - type: subtitle
    name: "博客文章"
  - type: link
    name: "通过 Azure AD SCIM 在 Postman 中引入用户管理"
    url: "https://blog.postman.com/introducing-user-management-postman-azure-ad-scim/"
---

Postman 支持通过 Microsoft Azure AD 进行 SCIM 配置，使您能够自动化团队的用户配置和取消配置。

您必须是 [Postman 团队管理员](/docs/collaborating-in-postman/roles-and-permissions/#team-roles) 才能为您的团队启用 SCIM。启用 SCIM 后，用户将无法自行离开您的团队，并且无法更改其帐户电子邮件或密码。只有团队管理员拥有删除团队成员所需的权限。

## 目录

* [在 Azure AD 中启用 SCIM](#enabling-scim-in-azure-ad)
* [配置 Azure AD SCIM 集成](#configuring-the-azure-ad-scim-integration)
    * [映射用户属性](#mapping-user-attributes)
    * [映射组属性（可选）](#mapping-group-attributes-optional)
    * [完成配置](#completing-the-configuration)

## 在 Azure AD 中启用 SCIM

可以使用 Azure AD 应用程序库中的“非库应用程序”功能将 Postman 连接到 Azure Active Directory。连接后，Azure AD 每 40 分钟查询分配的用户的 Postman SCIM 端点，并根据您设置的分配详细信息创建或修改它们。

要设置与 Azure AD 的配置，请执行以下操作：

1. 在 Postman 中，[启用 SCIM](/docs/administration/scim-provisioning/scim-provisioning-overview/#enabling-scim-in-postman) 并 [生成 SCIM API 密钥](/docs/administration/scim-provisioning/scim-provisioning-overview/#generating-scim-api-key)。
1. 登录到 [Azure Active Directory 门户](https://aad.portal.azure.com/)。
1. 在 Azure AD 中，从左侧窗格中选择 **企业应用程序**。
1. 选择 **+ 新建应用程序**。
1. 选择 **+ 创建自己的应用程序**。
1. 输入名称，然后选择 **集成任何其他未在库中找到的应用程序**。
1. 选择 **添加** 以创建应用程序对象。这将将新的 Postman 应用程序添加到企业应用程序列表中，并打开应用程序管理屏幕。
1. 在应用程序管理屏幕中，选择左侧窗格中的 **配置**。
1. 在 **配置模式** 菜单中，选择 **自动**。
1. 在 **租户 URL** 字段中，输入 Postman SCIM 端点：`https://api.getpostman.com/scim/v2/`
1. 在 **密钥令牌** 字段中，输入您的 [SCIM API 密钥](/docs/administration/scim-provisioning/scim-provisioning-overview/#generating-scim-api-key)。
1. 选择 **测试连接**，让 Azure AD 尝试连接到 Postman SCIM 端点。如果尝试失败，将显示错误消息。如果尝试成功，则响应为 `HTTP 200 OK`，并带有空的 SCIM `ListResponse` 消息。
1. 选择 **保存** 以保存管理员凭据。

接下来，您将配置 Azure AD 集成。

## 配置 Azure AD SCIM 集成

在设置了 Azure AD 中的 SCIM 后，您可以为用户（必需）和组（可选）配置与 Postman 的集成。

您选择的 **属性映射** 属性用于匹配 Postman 中的用户或组以进行更新操作。

### 映射用户属性

要将 Postman 用户属性映射到 Azure AD 用户属性，请执行以下操作：

1. 在 Azure AD 的 **映射** 部分中，选择 **是** 以打开 **配置 Azure Active Directory 用户**。这是用户对象的属性映射集。
1. 在 **目标对象操作** 下，选择 **创建**、**更新** 和 **删除**。
1. 在 **属性映射** 下，选择 **添加新映射**，以映射以下属性：

    Azure AD 属性 | 目标属性 | Postman 属性 | 映射类型 | 使用此属性匹配对象 | 应用此映射
    --- | --- | --- | --- | --- | ---
    `userPrincipalName` &#x2a; | `userName` | `email` | 直接 | 是 | 始终
    `surname` | `name.familyName` | `name`  | 直接| 否 | 始终
    `givenName` | `name.givenName` | `name` | 直接 | 否 | 始终
    `Switch([IsSoftDeleted], , "False", "True", "True", "False")` | `active` | `active` | 表达式 | 否 | 始终

    &#x2a; 对于 `userPrincipalName`，将 **匹配优先级** 的值设置为 `1`。

    > 您必须删除不在此列表中的任何现有属性映射，以避免任何冲突或不匹配。选择要删除的任何映射旁边的 **删除**，以将其删除。

1. 选择 **保存** 以提交任何更改。

### 映射组属性（可选）

要将 Postman 组属性映射到 Azure AD 组属性，请执行以下操作：

1. 在 Azure AD 的 **映射** 部分中，选择 **是** 以打开 **配置 Azure Active Directory 组**。这是组对象的属性映射集。
1. 在 **目标对象操作** 下，启用 **创建**、**更新** 和 **删除**。
1. 在 **属性映射** 下，选择 **添加新映射**，以映射以下属性：

    Azure AD 属性 | 目标属性 | Postman 属性 | 映射类型 | 使用此属性匹配对象 | 应用此映射
    --- | --- | --- | --- | --- | ---
    `displayName` &#x2a; |	`displayName` | `Group name` | 直接 | 是 | 始终
    `members` | `members` |	`Group members` | 直接 | 否 | 始终

    &#x2a; 对于 `displayName`，将 **匹配优先级** 的值设置为 `1`。

    > 您必须删除不在此列表中的任何现有属性映射，以避免任何冲突或不匹配。选择要删除的任何映射旁边的 **删除**，以将其删除。

1. 选择 **保存** 以提交任何更改。

### 完成配置

1. 在 **设置** 下，**范围** 字段定义要同步的用户。选择 **仅同步分配的用户和组**，以仅同步在 **用户和组** 选项卡中分配的用户。
1. 完成配置后，将 **配置状态** 设置为 **开启**。
1. 选择 **保存**。

一旦第一个周期开始，您可以在 Azure AD 左侧窗格中选择 **配置日志**，以监视配置服务在 Postman 中执行的操作。