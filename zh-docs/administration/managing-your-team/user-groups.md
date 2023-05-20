---
title: "管理用户组"
order: 141
page_id: "managing_user_groups"
warning: false
updated: 2021-12-06
contextual_links:
  - type: section
    name: "其他资源"
  - type: subtitle
    name: "博客文章"
  - type: link
    name: "介绍 Postman 用户组：更轻松地管理用户访问控制"
    url: "https://blog.postman.com/introducing-postman-groups/"
  - type: subtitle
    name: "案例研究"
  - type: link
    name: "Western Governors University (WGU) 利用用户组创建团队"
    url: "https://www.postman.com/case-studies/wgu/"
---

> **[Postman 企业版计划提供用户组功能。](https://www.postman.com/pricing)**

使用 Postman 用户组，您可以将用户组织成反映组织结构的组。用户组使您能够管理团队访问权限并引入新的团队成员。

您必须是 [Postman 团队管理员](/docs/collaborating-in-postman/roles-and-permissions/#team-roles) 才能创建、管理和删除用户组。

## 目录

* [创建用户组](#创建用户组)

* [编辑用户组](#编辑用户组)

    * [管理用户组成员](#管理用户组成员)

    * [管理用户组访问控制](#管理用户组访问控制)

        * [编辑用户组团队角色](#编辑用户组团队角色)

        * [管理工作区和 Postman 实体的角色](#管理工作区和-postman-实体的角色)

    * [编辑用户组详细信息](#编辑用户组详细信息)

* [删除用户组](#删除用户组)

## 创建用户组

作为团队管理员，您可以通过选择 Postman 标题中的 **团队**，然后选择 **管理团队** 来创建用户组。

在 **成员和组** 下，选择 **组 > 创建组**。

<img alt="创建用户组" src="https://assets.postman.com/postman-docs/team-groups-list-v9.1.jpg"/>

为您的用户组命名并添加描述，添加您的用户，并选择您想要分配给该组的团队角色，然后单击 **创建组**。

<img alt="创建用户组表单" src="https://assets.postman.com/postman-docs/create-a-group-9.5.jpg" width="500px"/>

当添加用户到用户组时，团队成员将收到电子邮件和应用内通知。

> 如果您将具有支持角色（管理员或计费）的用户添加到赋予他们开发者角色的用户组中，则他们将自动占用您的 Postman 团队中的一个可用付费位置。如果没有可用的位置，则您将无法授予该用户组的访问权限。

## 编辑用户组

您可以随时通过管理用户组的用户和访问 Postman 实体来编辑用户组。

### 管理用户组成员

在 Postman 中，选择 Postman 标题中的 **团队**，然后选择 **管理团队**。在 **成员和组** 下，选择 **组**。找到您想要更新的用户组，然后选择它以进行编辑。

选择 **+ 添加** 来将用户添加到用户组中。选择用户旁边的 **X** 将其从用户组中删除。

<img alt="管理用户组成员" src="https://assets.postman.com/postman-docs/edit-group-members-9.5.jpg" width="500px"/>

> 当添加或删除用户组中的用户时，用户将收到电子邮件和应用内通知。

### 管理用户组访问控制

您可以在团队级别、工作区级别和单个集合、API、环境、模拟服务器和监视器上控制用户组的访问权限。

> 当更新角色时，用户将收到应用内通知。

#### 编辑用户组团队角色

在 Postman 中，选择 Postman 标题中的 **团队**，然后选择 **管理团队**。在 **成员和组** 下，选择 **组**。找到您想要更新的用户组，然后选择它以进行编辑。

<img alt="编辑用户组团队角色" src="https://assets.postman.com/postman-docs/edit-group-roles-9.5.1.jpg" width="500px"/>

选择您想要分配给用户组的团队角色，或取消选择您想要从用户组中删除的团队角色，然后单击 **保存更改**。

> 有关您的团队可用角色及其权限的信息，请参阅 [团队角色](/docs/collaborating-in-postman/roles-and-permissions/#team-roles)。

#### 管理工作区和 Postman 实体的角色

您可以控制用户组对单个工作区、集合、API、环境、模拟服务器和监视器的访问权限。有关管理工作区的更多信息，请参阅 [共享工作区](/docs/collaborating-in-postman/using-workspaces/managing-workspaces/#sharing-workspaces)。

对于集合、API、环境、模拟服务器和监视器，请转到您想要管理角色的元素。在侧边栏中，选择更多操作图标 <img alt="更多操作图标" src="https://assets.postman.com/postman-docs/icon-more-actions-v9.jpg#icon" width="16px">，然后选择 **管理角色**。

<img alt="邀请用户组到集合" src="https://assets.postman.com/postman-docs/manage-roles-collection-with-user-group-v9.1.jpg"/>

使用搜索栏添加用户组，然后使用下拉菜单为用户组分配 **编辑器** 或 **查看器** 权限。要删除用户组，请选择用户组名称旁边的 <img alt="关闭图标" src="https://assets.postman.com/postman-docs/icon-close.jpg#icon" width="16px">。选择 **更新角色** 以确认更改。

> 有关在团队、工作区、API 和集合级别的访问控制的更多信息，请参阅 [定义角色](/docs/collaborating-in-postman/roles-and-permissions/)。

### 编辑用户组详细信息

在 Postman 中，选择 Postman 标题中的 **团队**，然后选择 **管理团队**。在 **成员和组** 下，选择 **组**。找到您想要更新的用户组，然后选择它以进行编辑。

<img alt="编辑用户组描述" src="https://assets.postman.com/postman-docs/team-edit-group-description-v9.1.jpg" width="500px"/>

选择页面顶部的用户组名称以进行编辑。要添加描述，请在用户组名称下选择 **添加描述**。要更新现有描述，请选择要编辑的描述。单击 **保存更改** 以确认您的更新。

## 删除用户组

在 Postman 中，选择 Postman 标题中的 **团队**，然后选择 **管理团队**。在 **成员和组** 下，选择 **组**。找到您想要更新的用户组，然后选择它以进行编辑。

选择 **删除** 以删除用户组，然后选择 **删除用户组** 以确认。

<img alt="删除用户组" src="https://assets.postman.com/postman-docs/team-delete-group-v9.1.jpg" width="400px"/>