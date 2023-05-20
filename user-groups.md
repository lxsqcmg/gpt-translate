---
title: "Managing user groups"
order: 141
page_id: "managing_user_groups"
warning: false
updated: 2021-12-06
contextual_links:
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Introducing Postman Groups: Manage Users with Easier Access Control"
    url: "https://blog.postman.com/introducing-postman-groups/"
  - type: subtitle
    name: "Case Studies"
  - type: link
    name: "Western Governors University (WGU) leverages user groups to create teams"
    url: "https://www.postman.com/case-studies/wgu/"
---

> **[Groups are available on Postman Enterprise plans.](https://www.postman.com/pricing)**

With Postman groups, you can organize users into groups that reflect your organizational structure. Groups enable you to manage access to your team and onboard new team members.

You must be a [Postman Team Admin](/docs/collaborating-in-postman/roles-and-permissions/#team-roles) to create, manage, and delete groups.

## Contents

* [Creating a group](#creating-a-group)

* [Editing a group](#editing-a-group)

    * [Managing members of a group](#managing-members-of-a-group)

    * [Managing access control for a group](#managing-access-control-for-a-group)

        * [Editing team roles for a group](#editing-team-roles-for-a-group)

        * [Managing roles on workspaces and Postman entities](#managing-roles-on-workspaces-and-postman-entities)

    * [Editing details for a group](#editing-details-for-a-group)

* [Deleting a group](#deleting-a-group)

## Creating a group

As a Team Admin, you can create a group by selecting **Team** in the Postman header, then select **Manage Team**.

Under **Members and groups**, select **Groups > Create Group**.

<img alt="Create group" src="https://assets.postman.com/postman-docs/team-groups-list-v9.1.jpg"/>

Give your group a name and description, add your users, and select the team roles you would like to assign to the group, then **Create Group**.

<img alt="Create a group form" src="https://assets.postman.com/postman-docs/create-a-group-9.5.jpg" width="500px"/>

Team members will receive an email and in-app notification when added to a group.

> If you add a user with a support-only role (Admin or Billing) to a group that gives them a Developer role, they will automatically take up an available paid spot on your Postman team. If no spots are available, you won't be able to grant access to the group with that user.

## Editing a group

You can edit a group at any time by managing a group's users and access to Postman entities.

### Managing members of a group

In Postman, select **Team** in the Postman header, then select **Manage Team**. Under **Members and groups**, select **Groups**. Locate the group you would like to update and select it to edit.

Select **+ Add** to add a user to the group. Select **X** next to a user to remove them from the group.

<img alt="Manage group members" src="https://assets.postman.com/postman-docs/edit-group-members-9.5.jpg" width="500px"/>

> Users will receive an email and in-app notification when added to or removed from a group.

### Managing access control for a group

You can control a group's access at the team level, workspace level, and on individual collections, APIs, environments, mock servers, and monitors.

> Users will receive an in-app notification when roles are updated.

#### Editing team roles for a group

In Postman, select **Team** in the Postman header, then select **Manage Team**. Under **Members and groups**, select **Groups**. Locate the group you would like to update and select it to edit.

<img alt="Edit group team roles" src="https://assets.postman.com/postman-docs/edit-group-roles-9.5.1.jpg" width="500px"/>

Select the team roles you would like to assign to the group, or deselect team roles you would like to remove from the group, then **Save Changes**.

> For information on roles available to your team and their permissions, see [Team Roles](/docs/collaborating-in-postman/roles-and-permissions/#team-roles).

#### Managing roles on workspaces and Postman entities

You can control a group's access to individual workspaces, collections, APIs, environments, mock servers, and monitors. For more information on managing workspaces, see [Sharing workspaces](/docs/collaborating-in-postman/using-workspaces/managing-workspaces/#sharing-workspaces).

For collections, APIs, environments, mock servers, and monitors, go to the element for which you want to manage roles. In the sidebar, select the more actions icon <img alt="More actions icon" src="https://assets.postman.com/postman-docs/icon-more-actions-v9.jpg#icon" width="16px"> then select **Manage roles**.

<img alt="Invite group to collection" src="https://assets.postman.com/postman-docs/manage-roles-collection-with-user-group-v9.1.jpg"/>

Use the search bar to add the group, then give the group **Editor** or **Viewer** permissions with the dropdown. To remove a group, select <img alt="Close icon" src="https://assets.postman.com/postman-docs/icon-close.jpg#icon" width="16px"> next to the group name. Select **Update Roles** to confirm changes.

> See [Defining roles](/docs/collaborating-in-postman/roles-and-permissions/) for more information on access control at a team, workspace, API, and collection level.

### Editing details for a group

In Postman, select **Team** in the Postman header, then select **Manage Team**. Under **Members and groups**, select **Groups**. Locate the group you would like to update and select it to edit.

<img alt="Edit group description" src="https://assets.postman.com/postman-docs/team-edit-group-description-v9.1.jpg" width="500px"/>

Select the group's name at the top of the page to edit it. To add a description, select **Add a description** under the group's name. To update an existing description, select it to edit. **Save Changes** to confirm your updates.

## Deleting a group

In Postman, select **Team** in the Postman header, then select **Manage Team**. Under **Members and groups**, select **Groups**. Locate the group you would like to update and select it to edit.

Select **Delete** to delete the group, then **Delete Group** to confirm.

<img alt="Delete group" src="https://assets.postman.com/postman-docs/team-delete-group-v9.1.jpg" width="400px"/>
