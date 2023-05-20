---
title: "管理您的团队"
order: 121
updated: 2022-12-19
page_id: "managing_your_team"
warning: false
contextual_links:
  - type: section
    name: "其他资源"
  - type: subtitle
    name: "视频"
  - type: link
    name: "管理员的Postman 101"
    url: "https://youtu.be/rEKvQO8EYR8"
  - type: link
    name: "API团队的协作和治理 | Postman Intergalactic"
    url: "https://youtu.be/4rxpdcGeixs"
  - type: subtitle
    name: "博客文章"
  - type: link
    name: "如何安全地部署Postman，第1部分：用户管理"
    url: "https://blog.postman.com/how-to-securely-deploy-postman-at-scale-user-management/"
  - type: link
    name: "更有效地管理您的公共API集合"
    url: "https://blog.postman.com/govern-your-public-api-collections-more-effectively/"

---

> **[某些团队选项仅适用于Postman专业版和企业版计划。](https://www.postman.com/pricing)**

Postman提供了各种选项来定制您的团队体验，从初始设置到持续的团队和计划管理。作为团队管理员，您可以简化团队的入职流程，管理访问控制，并让您的团队始终了解Postman的最新版本。

## 目录

* [设置您的团队](#设置您的团队)
* [管理团队成员](#管理团队成员)
    * [邀请用户](#邀请用户)
        * [了解邀请权限](#了解邀请权限)
    * [管理邀请](#管理邀请)
    * [删除团队成员](#删除团队成员)
    * [管理团队角色](#管理团队角色)
        * [管理超级管理员](#管理超级管理员)
    * [管理合作伙伴](#管理合作伙伴)
    * [管理访客](#管理访客)
* [管理您的团队的Postman计划](#管理您的团队的postman计划)
    * [更改团队大小](#更改团队大小)
    * [升级您的计划](#升级您的计划)
* [更新您的团队的Postman版本](#更新您的团队的postman版本)
* [下一步](#下一步)

## 设置您的团队

创建Postman团队后，您可以采取以下步骤，启用高效的用户入职流程：

* 使用[入职清单](/docs/administration/onboarding-checklist/)，确保Postman在您的组织使用的所有设备上可用，并且可以正常运行。
* [启用团队发现](/docs/collaborating-in-postman/working-with-your-team/enabling-team-discovery/)，让来自您组织的其他Postman用户请求加入您的团队。
* [配置SSO](/docs/administration/sso/admin-sso/)（仅限[专业版和企业版计划](https://www.postman.com/pricing)）。
* [配置SCIM provisioning](/docs/administration/scim-provisioning/scim-provisioning-overview/)（仅限[企业版计划](https://www.postman.com/pricing)）。

## 管理团队成员

您可以随时在Postman中邀请协作者、删除现有团队成员并更新用户权限。

### 邀请用户

1. 在您的[团队仪表板](https://go.postman.co/settings/team/members)中，选择**邀请人员**。
1. 输入您要邀请的人员的电子邮件地址。

    > 您还可以上传包含您要邀请的人员的电子邮件地址的文本或CSV文件。要这样做，请选择**从文件添加**。

1. 使用**角色**为这些用户分配一个或多个[团队角色](/docs/collaborating-in-postman/roles-and-permissions/#team-roles)。
1. 选择**发送邀请**。

<img alt="邀请用户加入团队" src="https://assets.postman.com/postman-docs/v10/team-invite-people-v10.jpg" width="400px"/>

您还可以使用链接邀请用户加入您的团队。要这样做，请选择**复制邀请链接**。

#### 了解邀请权限

作为团队[管理员或超级管理员](/docs/collaborating-in-postman/roles-and-permissions/#team-roles)，您可以直接发送任何角色类型的邀请。在[免费、基础和专业版计划](https://www.postman.com/pricing/)上，具有开发人员角色的团队成员可以自动邀请外部用户作为开发人员，无需团队管理员批准。您可以在您的[团队仪表板](https://go.postman.co/settings/team/members)下的**已发送邀请**中查看待处理的邀请。有关更多详细信息，请参见[管理邀请](#管理邀请)。

如果发送邀请的团队成员不是在免费、基础或专业版计划上邀请另一个开发人员的开发人员或任何计划上的团队管理员，则他们向您建议将外部用户添加到您的Postman团队，需要您批准。您可以在您的[团队仪表板](https://go.postman.co/settings/team/members)下的**建议**中查看这些邀请建议。有关更多详细信息，请参见[管理邀请](#管理邀请)。

您还可以通过启用[团队发现](/docs/collaborating-in-postman/working-with-your-team/enabling-team-discovery/#enabling-team-discovery)让Postman用户从您的公司请求加入您的团队。

> [Postman企业版](https://www.postman.com/pricing)团队可以启用[SCIM provisioning](/docs/administration/scim-provisioning/scim-provisioning-overview/)，从而可以通过您的身份提供者（IdP）批量创建、更新和停用用户帐户。

### 管理邀请

作为团队管理员，您可以管理[待处理邀请](#已发送邀请)，审核没有直接发送邀请权限的团队成员的[建议](#建议)，以及查看[邀请链接](#邀请链接)。

#### 已发送邀请

您还可以在您的[团队仪表板](https://go.postman.co/settings/team/members)下的**已发送邀请**中查看团队成员提交的待处理邀请。要重新发送邀请，请将鼠标悬停在该人员的名称上，然后选择**重新发送邀请**。要复制邀请链接，请选择复制邀请链接图标<img alt="复制邀请链接图标" src="https://assets.postman.com/postman-docs/icon-copy-v9.jpg#icon" width="15px">。要删除邀请，请选择撤销邀请图标<img alt="撤销邀请图标" src="https://assets.postman.com/postman-docs/icon-close.jpg#icon" width="16px">。

<img alt="查看已发送邀请" src="https://assets.postman.com/postman-docs/v10/team-manage-invite-requests-v10.jpg"/>

#### 建议

如果发送邀请的团队成员不是在免费、基础或专业版计划上邀请另一个开发人员的开发人员（或在任何计划上不是团队管理员），则您或具有管理员或超级管理员角色的另一名团队成员必须审核邀请建议。您可以在您的[团队仪表板](https://go.postman.co/settings/team/members)下的**建议**中查看这些邀请建议。

要批准建议并邀请用户加入您的团队，请选择**邀请**。要删除邀请，请选择撤销邀请图标<img alt="撤销邀请图标" src="https://assets.postman.com/postman-docs/icon-close.jpg#icon" width="16px">。



<img alt="Review invite suggestions" src="https://assets.postman.com/postman-docs/v10/team-manage-invite-suggestions-v10.jpg"/>

#### 邀请链接

您可以通过打开您的[团队仪表板](https://go.postman.co/settings/team/members)并从左侧菜单中选择[**邀请链接**](https://go.postman.co/settings/team/manage-invite-links)来查看您的团队发送的邀请。该列表提供了有关哪些用户生成了链接、何时生成、何时过期以及它们的URL的信息。

<img alt="Invite links dashboard" src="https://assets.postman.com/postman-docs/team-manage-invite-links-v9.2.jpg"/>

要复制活动邀请的URL，请将鼠标悬停在其行上，然后选择复制图标<img alt="Copy link icon" src="https://assets.postman.com/postman-docs/icon-copy-v9.jpg#icon" width="15px">。

要撤销活动邀请，请将鼠标悬停在其行上，然后选择删除图标<img alt="Delete link icon" src="https://assets.postman.com/postman-docs/icon-delete-v9.jpg#icon" width="12px" />。

### 删除团队成员

要从团队中删除成员，请转到您的[团队仪表板](https://go.postman.co/settings/team/members)。选择团队成员姓名旁边的删除图标<img alt="Delete icon" src="https://assets.postman.com/postman-docs/icon-delete-v9.jpg#icon" width="12px">。然后确认，选择**删除成员**。当您删除团队成员时，您仍将保留对他们与团队共享的任何数据的访问权限。

![Removing a team member](https://assets.postman.com/postman-docs/v10/remove-team-member-v10.jpg)

重新分配他们的个人工作区给另一个团队成员，以确保团队继续访问用户被删除时完成的任何未共享的工作。如果以下任一条件为真，则必须重新分配他们的个人工作区：

* 他们来自企业团队。
* 他们来自免费、基本或专业团队，并且他们有个人帐户。

> 个人帐户不与团队关联，只有用户可以访问。要访问个人帐户，请参阅[在团队之间切换](/docs/collaborating-in-postman/working-with-your-team/collaboration-overview/#switching-between-teams)。

<img alt="Confirmation for removing a team member" src="https://assets.postman.com/postman-docs/remove-user-from-team-v9.2.jpg" width="400px"/>

当您删除团队成员时，如果以下条件为真，则他们的个人工作区及其中的数据将移至个人帐户：他们来自免费、基本或专业团队，并且他们没有个人帐户。

> 请注意，当您从团队中删除成员时，这不会自动减少您的团队的付费席位数量，除非该成员是在当前的自动弹性周期中由[自动弹性](/docs/administration/billing/#using-auto-flex)添加的。如果您想减少团队的付费席位数量，您的团队成员[账单角色](/docs/collaborating-in-postman/roles-and-permissions/#team-roles)可以[编辑您的计划](/docs/administration/billing/#changing-your-plan)。

### 管理团队角色

每个团队成员必须被分配一个或多个团队角色，这将允许他们在您的团队中执行不同的操作。角色可以分配给单个团队成员，也可以分配给[组](/docs/administration/managing-your-team/user-groups/)的成员。

您可以从您的[团队仪表板](https://go.postman.co/settings/team/members)更改团队成员的角色。

通过在搜索字段中键入其名称或电子邮件地址来搜索特定用户。您还可以按角色类型过滤用户。选择您要更新的用户旁边的角色，然后选择您要分配或删除的角色。选择**更新角色**以确认更改。

<img alt="Edit team roles" src="https://assets.postman.com/postman-docs/v10/update-team-roles-v10.1.jpg"/>

每个团队可以免费拥有两个支持帐户。支持帐户是仅具有管理员或账单角色的团队成员。具有超级管理员或开发人员角色的团队成员将消耗您团队的付费席位。

有关您可以作为团队管理员分配的Postman团队角色的完整详细信息，请参见[团队角色](/docs/collaborating-in-postman/roles-and-permissions/#team-roles)。某些角色仅适用于具有[Postman专业版或企业版](https://www.postman.com/pricing)计划的团队。

#### 管理超级管理员

> **[超级管理员仅适用于Postman企业版计划。](https://www.postman.com/pricing)**

如果您的团队尚未拥有[超级管理员](/docs/collaborating-in-postman/roles-and-permissions/#team-roles)，团队管理员可以将该角色分配给团队中的任何人。一旦您的团队至少有一个超级管理员，只有超级管理员才能将此角色分配给另一个用户。

超级管理员可以在[团队仪表板](https://go.postman.co/settings/team/members)中向用户分配超级管理员角色，也可以在[邀请新团队成员](#inviting-users)和[group](/docs/administration/managing-your-team/user-groups/#editing-team-roles-for-a-group)中分配超级管理员角色。如果您的团队正在使用[SCIM](/docs/administration/scim-provisioning/scim-provisioning-overview/)，则必须由超级管理员创建[SCIM凭据](/docs/administration/scim-provisioning/scim-provisioning-overview/#enabling-scim-provisioning)才能使SCIM更改已分配超级管理员角色的组的成员身份。

常规团队管理员无法从团队中删除超级管理员或删除其超级管理员角色分配。

建议您创建一个不与任何个人关联的服务用户，并将该用户分配为超级管理员角色。通过这样做，您的团队可以避免因实际用户离开您的公司而导致服务中断的风险，并确保您的团队管理人员能够在需要时登录服务帐户。

### 管理合作伙伴

> **[合作伙伴仅适用于Postman企业版计划。](https://www.postman.com/pricing)**

您可以像管理内部团队成员一样管理外部合作伙伴。有关详细信息，请参见[合作伙伴工作区](/docs/collaborating-in-postman/using-workspaces/partner-workspaces/)。

### 管理访客

您可以管理具有查看特定集合和发送集合中请求权限的外部用户。具有这些权限的外部用户被分配[访客角色](/docs/collaborating-in-postman/roles-and-permissions/#team-roles)。[团队管理员](/docs/collaborating-in-postman/roles-and-permissions/#team-roles)可以通过转到您的[团队仪表板](https://go.postman.co/settings/team/members)并选择**转换**来将外部用户的角色从访客角色更改为开发人员角色。当您将外部用户的角色从访客角色更改为开发人员角色时，他们将被添加到团队并获得访问所有团队资源和工作区的权限。

![Convert Guest role](https://assets.postman.com/postman-docs/v10/convert-guest-role-v10.jpg)

> 您的团队必须具有[可用席位](/docs/administration/billing/#changing-your-plan)或[启用自动弹性](/docs/administration/billing/#using-auto-flex)才能将外部用户的角色从访客角色更改为开发人员角色。

一个团队管理员也可以查看用户分配为访客角色可以访问的工作区和集合。前往您的[团队仪表板](https://go.postman.co/settings/team/members)，并选择**查看资源**。选择工作区名称或集合名称以在新标签页中打开它。您还可以选择用户的名称以转到他们的Postman个人资料。

<img alt="View collections a Guest can view" src="https://assets.postman.com/postman-docs/v10/view-guest-collections-v10.jpg" width="500px"/>

要了解有关与外部用户共享集合的更多信息，请参见[允许外部用户查看集合](/docs/collaborating-in-postman/sharing/#allowing-external-users-to-view-collections)。

有关如何从团队或集合中删除外部用户的信息，请参见[更改外部用户访问集合的访问权限](/docs/collaborating-in-postman/sharing/#changing-external-user-access-to-collections)。

## 管理您的团队的Postman计划

您可以在团队的计费周期内随时管理团队规模或升级计划。

### 更改团队规模

如果您想更改团队的规模，您有两个不同的选项：

* **更改付费席位数量** - 具有计费角色的团队成员可以在[计费仪表板](https://go.postman.co/billing/overview)中更改您的团队的付费席位数量。
* **打开自动扩展** - 您的团队可以邀请更多用户，而无需提前支付更多席位费用，使用[自动扩展](/docs/administration/billing/#using-auto-flex)。

有关更多信息，请参见[团队和计划更改](/docs/administration/billing/#team-and-plan-changes)。

### 升级您的计划

具有计费角色的团队成员可以在[计费仪表板](https://go.postman.co/billing/overview)中升级您的团队计划。有关更多信息，请参见[更改您的计划](/docs/administration/billing/#changing-your-plan)。

## 更新您的团队的Postman版本

如果您的团队没有使用最新版本的桌面应用程序，您可以更新您的团队，以确保每个人都可以访问完整的Postman API开发体验。要这样做，请参见[将您的团队更新到当前版本的Postman](/docs/administration/updating/)。

## 下一步

设置完Postman团队后，您可以使用报告来了解团队的API开发情况，包括测试、文档和监控覆盖范围。

* 要了解有关Postman报告功能的更多信息，请访问[使用报告](/docs/reports/reports-overview/)。(_[企业团队](https://www.postman.com/pricing/)专用。_)