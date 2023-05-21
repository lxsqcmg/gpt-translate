---
title: "SCIM 配置概述"
order: 142
updated: 2022-03-02
page_id: "scim_provisioning_overview"
warning: false
contextual_links:
  - type: section
    name: "其他资源"
  - type: subtitle
    name: "博客文章"
  - type: link
    name: "使用 SCIM 在 Postman 中引入用户管理"
    url: "https://blog.postman.com/introducing-user-management-in-postman-with-scim/"
  - type: subtitle
    name: "案例研究"
  - type: link
    name: "Western Governors University (WGU) 使用 SCIM 创建团队"
    url: "https://www.postman.com/case-studies/wgu/"
---

> **[使用 SCIM 进行配置可在 Postman 企业版计划中使用。](https://www.postman.com/pricing)**

Postman 支持 [SCIM](https://datatracker.ietf.org/doc/html/rfc7642)（跨域身份管理系统），允许您自动化团队的用户配置和去配置。通过此功能，您可以高效地在整个组织中部署 Postman，并使用身份提供者（IdP）控制对其的访问。

您可以使用 [SCIM API](#使用 SCIM API 进行配置 SCIM)，[Okta](/docs/administration/scim-provisioning/configuring-scim-with-okta/) 或 [Azure AD](/docs/administration/scim-provisioning/configuring-scim-with-azure-ad/) 启用 SCIM 配置。您必须是 [Postman 团队管理员](/docs/collaborating-in-postman/roles-and-permissions/#team-roles) 才能为您的团队启用 SCIM 配置。启用 SCIM 后，用户将无法自行离开您的团队，并且无法更改其帐户电子邮件或密码。只有团队管理员才有权删除团队成员。

## 目录

* [SCIM 功能](#scim-features)

* [启用 SCIM 配置](#enabling-scim-provisioning)

    * [在 Postman 中启用 SCIM](#enabling-scim-in-postman)

    * [生成 SCIM API 密钥](#generating-scim-api-key)

* [使用 SCIM API 进行配置 SCIM](#configuring-scim-with-the-scim-api)

* [下一步](#next-steps)

## SCIM 功能

Postman 支持以下配置功能：

* **创建用户** - 在 Postman 中创建新用户帐户，将帐户添加到您的组织的 Postman 团队中，并激活用户的身份验证。如果存在相同电子邮件 ID 的帐户，则向用户发送 [电子邮件邀请](/docs/administration/managing-your-team/managing-your-team/#inviting-users) 加入您的 Postman 团队。一旦用户接受邀请，他们将被添加到您的团队中。

    > 新添加的用户默认在 Postman 中具有开发人员角色。您可以稍后 [在 Postman 中更新帐户角色](/docs/administration/managing-your-team/managing-your-team/#managing-team-roles)。

* **更新用户信息**

    * **更新用户属性** - 在 Postman 中更新用户的名字和姓氏。

    * **激活用户** - 在您的 Postman 团队中创建一个新用户（如果不存在），并激活该用户以进行身份验证。

    * **去激活用户** - 从您的 Postman 团队中删除用户并去激活其帐户，阻止该帐户进行 Postman 身份验证。

        > 用户帐户及其相应的数据不会被删除。要永久删除用户帐户及其数据，请[联系 Postman 支持](https://www.postman.com/support/)。

    * **重新激活用户** - 通过解除帐户的身份验证阻止帐户的身份验证，重新激活现有的已去激活用户，并将帐户添加回您的 Postman 团队中。

* **创建组** - 在 Postman 中创建新的 [用户组](/docs/administration/managing-your-team/user-groups/)。当您将 Postman 应用程序分配给组时，Postman 会为每个用户创建一个新帐户，将每个帐户添加到您的组织的 Postman 团队中，并激活每个用户的身份验证。如果现有的 Postman 帐户使用与用户的电子邮件 ID 匹配的电子邮件，则向该用户发送 [电子邮件邀请](/docs/administration/managing-your-team/managing-your-team/#inviting-users) 加入您的 Postman 团队。一旦用户接受邀请，他们将被添加到您的团队中。

    > 新创建的组默认在 Postman 中具有开发人员角色。您可以稍后 [在 Postman 中更新组角色](/docs/administration/managing-your-team/user-groups/#editing-team-roles-for-a-group) 和 [控制组对工作区和单个 Postman 实体（如集合和 API）的访问](/docs/administration/managing-your-team/user-groups/#managing-roles-on-workspaces-and-postman-entities)。

* **删除组** - 在 Postman 中删除用户组。已删除组的用户帐户在 Postman 中被去激活。

    > 用户帐户及其相应的数据不会被删除。要永久删除用户帐户及其数据，请[联系 Postman 支持](https://www.postman.com/support/)。

* **更新组信息**

    * **更新组属性** - 在 Postman 中更新组的名称。

    * **更新组成员** - 在 Postman 中添加或删除组中的用户。

        > 组中的用户具有分配给组的角色。您可以 [在 Postman 中更新组角色](/docs/administration/managing-your-team/user-groups/#editing-team-roles-for-a-group) 和 [控制组对工作区和单个 Postman 实体（如集合和 API）的访问](/docs/administration/managing-your-team/user-groups/#managing-roles-on-workspaces-and-postman-entities)。

Postman 不支持以下配置功能：

* 将组从 Postman 推送到您的 IdP
* 推送或同步密码更新
* 从您的 IdP 推送用户属性更新到 Postman，除了名称
* 从 Postman 拉取用户属性更新到您的 IdP

## 启用 SCIM 配置

在启用 Postman 团队的 SCIM 配置之前，您必须配置 SSO。

> 要使用 SCIM，您必须仅配置一种 SSO 方法。如果启用了多个 SSO 方法，则无法生成 SCIM API 密钥。

<!-- -->
> 了解 [如何在 Postman 中配置 SSO](/docs/administration/sso/admin-sso/)。

### 在 Postman 中启用 SCIM

1. 打开 [Postman](https://go.postman.co/home)。
1. 在右上角选择 **团队**，然后选择 **团队设置**。
1. 在侧边栏中选择 **身份验证**。
1. 选择 **SCIM 配置** 切换。

    <img alt="在仪表板中启用 SCIM" src="https://assets.postman.com/postman-docs/auth-enable-scim-v9.jpg"/>

1. 单击 **打开** 以启用 SCIM 配置。

    <img alt="在仪表板中启用 SCIM" src="https://assets.postman.com/postman-docs/turn-on-scim-provisioning-1.jpg" width="400px"/>

### 生成 SCIM API 密钥

1. 在 **SCIM 配置** 下，选择 **生成 SCIM API 密钥**。

    <img alt="生成 SCIM API 密钥" src="https://assets.postman.com/postman-docs/generate-scim-api-key-v9.jpg"/>

1. 命名您的密钥并单击 **生成**。
1. 复制您的新 API 密钥以供以后使用，然后单击 **完成**。

您可以重新访问此页面以管理您的SCIM API密钥。如果您重新生成现有的API密钥，则可以选择在切换期间保持第一个密钥处于活动状态。

要继续启用SCIM配置，请参见[使用SCIM API配置SCIM](#configuring-scim-with-the-scim-api)、[使用Okta配置SCIM](/docs/administration/scim-provisioning/configuring-scim-with-okta/)、[使用Azure AD配置SCIM](/docs/administration/scim-provisioning/configuring-scim-with-azure-ad/)或[使用OneLogin配置SCIM](/docs/administration/scim-provisioning/configuring-scim-with-onelogin/)。如需进一步了解或帮助配置SCIM，请[联系Postman支持](https://www.postman.com/support/)。

## 使用SCIM API配置SCIM

访问Postman的[SCIM API文档](https://www.postman.com/postman/workspace/scim/documentation/6248949-de4a96e2-9ebf-426f-bc55-4c5f2de51ab2)，了解如何使用SCIM 2.0 API为您的Postman团队设置SCIM。

## 下一步

现在您已经启用了SCIM并生成了SCIM API密钥，您可以继续启用SCIM配置。完成SCIM设置后，了解如何管理团队的角色和权限：

* 要了解如何通过您的IdP启用SCIM配置，请访问[使用Okta配置SCIM](/docs/administration/scim-provisioning/configuring-scim-with-okta/)、[使用Azure AD配置SCIM](/docs/administration/scim-provisioning/configuring-scim-with-azure-ad/)或[使用OneLogin配置SCIM](/docs/administration/scim-provisioning/configuring-scim-with-onelogin/)。
* 了解更多关于在您的团队中[定义角色](/docs/collaborating-in-postman/roles-and-permissions/)以及如何[创建用户组](/docs/administration/managing-your-team/user-groups/)的信息。