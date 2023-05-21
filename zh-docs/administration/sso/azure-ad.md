---
title: "Azure AD"
order: 135
updated: 2022-03-14
page_id: "azure_ad"
warning: false
contextual_links:
  - type: section
    name: "前提条件"
  - type: link
    name: "为团队配置单点登录"
    url: "/docs/administration/sso/admin-sso/"
---

> **[使用Azure AD进行SSO仅适用于Postman企业版计划。](https://www.postman.com/pricing)**

要配置与Azure Active Directory（AD）的SSO，您可以使用Azure AD中提供的Postman应用程序或创建自定义SAML应用程序。您必须在Azure AD和Postman中都是管理员，才能为您的团队配置SSO。

## 目录

* [配置与Azure AD的SSO](#configuring-sso-with-azure-ad)

* [下一步](#next-steps)

## 配置与Azure AD的SSO

在Azure AD中配置SAML应用程序之前，您必须[在Postman中配置SSO](/docs/administration/sso/admin-sso/)。在选择**身份验证类型**时，选择**SAML 2.0**。命名您的身份验证并**继续**。

<img alt="在Postman中配置身份提供程序详细信息" src="https://assets.postman.com/postman-docs/configure-identity-provider-details-v9.14.jpg"/>

继续配置您的SAML应用程序，请执行以下操作：

1. 在新标签页中打开Azure AD管理门户。
1. 转到**企业应用程序**并选择**+新应用程序**。
1. 搜索“Postman”并从结果中选择Postman应用程序，然后选择**创建**。或者，您可以**+创建自己的应用程序**。
1. 选择**设置单一登录 > SAML**。
1. 从Postman中获取**实体ID**、**登录URL**和**ACS URL**，并将它们添加到Azure AD中的SAML配置中。

    <img alt="Azure AD中的基本SAML配置" src="https://assets.postman.com/postman-docs/basic-saml-config-azuread.jpg"/>
1. 在Postman中，选择**生成中继状态**，并将生成的值添加到Azure AD中的SAML配置中。

    <img alt="在Postman中生成中继状态" src="https://assets.postman.com/postman-docs/generate-relay-state-v9.14.jpg" width="350px"/>
1. 在Azure AD的**属性和声明**下，选择**编辑 > 添加新声明**。将`唯一用户标识符（名称ID）`映射到`user.mail`值。

    <img alt="Azure AD中的属性和声明" src="https://assets.postman.com/postman-docs/attributes-claims-config-azuread.jpg"/>
1. 在Azure AD中的**SAML签名证书**下**下载**联合元数据XML文件。

    <img alt="Azure AD中的SAML签名证书" src="https://assets.postman.com/postman-docs/saml-signing-certificate-azuread.jpg"/>

1. 在Postman中，在**身份提供程序元数据文件**下上传联合元数据XML文件。或者，您可以在**身份提供程序详细信息**下单独输入**身份提供程序SSO URL**、**身份提供程序发行者**和**X.509证书**。

1. 在Postman中选择**保存身份验证**。

您可以通过在Azure AD中创建测试用户并分配Postman应用程序来测试您的SAML配置。如果您选择在配置SAML时[自动添加新用户](/docs/administration/sso/admin-sso/#automatically-adding-new-users)，则可以立即使用测试用户的凭据登录Postman以确认该过程按预期工作。如果您没有选择自动添加新用户，则可以手动[邀请测试用户](/docs/administration/managing-your-team/managing-your-team/#inviting-users)加入您的Postman团队，然后使用测试用户的凭据登录Postman。

> 如果遇到任何问题，请确认您已在Postman和Azure AD上添加并保存了正确的配置值。[联系Postman支持](https://www.postman.com/support/)以获取进一步帮助。

## 下一步

现在您已经设置了与Azure AD的SSO，您可以了解有关设置SCIM提供程序的信息：

* 要了解更多信息，请访问[使用Azure AD配置SCIM](/docs/administration/scim-provisioning/configuring-scim-with-azure-ad/)。(_[企业团队](https://www.postman.com/pricing/)专用。_)