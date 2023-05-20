---
title: "使用 OneLogin 配置 SCIM"
order: 142
updated: 2022-03-17
page_id: "configuring_scim_with_onelogin"
warning: false
contextual_links:
  - type: section
    name: "前提条件"
  - type: link
    name: "使用 OneLogin 配置 SSO"
    url: "/docs/administration/sso/onelogin/"

---

通过 Postman OneLogin 应用程序，Postman 支持使用 SCIM 在 OneLogin 中进行配置，从而使您能够自动化团队的用户配置和取消配置。

您必须是 OneLogin 和 Postman 中的管理员才能为您的团队启用 SCIM。启用 SCIM 后，用户将无法自行离开您的团队，并且将无法更改其帐户电子邮件或密码。只有团队管理员才有权删除团队成员。

## 目录

* [在 OneLogin 中启用 SCIM](#enabling-scim-in-onelogin)

* [配置 OneLogin SCIM 集成](#configuring-the-onelogin-scim-integration)

## 在 OneLogin 中启用 SCIM

Postman 可以作为 OneLogin 中的应用程序使用，从而使您能够在 SSO 中启用用户配置。

在启用 SCIM 之前，您必须为您的 Postman 团队[配置 OneLogin SSO](/docs/administration/sso/onelogin/)。

要使用 OneLogin 设置配置，请执行以下操作：

1. [在 Postman 中启用 SCIM](/docs/administration/scim-provisioning/scim-provisioning-overview/#enabling-scim-in-postman) 并[生成 SCIM API 密钥](/docs/administration/scim-provisioning/scim-provisioning-overview/#generating-scim-api-key)。

2. 在 OneLogin 中，转到 Postman 应用程序并选择 **配置**。在 **API 连接** 下粘贴生成的 SCIM API 密钥，然后选择 **启用**。

    <img alt="OneLogin 配置 API 连接" src="https://assets.postman.com/postman-docs/onelogin-api-connection.jpg" width="275px"/>

3. 单击 **保存**。

## 配置 OneLogin SCIM 集成

Postman 支持 [SCIM 配置概述](/docs/administration/scim-provisioning/scim-provisioning-overview/#scim-features) 中详细说明的配置功能。

要配置配置，请转到 OneLogin 中的 Postman 应用程序，然后在左侧选择 **配置**，然后选择 **启用配置**。

<img alt="OneLogin 配置工作流程" src="https://assets.postman.com/postman-docs/onelogin-provisioning-workflow.jpg" width="400px"/>

选择要启用的功能，或取消选择以关闭它们。

您还可以定义当在 OneLogin 中删除用户、删除其 Postman 应用程序访问权限或暂停其帐户时会发生什么。您可以选择 **暂停** 这些用户的 Postman 帐户或 **不执行任何操作**。如果您选择 **暂停**，则受影响的帐户将不再出现在您的 [Postman 团队仪表板](https://go.postman.co/settings/team/members) 中。无论您的选择如何，已删除、已暂停或已删除其应用程序访问权限的用户将无法再登录其 Postman 帐户。

选择 **保存** 以保存更改。