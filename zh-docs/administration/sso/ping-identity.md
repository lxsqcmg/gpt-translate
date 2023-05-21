---
title: "Ping Identity"
order: 140
updated: 2020-05-22
page_id: "ping_identity"
warning: false
contextual_links:
  - type: section
    name: "先决条件"
  - type: link
    name: "SSO简介"
    url: "/docs/administration/sso/intro-sso/"
---

> **[使用Ping Identity进行SSO仅适用于Postman企业版计划。](https://www.postman.com/pricing)**

*注意：只有您的Ping Identity组织的管理员才能创建应用程序。*

## 在Ping Identity中设置自定义SAML应用程序

1. 从Ping Identity管理控制台中选择**应用程序**选项卡。
   [![ping_app](https://assets.postman.com/postman-docs/ping_app)](https://assets.postman.com/postman-docs/ping_app)

2. 在**我的应用程序**选项卡下，找到**添加应用程序**下拉菜单并选择**新建SAML应用程序**。
   [![ping_new_SAML](https://assets.postman.com/postman-docs/ping_new_SAML)](https://assets.postman.com/postman-docs/ping_new_SAML)

3. 填写必填的应用程序详细信息并继续下一步。
   [![ping_details](https://assets.postman.com/postman-docs/ping_details)](https://assets.postman.com/postman-docs/ping_details)

4. 下载**SAML元数据**文件，并输入您的Postman服务提供商详细信息。这些详细信息可以在Postman的[编辑团队详细信息页面](https://go.postman.co/settings/team/general)上找到。

    | **字段** | **值** |
    |---|---|
    | 协议版本 | SAML v 2.0 |
    | Assertion Consumer Service | *从Postman团队详细信息页面收集* |
    | 实体ID | *从Postman团队详细信息页面收集* |

    将其余字段留空或使用默认值，并继续下一步。
    [![ping service provider](https://assets.postman.com/postman-docs/ping_service_provider)](https://assets.postman.com/postman-docs/ping_service_provider)

5. 将**电子邮件**添加为应用程序属性，并将其映射到**电子邮件**。选择**保存并发布**。
   [![ping email](https://assets.postman.com/postman-docs/ping_email)](https://assets.postman.com/postman-docs/ping_email)

6. 配置所有详细信息后，选择**启用**。
   [![ping toggle](https://assets.postman.com/postman-docs/ping_toggle)](https://assets.postman.com/postman-docs/ping_toggle)

7. 启用后，SAML应用程序的状态将显示为**活动**。
   [![ping active](https://assets.postman.com/postman-docs/ping_active)](https://assets.postman.com/postman-docs/ping_active)

8. 完成设置后，将您的身份提供者（IdP）详细信息提交给Postman。从下载的**SAML元数据**文件中复制`Identity Provider Single Sign-On URL`、`Identity Provider Issuer`和`X.509 Certificate`，并在Postman的[编辑团队详细信息页面](https://go.postman.co/settings/team/general)中输入这些值，以在**Ping Identity Provider Details**模态框中进行设置SSO的更多详细信息，请参阅[在Postman中设置SSO](/docs/administration/sso/admin-sso/)。