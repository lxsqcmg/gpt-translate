---
title: "配置域名验证和捕获"
order: 143
page_id: "configuring_domain_capture"
warning: false
updated: 2023-03-07
contextual_links:
  - type: section
    name: "其他资源"
  - type: subtitle
    name: "博客文章"
  - type: link
    name: "介绍域名捕获：将您的组织的 Postman 用户分组为一个团队"
    url: "https://blog.postman.com/introducing-domain-capture/"

---

> **[域名验证和捕获仅适用于 Postman 企业版计划。](https://www.postman.com/pricing)**

验证域名以查看在 Postman 中使用您的组织域名和子域名创建的所有用户帐户。启用域名捕获以管理在 Postman 中的所有这些用户帐户。使用域名捕获，您可以将您组织的所有 Postman 用户合并为一个 Postman 团队，并确保使用您的域名注册 Postman 的任何新用户都会自动添加。

要启用域名捕获，[团队管理员](/docs/collaborating-in-postman/roles-and-permissions/#team-roles)必须首先[添加和验证域名或子域名](#adding-and-verifying-a-domain)。一旦域名已验证，他们可以创建一个请求来[启用域名捕获](#enabling-domain-capture)。一旦请求获得批准，他们可以[联系 Postman 支持](#contacting-support-to-manage-accounts)来管理[未声明的帐户](#viewing-unclaimed-accounts)。

## 目录

* [域名验证和捕获的先决条件](#prerequisites-for-domain-verification-and-capture)

* [添加和验证域名](#adding-and-verifying-a-domain)

    * [稍后验证域名](#verifying-a-domain-later)

    * [查看验证详细信息](#viewing-verification-details)

    * [查看未声明的帐户](#viewing-unclaimed-accounts)

* [启用域名捕获](#enabling-domain-capture)

    * [用户体验](#user-experience)

    * [联系支持以管理帐户](#contacting-support-to-manage-accounts)

* [删除域名](#deleting-a-domain)

* [域名捕获常见问题解答](#domain-capture-faqs)

## 域名验证和捕获的先决条件

您必须是[Postman 团队管理员](/docs/collaborating-in-postman/roles-and-permissions/#team-roles)，才能为您的团队添加和验证域名并启用域名捕获。

添加和验证域名并启用域名捕获需要以下条件：

* 您的团队必须使用[Postman 企业版](https://www.postman.com/pricing)计划。
* 您的团队必须使用[Postman 版本 9 或更高版本](/docs/administration/updating/)。

启用域名捕获需要以下条件：

* 必须配置和启用[SSO](/docs/administration/sso/admin-sso/)。
    * 必须关闭替代身份验证方法（Postman 或 Google 登录）。

建议您启用[SSO 配置](/docs/administration/scim-provisioning/scim-provisioning-overview/)以简化新用户的入职流程，并启用[Auto-Flex](/docs/administration/billing/#using-auto-flex)以确保您的团队可以自动适应可能添加到您的 Postman 团队中的所有用户，当启用域名捕获时。

## 添加和验证域名

[团队管理员](/docs/collaborating-in-postman/roles-and-permissions/#team-roles)可以通过导航到[域名仪表板](https://go.postman.co/settings/team/domain-capture)来为您的团队添加域名和子域名。一旦您将验证**TXT 记录**添加到您的 DNS 配置中，Postman 团队将验证您的域名或子域名。在您可以查看和管理在 Postman 中使用您的组织域名和子域名创建的所有用户帐户之前，必须验证您的域名。

1. 打开 Postman 并在 Postman 标头中选择 **Team > Team Settings**。在左侧边栏中选择 **Authentication**。
1. 确认您的团队仅启用了 SSO 身份验证方法。然后，选择 **Domains** 选项卡。

    > 您的团队必须仅启用基于 SAML 的 SSO 身份验证方法才能设置域名捕获。必须关闭替代身份验证方法，例如 Postman 或 Google 登录。

1. 选择 **Add Domain**。

    ![选择添加域名](https://assets.postman.com/postman-docs/v10/select-add-domain-v10.jpg)

1. 输入要添加的域名或子域名，然后选择 **Generate Verification Record**。

    <img alt="生成验证记录" src="https://assets.postman.com/postman-docs/v10/enter-domain-name-v10.jpg" width="450px"/>

1. 选择 <img alt="复制图标" src="https://assets.postman.com/postman-docs/icon-copy-v9.jpg#icon" width="15px"> **Copy** 以复制 **TXT 记录**，然后将其添加到您的域名的 DNS 配置中。

    > 如果您还没有准备好将 **TXT 记录** 添加到您的域名的 DNS 配置中，则可以选择 **Verify Later**。有关稍后验证您的域名的信息，请参阅[稍后验证域名](#verifying-a-domain-later)。

1. 选择 **I have added the TXT record to the DNS tool** 复选框，然后选择 **Verify Domain**。请注意，可能需要长达 24 小时才能使 TXT 更改生效，以便成功验证域名。当域名验证成功时，团队管理员将收到电子邮件通知。

    <img alt="添加域名 TXT 记录" src="https://assets.postman.com/postman-docs/v10/add-domain-verification-record-v10.jpg" width="450px"/>

    > 您可以联系[Postman 支持](https://www.postman.com/support/)，以检查您的域名验证请求的状态。

1. 一旦您的域名已验证，您可以[创建请求以启用域名捕获](#enabling-domain-capture)。

### 稍后验证域名

如果您在添加域名时没有验证域名，则可以选择稍后验证域名。

要验证您已添加的域名，请执行以下操作：

1. 打开 Postman 并在 Postman 标头中选择 **Team > Team Settings**。在左侧边栏中选择 **Authentication**。
1. 选择您要验证的具有 `UNVERIFIED` 状态的域名旁边的 **Verify**。

    > 您还可以选择要验证的具有 `UNVERIFIED` 状态的域名旁边的 **Manage**，然后选择 **View Verification Details**。

    ![稍后验证域名](https://assets.postman.com/postman-docs/v10/verify-domain-later-v10.jpg)

1. 选择 <img alt="复制图标" src="https://assets.postman.com/postman-docs/icon-copy-v9.jpg#icon" width="15px"> **Copy** 以复制 **TXT 记录**，然后将其添加到您的域名的 DNS 配置中。
1. 选择 **I have added the TXT record to the DNS tool** 复选框，然后选择 **Verify Domain**。Postman 团队将检查您请求的域名，并在您的域名仪表板中将其状态更新为 `VERIFIED`。当域名验证成功时，团队管理员将收到电子邮件通知。

    <img alt="验证未验证的域名" src="https://assets.postman.com/postman-docs/v10/verify-unverified-domain-later-v10.jpg" width="450px"/>

    > 您可以联系[Postman 支持](https://www.postman.com/support/)，以检查您的域名验证请求的状态。

1. 一旦您的域名已验证，您可以[创建请求以启用域名捕获](#enabling-domain-capture)。

### 查看验证详细信息



团队管理员可以通过导航到[域名仪表板](https://go.postman.co/settings/team/domain-capture)来查看已验证和未验证域名的验证详细信息。验证详细信息显示验证**TXT记录**。

1. 打开Postman并在Postman标题中选择**团队>团队设置**。在左侧边栏中选择**身份验证**。
2. 选择要查看验证详细信息的域旁边的**管理**。
3. 选择**查看验证详细信息**。

### 查看未认领的帐户

未认领的帐户是与已验证域名相关联但不属于您团队的帐户。团队管理员可以通过导航到[域名仪表板](https://go.postman.co/settings/team/domain-capture)来查看未认领的帐户。

1. 打开Postman并在Postman标题中选择**团队>团队设置**。在左侧边栏中选择**身份验证**。
2. 选择具有`已验证`状态的域旁边的**管理**，然后选择**查看帐户**。

    > 可选地，您可以在域名仪表板中选择未认领帐户的数量。

3. 查看不属于您团队的帐户列表。

    <img alt="View unclaimed accounts" src="https://assets.postman.com/postman-docs/v10/view-unclaimed-accounts-v10.jpg" width="450px"/>

4. 可选地，您可以选择**导出CSV**将列表导出为CSV文件。您将收到一封包含下载链接的电子邮件。

## 启用域名捕获

在添加和验证域名或子域名之后，团队管理员可以通过导航到[域名仪表板](https://go.postman.co/settings/team/domain-capture)创建请求以启用域名捕获。要启用域名捕获，团队管理员必须使用Postman支持创建请求。一旦请求获得批准，团队管理员可以与Postman支持合作管理[未认领的帐户](#查看未认领的帐户)。

执行以下操作以启用域名捕获：

1. 打开Postman并在Postman标题中选择**团队>团队设置**。在左侧边栏中选择**身份验证**。
2. 选择具有`已验证`状态的域旁边的**管理**，然后选择**请求认领**。然后，Postman支持将与团队管理员联系以解释启用域名捕获的影响。
3. 一旦请求获得批准，您可以[联系Postman支持](#联系支持以管理帐户)以管理[未认领的帐户](#查看未认领的帐户)。

要查看启用域名捕获的请求状态，请选择域旁边的**管理**。选择**请求认领**后，请求状态将更改为`请求已发送`。

![Request to claim sent](https://assets.postman.com/postman-docs/v10/request-to-claim-sent-v10.jpg)

一旦请求获得批准，屏幕顶部将显示通知，说明**已启用帐户捕获**。

![Domain capture enabled](https://assets.postman.com/postman-docs/v10/domain-capture-enabled-v10.jpg)

> 要关闭域名捕获，您必须[联系Postman支持](#联系支持以管理帐户)。

### 用户体验

启用域名捕获后，使用您的域名或子域名注册Postman的新用户将自动添加到您的团队中。

与域名或子域名相关联的现有Postman用户仅在加入您的团队后才能访问Postman。这适用于其他团队的现有用户和现有个人用户。下次现有用户登录Postman时，他们将收到通知，说明您的团队管理他们的帐户。现有用户可以使用此通知加入团队。

<img alt="Domain capture join team notification" src="https://assets.postman.com/postman-docs/domain-capture-join-team-9.4.jpg" width="350px"/>

> 您将无法有选择性地选择要添加到团队中的用户。启用后，未认领帐户的数量将减少，因为这些用户登录并加入您的团队。

以前在其他Postman团队中的现有用户将失去其早期团队的所有数据，包括个人工作区。不会将任何数据从他们的早期团队转移到他们的新团队。用户将无法留在或加入额外的Postman团队以使用其捕获的帐户。

> 要将现有用户的集合和环境从他们的早期团队转移到他们的新团队，请[联系Postman支持](#联系支持以管理帐户)。

有关启用域名捕获的影响的更多详细信息，请参见[域名捕获FAQ](#域名捕获FAQ)。

> 如果用户在加入您的Postman团队时遇到任何问题，请联系[Postman支持](https://www.postman.com/support/)。

### 联系支持以管理帐户

一旦获得[启用域名捕获](#启用域名捕获)的批准，团队管理员可以通过导航到[域名仪表板](https://go.postman.co/settings/team/domain-capture)来联系Postman支持。联系Postman支持以认领不属于您团队的帐户，将团队合并到您的团队中，并限制用户仅在您的团队中工作。

1. 打开Postman并在Postman标题中选择**团队>团队设置**。在左侧边栏中选择**身份验证**。
2. 选择具有`已验证`状态的域旁边的**管理**，然后选择**联系支持**。

    ![Contact support about managing accounts](https://assets.postman.com/postman-docs/v10/domain-capture-enabled-v10.jpg)

## 删除域名

团队管理员可以通过导航到[域名仪表板](https://go.postman.co/settings/team/domain-capture)从您的团队中删除域名和子域名。

1. 打开Postman并在Postman标题中选择**团队>团队设置**。在左侧边栏中选择**身份验证**。
2. 选择要删除的域旁边的**管理**。
3. 选择**删除域名**。

## 域名捕获FAQ

### 启用域名捕获后，捕获的用户及其数据（集合、环境）会发生什么？

捕获用户的体验取决于他们的先前团队状态：

* 如果被捕获的用户已经在您的组织团队中，对他们来说不会有任何变化。
* 如果被捕获的用户不属于任何团队：
    * 所有现有用户会话将被撤销。
    * 用户下次登录时，将提示使用SSO加入您的组织团队。
    * 当用户使用SSO验证进入您的组织团队时，他们的现有数据将被转移到该团队。
* 如果被捕获的用户是现有免费或付费团队的一部分：
    * 他们将从现有团队中删除。
    * 所有现有用户会话将被撤销。
    * 用户下次登录时，将提示使用SSO加入您的组织团队。
    * 用户可以使用SSO验证进入您的组织团队。
    * 他们将失去从早期团队获得的所有数据，包括个人工作区。不会将任何数据从早期团队转移到新团队。
        > 要将现有用户的集合和环境从早期团队转移到新团队，请[联系Postman支持](#contacting-support-to-manage-accounts)。
* 如果被捕获的用户是现有免费团队的最后一个管理员：
    * 他们将从团队中删除，其余用户将被分配[管理员角色](/docs/collaborating-in-postman/roles-and-permissions/#team-roles)。
    * 所有现有用户会话将被撤销。
    * 用户下次登录时，将提示使用SSO加入您的组织团队。
    * 用户可以使用SSO验证进入您的组织团队。
    * 他们将失去从早期团队获得的所有数据，包括个人工作区。不会将任何数据从早期团队转移到新团队。
        > 要将现有用户的集合和环境从早期团队转移到新团队，请[联系Postman支持](#contacting-support-to-manage-accounts)。
* 如果被捕获的用户是现有付费团队的最后一个管理员：
    * 在验证您添加到团队的域之前，Postman支持将与您的团队管理员联系，讨论如何处理此问题。
    * 所有现有用户会话将被撤销。
    * 用户下次登录时，将提示离开他们现有的团队。
    * 他们需要联系[Postman支持](https://www.postman.com/support/)将管理员角色分配给另一个团队成员并将其从团队中删除。
    * 用户可以使用SSO验证进入您的组织团队。
    * 他们将失去从早期团队获得的所有数据，包括个人工作区。不会将任何数据从早期团队转移到新团队。
        > 要将现有用户的集合和环境从早期团队转移到新团队，请[联系Postman支持](#contacting-support-to-manage-accounts)。

### 团队管理员是否可以在启用域捕获之前查看将被捕获的用户帐户列表？

是的，团队管理员可以在确认要启用域捕获之前查看将被捕获的未声明的Postman帐户列表。要了解更多信息，请参见[查看未声明的帐户](#viewing-unclaimed-accounts)。

### 添加域是否会自动将所有使用组织域的团队成员添加到组织团队中？

不会，团队管理员添加域后，必须创建请求以便Postman团队验证域或子域。一旦满足这两个标准，团队管理员可以创建请求以启用域捕获。然后，Postman支持将联系团队管理员，以解释启用域捕获的影响。要了解更多信息，请参见[启用域捕获](#enabling-domain-capture)。