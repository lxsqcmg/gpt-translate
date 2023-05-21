---
title: "Google Workspace"
updated: 2020-05-22
contextual_links:
  - type: section
    name: "先决条件"
  - type: link
    name: "SSO简介"
    url: "/docs/administration/sso/intro-sso/"
---

> **[Postman专业版和企业版支持使用Google Workspace进行SSO。](https://www.postman.com/pricing)**

*注意：您的GSuite组织的管理员必须创建SAML应用程序。*

### 在GSuite中设置自定义SAML应用程序

1. 从Google管理控制台中选择“应用程序”。
   [![gsuite admin](https://assets.postman.com/postman-docs/gsuite_admin.png)](https://assets.postman.com/postman-docs/gsuite_admin.png)

2. 查找“SAML应用程序”。
   [![gsuite saml apps](https://assets.postman.com/postman-docs/gsuite_saml_apps.png)](https://assets.postman.com/postman-docs/gsuite_saml_apps.png)

3. 创建新的SAML应用程序。
   [![gsuite create new](https://assets.postman.com/postman-docs/gsuite_create_new.png)](https://assets.postman.com/postman-docs/gsuite_create_new.png)

4. 选择“设置我的自定义应用程序”。
   [![gsuite setup](https://assets.postman.com/postman-docs/gsuite_setup.png)](https://assets.postman.com/postman-docs/gsuite_setup.png)

5. 从此窗口收集“身份提供者单点登录URL”、“身份提供者发行者”和“X.509证书”，并将这些值输入到您的Postman [编辑团队详细信息页面](https://go.postman.co/settings/team/general) 中的**GSuite身份提供者详细信息**模态框中。
   [![gsuite google IdP](https://assets.postman.com/postman-docs/gsuite_google_IdP.png)](https://assets.postman.com/postman-docs/gsuite_google_IdP.png)

6. 输入应用程序名称（例如“Postman SAML应用程序”）并填写任何其他可选字段。
   [![gsuite basic info](https://assets.postman.com/postman-docs/gsuite_basic_info.png)](https://assets.postman.com/postman-docs/gsuite_basic_info.png)

7. 输入Postman服务提供者详细信息，这些信息可以在Postman [编辑团队详细信息页面](https://go.postman.co/settings/team/general) 中的**GSuite身份提供者详细信息**模态框中找到。有关此最后一步的更多详细信息，请查看[在Postman中设置SSO](/docs/administration/sso/admin-sso/)。
   [![gsuite service provider](https://assets.postman.com/postman-docs/gsuite_service_provider.png)](https://assets.postman.com/postman-docs/gsuite_service_provider.png)

 | **字段** | **值** |
 | --- | --- |
 | 单点登录URL | ACS URL |
 | 受众URI（SP实体ID） | 实体ID |
 | 名称ID格式 | EmailAddress |