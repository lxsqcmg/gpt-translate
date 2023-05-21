---
title: '自定义SAML'
updated: 2023-03-21
contextual_links:
  - type: section
    name: "先决条件"
  - type: link
    name: "为团队配置SSO"
    url: "/docs/administration/sso/admin-sso/"
---

> **[使用自定义SAML的SSO仅适用于Postman企业版计划。](https://www.postman.com/pricing)**

要配置自定义SAML的SSO，请在您的身份提供者（IdP）中创建一个自定义SAML应用程序。您的IdP必须支持SAML 2.0标准。此外，您必须是IdP和Postman中的管理员，才能为您的团队配置SSO。

如果Postman不明确支持IdP，则可以配置自定义SAML的SSO。如果Postman明确支持IdP，则建议选择IdP作为身份验证类型，并按照文档说明进行操作。有关Postman支持哪些IdP的更多信息，请参见[支持的IdP](/docs/administration/sso/intro-sso/#supported-idps)。

## 配置自定义SAML的SSO

在配置自定义SAML的SSO之前，您必须[在Postman中配置SSO](/docs/administration/sso/admin-sso/)。在选择**身份验证类型**时，选择**SAML 2.0**。命名您的身份验证并**继续**。

<img alt="在Postman中配置身份提供者详细信息" src="https://assets.postman.com/postman-docs/v10/configure-identity-provider-v10.jpg"/>

要继续配置自定义SAML的SSO，请按照您的IdP的步骤创建自定义SAML应用程序。