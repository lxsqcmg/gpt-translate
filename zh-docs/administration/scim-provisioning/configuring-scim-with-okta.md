---
title: "使用Okta配置SCIM"
updated: 2023-04-12
contextual_links:
  - type: section
    name: "先决条件"
  - type: link
    name: "使用Okta配置SSO"
    url: "/docs/administration/sso/okta/"
---

Postman支持通过[Postman Okta应用程序](https://www.okta.com/integrations/postman/)进行SCIM配置，使您能够自动化为您的团队进行用户配置和去配置。

您必须是[Postman团队管理员](/docs/collaborating-in-postman/roles-and-permissions/#team-roles)才能为您的团队启用SCIM。启用SCIM后，用户将无法自行离开您的团队，并且将无法更改其帐户电子邮件或密码。只有团队管理员才有权删除团队成员。

## 目录

* [在Okta中启用SCIM](#enabling-scim-in-okta)

* [配置Okta SCIM集成](#configuring-the-okta-scim-integration)

## 在Okta中启用SCIM

Postman作为Okta集成网络中的应用程序可用，允许您直接通过Okta启用用户配置。

在启用Okta中的SCIM之前，您必须[在Okta中添加Postman应用程序](https://www.okta.com/integrations/postman/)并[为您的Postman团队配置Okta的SSO](/docs/administration/sso/saml-okta/)。

要使用Okta设置配置，请执行以下操作：

1. [在Postman中启用SCIM](/docs/administration/scim-provisioning/scim-provisioning-overview/#enabling-scim-in-postman)并[生成SCIM API密钥](/docs/administration/scim-provisioning/scim-provisioning-overview/#generating-scim-api-key)。

2. 在Okta中，转到Postman应用程序，选择**配置**，然后选择**配置API集成**。

    <img alt="在Okta Postman应用程序中配置API集成" src="https://assets.postman.com/postman-docs/postman-okta-app-configure-api-integration.jpg"/>

3. 选择**启用API集成**，并将您的SCIM API密钥输入为**API令牌**。

    <img alt="在Okta的Postman应用程序中配置配置" src="https://assets.postman.com/postman-docs/postman-okta-app-enable-provisioning.jpg"/>

4. 选择**测试API凭据**。如果成功，将出现验证消息。

    > 如果验证失败，请确认您已在Postman中为您的团队启用了SCIM，正在使用正确的SCIM API密钥，并且您的API密钥的状态在您的[团队身份验证设置](https://go.postman.co/settings/team/auth)中为**ACTIVE**。如果您继续遇到问题，请[联系Postman支持](https://www.postman.com/support/)寻求帮助。

5. 选择**保存**。

## 配置Okta SCIM集成

Postman Okta应用程序支持[SCIM配置概述](/docs/administration/scim-provisioning/scim-provisioning-overview/#scim-features)中列出的配置功能。

要打开或关闭这些功能，请执行以下操作：

1. 转到Okta中的Postman应用程序，选择左侧的**到应用程序**，然后选择**编辑**。

    <img alt="在Okta的Postman应用程序中配置功能" src="https://assets.postman.com/postman-docs/postman-okta-app-enable-features.jpg"/>

1. 选择要启用的功能，或清除以关闭它们。

    <img alt="在Okta的Postman应用程序中启用的功能" src="https://assets.postman.com/postman-docs/postman-okta-app-enabled-features.jpg"/>

1. 选择**保存**以保存更改。

您已启用的任何配置功能都将立即可用于您的Postman Okta应用程序中。如果用户已从Postman应用程序进行了配置，则可能会在Okta中出现错误。如果发生这种情况，请从Postman管理团队设置中删除待处理的邀请，然后Okta将进行配置。