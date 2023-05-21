---
title: "为团队配置单点登录（SSO）"
updated: 2023-02-06
contextual_links:
  - type: section
    name: "前提条件"
  - type: link
    name: "SSO 简介"
    url: "/docs/administration/sso/intro-sso/"
  - type: section
    name: "其他资源"
  - type: subtitle
    name: "视频"
  - type: link
    name: "管理员的 Postman 101 | 网络研讨会"
    url: "https://youtu.be/d6pw-0Yy5fs"
---

> **[SSO 适用于 Postman 专业版和企业版。](https://www.postman.com/pricing)**

您的[团队管理员](/docs/collaborating-in-postman/roles-and-permissions/#team-roles)可以为 Postman 团队配置单点登录（SSO）。要为团队配置 SSO，请添加身份验证方法，然后配置身份提供者（IdP）详细信息。

## 目录

* [配置单点登录](#configuring-single-sign-on)
* [编辑 SSO 设置](#editing-sso-settings)
* [管理用户帐户](#managing-user-accounts)
* [故障排除](#troubleshooting)
* [下一步操作](#next-steps)

## 配置单点登录

要开始添加身份验证方法，请执行以下操作：

1. 转到[团队设置](https://app.getpostman.com/dashboard/teams/edit)，然后选择**身份验证**。
1. 选择**添加身份验证方法**。
1. 选择身份验证类型。
1. 输入一个对您的团队可识别的身份验证名称。
1. 选择**继续**以[配置 IdP 详细信息](#configuring-the-idp-details)。

    <img src="https://assets.postman.com/postman-docs/v10/add-auth-method-v10.jpg" width="600px" alt="身份验证方法"/>

    > 始终与您的身份验证提供者仪表板或 IT 支持人员核对正确的信息以配置 SSO。

### 配置 IdP 详细信息

在[添加身份验证方法](#configuring-single-sign-on)之后，您可以配置 IdP 详细信息。

> 要稍后配置 IdP 详细信息，请选择**稍后配置**。当您准备好继续配置 IdP 详细信息时，请参阅[编辑 SSO 设置](#editing-sso-settings)。

在**服务提供者详细信息（Postman）**部分，**实体 ID**、**登录 URL** 和 **ACS URL** 已经填好。

填写**身份提供者详细信息**部分。从您的 IdP 帐户中，输入您的**SSO URL**、**身份提供者发行者**和**X.509 证书**。或者，您可以上传元数据文件以一步配置 IdP 详细信息。

<img alt="" src="https://assets.postman.com/postman-docs/v10/configure-identity-provider-details-v10.jpg"/>

要在**身份提供者详细信息**部分输入详细信息，您必须登录到您的 IdP 帐户并获取详细信息。请参阅文档的相应部分，并按照那里概述的过程操作：

* [Microsoft AD FS](/docs/administration/sso/microsoft-adfs/)*

* [Azure AD](/docs/administration/sso/azure-ad/)*

* [自定义 SAML](/docs/administration/sso/custom-saml/)*

* [Duo](/docs/administration/sso/duo/)*

* [Google Workspace](/docs/administration/sso/google-workspace/)

* [Okta](/docs/administration/sso/okta/)*

* [OneLogin](/docs/administration/sso/onelogin/)*

* [Ping Identity](/docs/administration/sso/ping-identity/)*

&#42; 仅适用于企业版。

如果您希望用户自动加入您的团队，可以选择[**自动添加新用户**](#automatically-adding-new-users)复选框。用户第一次使用此身份验证方法登录 Postman 时，他们将自动加入团队。

## 编辑 SSO 设置

为您的 Postman 团队配置[身份验证方法](#configuring-single-sign-on)后，您可以选择**状态**切换以打开或关闭它。这是一个团队级别的选项，因此此设置适用于整个团队。

<img alt="" src="https://assets.postman.com/postman-docs/admin-sso-turn-on-auth-method-v9.jpg" width="800px"/>

要更新身份验证方法的设置，请选择**编辑**，然后选择**继续**。

要删除身份验证方法，请选择**编辑**，然后选择**删除**。

<img alt="" src="https://assets.postman.com/postman-docs/v10/edit-auth-method-v10.jpg" width="600px"/>

## 管理用户帐户

本节介绍以下主题：

* [创建用户帐户](#creating-user-accounts)

* [添加现有用户帐户](#adding-existing-user-accounts)

* [自动添加新用户](#automatically-adding-new-users)

* [管理团队登录](#managing-team-sign-ins)

* [删除团队访问权限](#removing-team-access)

### 创建用户帐户

当新的 Postman 用户[使用身份验证方法登录 Postman](/docs/administration/sso/user-sso/)时，将创建一个 Postman 帐户，并自动将用户添加到团队，如果以下条件为真：团队有可用的席位，并且在[身份验证方法配置](#configuring-single-sign-on)期间选择了[**自动添加新用户**](#automatically-adding-new-users)复选框。

用户将自动关联到团队，拥有[开发人员角色](/docs/collaborating-in-postman/roles-and-permissions/#team-roles)，并且可以访问团队资源。

> 如果不满足自动加入团队的要求，则所有团队管理员都将收到您加入团队的请求。

### 添加现有用户帐户

当现有的 Postman 用户[使用身份验证方法登录 Postman](/docs/administration/sso/user-sso/)时，如果满足以下条件之一，则用户将自动添加到团队：

* 团队有可用席位，并且在[身份验证方法配置](#configuring-single-sign-on)期间选择了[**自动添加新用户**](#automatically-adding-new-users)复选框。
* 团队管理员已[邀请用户](/docs/administration/managing-your-team/managing-your-team/#inviting-users)加入团队。

用户将自动关联到团队，拥有[开发人员角色](/docs/collaborating-in-postman/roles-and-permissions/#team-roles)，并且可以访问团队资源。

> 如果不满足自动加入团队的要求，则所有团队管理员都将收到您加入团队的请求。

### 自动添加新用户

您在[身份验证方法](#configuring-single-sign-on)中的**自动添加新用户**复选框确定是否允许在您的 IdP 中具有帐户的用户自动加入您的团队。[使用身份验证方法登录 Postman](/docs/administration/sso/user-sso/)以自动加入团队。

> **自动添加新用户**仅在您的团队有可用的用户席位时才有效。如果更多用户使用 SSO 登录，则您的团队大小不会自动增加。

### 管理团队登录



默认情况下，Postman仅支持服务提供商（Postman）启动的登录方式，适用于Postman [专业版或企业版团队](https://www.postman.com/pricing/)。您的团队必须使用身份验证方法登录Postman。如果您要求用户使用SSO门户的IdP启动的登录方式进行登录，则可以从您的[身份验证方法](#configuring-single-sign-on)生成并复制**中继状态**，然后将其保存在您的IdP配置中。这可以确保在登录过程由Postman未知来源启动时，有一个额外的安全级别。

### 移除团队访问权限

您必须从Postman中删除用户，以防止访问共享资源。当您从团队中删除用户时，您仍将保留对他们与团队共享的任何数据的访问权限。在某些情况下，您还可以重新分配他们的个人工作区和其中的数据给剩余的团队成员。要了解更多信息，请参见[删除团队成员](/docs/administration/managing-your-team/managing-your-team/#removing-team-members)。

## 故障排除

了解常见的SSO问题以及如何解决它们。

如果您在使用SSO登录Postman后遇到错误，请参见以下错误和可能的解决方案：

* **您的IdP返回404错误。** 确保将**SSO URL**正确复制从您的IdP到您在Postman中的[身份验证方法](#configuring-single-sign-on)。
* **Postman返回500错误。** 确保将**X.509证书**正确复制从您的IdP到您在Postman中的[身份验证方法](#configuring-single-sign-on)。
* **Postman返回404错误。** 确保将[身份验证方法](#configuring-single-sign-on)中的**服务提供商详细信息（Postman）**部分的值正确复制到您的IdP中。
* **Postman返回一个解释登录请求已过期的页面。** 确保将**中继状态**正确复制从您在Postman中的[身份验证方法](#configuring-single-sign-on)到您的IdP中。

有关更常见的SSO问题，请参见以下内容：

* **电子邮件地址未与您的团队成员关联。** 在您的IdP配置设置中，确保用户名格式设置为**电子邮件**。

## 下一步

现在您已为团队设置了SSO，您可能会对了解团队如何与SSO交互并继续进行SCIM提供感兴趣。

* 要了解更多关于用户体验的信息，请参见[登录SSO团队](/docs/administration/sso/user-sso/)。
* 如果您的团队使用的是Postman企业版计划，请查看[SCIM提供](/docs/administration/scim-provisioning/scim-provisioning-overview/)。