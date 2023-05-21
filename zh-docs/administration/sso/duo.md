---
title: "Duo"
order: 136
updated: 2020-05-22
page_id: "duo"
warning: false
contextual_links:
  - type: section
    name: "先决条件"
  - type: link
    name: "SSO简介"
    url: "/docs/administration/sso/intro-sso/"
---

> **[使用Duo的SSO仅适用于Postman企业版计划。](https://www.postman.com/pricing)**

*注意：您的Duo组织的管理员必须创建SAML应用程序。*

## 在Duo中设置自定义SAML应用程序

1. 从Duo仪表板转到应用程序页面。选择**保护应用程序**。

     [![duo dashboard](https://assets.postman.com/postman-docs/duo_dashboard.png)](https://assets.postman.com/postman-docs/duo_dashboard.png)

1. 搜索"SAML - 服务提供商"并选择**保护此应用程序**链接。
     [![duo protect](https://assets.postman.com/postman-docs/duo_protect.png)](https://assets.postman.com/postman-docs/duo_protect.png)

1. 将`Postman`输入为服务提供商。服务提供商详细信息可以在Postman的[编辑团队详细信息页面](https://go.postman.co/settings/team/general)上找到。其他字段可以留空或设置为默认值。
     [![duo provider](https://assets.postman.com/postman-docs/duo_provider.png)](https://assets.postman.com/postman-docs/duo_provider.png)

     | **字段** | **值** |
     |---|---|
     | 服务提供商名称 | Postman |
     | 实体ID | *从Postman团队详细信息页面收集* |
     | 断言使用者服务 | *从Postman团队详细信息页面收集* |
     | NameID格式 | EmailAddress |

1. 配置服务提供商详细信息后，选择**保存配置**。
     [![duo save](https://assets.postman.com/postman-docs/duo_save.png)](https://assets.postman.com/postman-docs/duo_save.png)

1. 下载配置文件。
     [![duo download](https://assets.postman.com/postman-docs/duo_download.png)](https://assets.postman.com/postman-docs/duo_download.png)

1. Duo要求将您的云应用程序添加到Duo Access Gateway中。请参阅此[设置指南](https://duo.com/docs/dag-generic)。

1. 完成设置后，将您的身份提供者（IdP）详细信息提交给Postman。从Duo配置页面收集`Identity Provider Single Sign-On URL`、`Identity Provider Issuer`和`X.509 Certificate`，并在Postman的**Duo Identity Provider Details**模态框中填写这些值。有关此最后一步的更多详细信息，请查看[在Postman中设置SSO](/docs/administration/sso/admin-sso/)。