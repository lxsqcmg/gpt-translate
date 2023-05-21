---
title: "OneLogin"
order: 139
updated: 2022-03-16
page_id: "onelogin"
warning: false
contextual_links:
  - type: section
    name: "前提条件"
  - type: link
    name: "为团队配置SSO"
    url: "/docs/administration/sso/admin-sso/"
---

> **[使用OneLogin进行SSO仅适用于Postman企业版计划。](https://www.postman.com/pricing)**

要配置与OneLogin的SSO，您可以使用可用的Postman应用程序。您必须在OneLogin和Postman中都是管理员，才能为您的团队配置SSO。

## 目录

* [配置与OneLogin的SSO](#配置与onelogin的sso)

* [下一步](#下一步)

## 配置与OneLogin的SSO

在OneLogin中配置Postman应用程序之前，您必须[在Postman中配置SSO](/docs/administration/sso/admin-sso/)。在选择**身份验证类型**时，选择**OneLogin**。命名您的身份验证并**继续**。

<img alt="在Postman中配置身份提供者详细信息" src="https://assets.postman.com/postman-docs/configure-identity-provider-details-v9.14.jpg"/>

要继续配置您的Postman应用程序，请执行以下操作：

1. 在新标签页中打开您的OneLogin管理控制台。
1. 转到**应用程序**并选择**添加应用程序**。
1. 搜索“Postman”，并从结果中选择Postman应用程序。
1. 在左侧选择**配置**。
1. 从Postman中获取**ACS URL**，并将其添加为OneLogin中的**SAML使用者URL**。

    <img alt="OneLogin配置应用程序详细信息" src="https://assets.postman.com/postman-docs/onelogin-configuration3.jpg"/>

1. 在Postman中，选择**生成中继状态**，并将生成的值添加为OneLogin中的SAML RelayState。

    <img alt="在Postman中生成中继状态" src="https://assets.postman.com/postman-docs/generate-relay-state-v9.14.jpg" width="350px"/>

1. 在OneLogin中左侧选择**SSO**。
1. 复制**发行者URL**，并将其添加为Postman中的**身份提供者发行者**。

    <img alt="OneLogin SSO启用SAML 2.0" src="https://assets.postman.com/postman-docs/onelogin-sso.jpg"/>

1. 复制**SAML 2.0端点（HTTP）**，并将其添加为Postman中的**身份提供者SSO URL**。
1. 在**X.509证书**下选择**查看详细信息**。复制**X.509证书**，并将其添加到Postman的**X.509证书**下。

1. 在Postman中选择**保存身份验证**以完成配置。

> 如果遇到任何问题，请确认您已在Postman和OneLogin上添加并保存了正确的配置值。[联系Postman支持](https://www.postman.com/support/)以获取进一步帮助。

## 下一步

现在您已经设置了与OneLogin的SSO，您可以了解有关设置SCIM配置的信息：

* 要了解更多信息，请访问[使用OneLogin配置SCIM](/docs/administration/scim-provisioning/configuring-scim-with-onelogin/)。(_[企业团队](https://www.postman.com/pricing/)专用。_)