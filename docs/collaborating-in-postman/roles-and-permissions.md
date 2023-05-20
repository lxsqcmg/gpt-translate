---
title: "Defining roles"
order: 72
updated: 2022-12-19
page_id: "roles_and_permissions"
warning: false
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Working with your team"
    url: "/docs/collaborating-in-postman/working-with-your-team/collaboration-overview/"
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "Postman 101 for Admins | Webinar"
    url: "https://youtu.be/rEKvQO8EYR8"
  - type: link
    name: "Working With Your Team in Postman | The Exploratory"
    url: "https://youtu.be/5lscUV-Exac"
  - type: link
    name: "Super Admin Role for Enterprise | Postman Level Up"
    url: "https://youtu.be/SbvSAvs0Ii8"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Manage large teams in Postman with workspaces, permissions & more"
    url: "https://blog.postman.com/postman-team-workspaces-and-permissions/"
  - type: subtitle
    name: "Case Studies"
  - type: link
    name: "Western Governors University (WGU) uses the Super Admin role for API assets"
    url:  "https://www.postman.com/case-studies/wgu/"
---

> Certain team options are only available on **[Postman paid plans](https://www.postman.com/pricing)**. To learn which roles are available on your plan, go to your **[web dashboard](https://go.postman.co/settings/team/roles)**.

Roles define user permissions within a Postman team and a user's level of access to a Postman element, like a collection or an API.

## Contents

* [Team roles](#team-roles)
    * [Managing team roles](#managing-team-roles)
* [Workspace roles](#workspace-roles)
* [Element-based roles](#element-based-roles)
    * [Collection roles](#collection-roles)
    * [API roles](#api-roles)
    * [Environment roles](#environment-roles)
    * [Mock server roles](#mock-server-roles)
    * [Monitor roles](#monitor-roles)
* [Partner roles](#partner-roles)
* [Next steps](#next-steps)

## Team roles

With the [Admin role](/docs/collaborating-in-postman/roles-and-permissions/#team-roles), you have the power to define Postman access at the team level. You can use Postman's role-based access control system to limit visibility of team resources, define your development workflow, and give access to administrative and billing personnel. Each user on a team must have at least one role attached to them, and can hold multiple roles simultaneously.

You can [assign](/docs/administration/managing-your-team/managing-your-team/) one or more role types to team members, based on the functions those team members require:

* **Super Admin** ([Enterprise plans only](https://www.postman.com/pricing)) - Manages everything within a team, including team settings, members, roles, and resources in [public, team, or private workspaces](/docs/collaborating-in-postman/using-workspaces/managing-workspaces/#changing-workspace-visibility). Team members with this role can perform all actions that Admin, Billing, Community Manager, API Network Manager, Developer, and Partner Manager roles can perform. For information on assigning this role, see [Managing Super Admins](/docs/administration/managing-your-team/managing-your-team/#managing-super-admins).
* **Admin** - Manages team members and team settings. Can also view monitor metadata and run, pause, and resume monitors.
* **Billing** - Manages team plan and payments. Billing roles can be granted by a Super Admin, Team Admin, or by a fellow team member with a Billing role.
* **Developer** - Has access to all team resources and workspaces.
* **Community Manager** ([Professional and Enterprise plans only](https://www.postman.com/pricing)) - Manages the public visibility of workspaces and team profile.
* **API Network Manager** ([Enterprise plans only](https://www.postman.com/pricing)) - Manages a team's [Private API Network](/docs/collaborating-in-postman/adding-private-network/), including adding APIs and reviewing requests to add APIs.
* **Partner Manager** (Internal, [Enterprise plans only](https://www.postman.com/pricing)) - Manages all [Partner Workspaces](/docs/collaborating-in-postman/using-workspaces/partner-workspaces/) within an organization. Controls Partner Workspace settings and visibility, and can send invites to partners. To learn more, see [Partner roles](#partner-roles).
* **Partner** (External, [Enterprise plans only](https://www.postman.com/pricing)) - All partners are automatically granted the Partner role at the team level. Partners can only access the [Partner Workspaces](/docs/collaborating-in-postman/using-workspaces/partner-workspaces/) they've been invited to. To learn more, see [Partner roles](#partner-roles).
* **Guest** (External) - Views collections and sends requests in collections that have been shared with them. This role can't be directly assigned to a user. To learn more, see [Allowing external users to view collections](/docs/collaborating-in-postman/sharing/#allowing-external-users-to-view-collections).
* **Flow Editor** ([Annual Professional plans only](https://www.postman.com/pricing/#postman-flows-access-and-pricing)) - Can create, edit, and deploy [Postman Flows](/docs/postman-flows/gs/flows-overview/).

> If you are on a [Postman Enterprise plan](https://www.postman.com/pricing), you can also assign roles at the [group level](/docs/administration/managing-your-team/user-groups/).

Team roles offer high-level access control:

| Permission | Super Admin | Admin | Billing | Developer | Community Manager |
| --- |:---:| --- | --- | --- | --- |
| Add users | &#x2714; | &#x2714; | | | |
| Remove users | &#x2714; | &#x2714; | | | |
| Manage team Admins and Developers | &#x2714; | &#x2714; | | | |
| Manage SSO | &#x2714; | &#x2714; || | |
| Add and edit custom domains  | &#x2714; | &#x2714; | | | &#x2714; |
| Delete custom domains  | &#x2714; | &#x2714; | | | |
| View audit logs  | &#x2714; | &#x2714; | | | &#x2714; |
| View usage data | &#x2714; | &#x2714; | &#x2714; | &#x2714; | &#x2714; |
| Manage Billing members | &#x2714; | &#x2714; | &#x2714; | | |
| Manage payment | &#x2714; | | &#x2714; | | | |
| Change plan  | &#x2714; | | &#x2714; | | |
| View shared APIs, collections, environments, mock servers and monitors | &#x2714; | | | &#x2714; | &#x2714; |
| View and create team workspaces | &#x2714; | | | &#x2714; | &#x2714; |
| Change visibility of workspaces to team or public | &#x2714; | | | &#x2714;&ast; | &#x2714; |
| Approve requests to change workspace visibility&ast;&ast; | &#x2714; | | | | &#x2714; |
| Enable public team profile | &#x2714; | &#x2714; | | | &#x2714; |
| Manage a team's Private API Network&ast;&ast;&ast; | &#x2714; | | | | |

&ast; On Postman Basic and Free plans, any developer can change visibility of workspaces.

&ast;&ast; Enterprise and Professional plans only.

&ast;&ast;&ast; Enterprise plans only. Teams that don't use the [optional approval process workflow](/docs/collaborating-in-postman/adding-private-network/#using-the-approval-process-workflow) for the Private API Network can allow users with [an API Editor role](/docs/collaborating-in-postman/roles-and-permissions/#element-based-roles) to add APIs to the Private API Network instead.

> **Postman support users**. Team members with a Developer or Super Admin role consume a paid seat on your team. Team members who have only Admin or Billing roles become support users and don’t consume paid seats. Each team can have two support users.

### Managing team roles

To learn how to manage team roles in Postman, see [Managing your team](/docs/administration/managing-your-team/managing-your-team/).

## Workspace roles

You can [assign](/docs/collaborating-in-postman/using-workspaces/managing-workspaces/#managing-workspace-roles) three role types in Postman workspaces: **Admin**, **Editor**, and **Viewer**. Partner Workspaces offer an additional role type: **Partner Lead**.

* **Admin** - Can manage workspace resources and settings.
* **Editor** ([Professional and Enterprise plans only](https://www.postman.com/pricing)) - Can create and edit workspace resources.
* **Viewer** ([Professional and Enterprise plans only](https://www.postman.com/pricing)) - Can view, fork, and export workspace resources.
* **Partner Lead** (External, [Enterprise plans only](https://www.postman.com/pricing)) - Can invite other partners from their organization to join a [Partner Workspace](/docs/collaborating-in-postman/using-workspaces/partner-workspaces/). To learn more, see [Partner roles](#partner-roles).

The following roles control access at a workspace level:

| Action | Admin | Editor | Viewer |
| --- | --- | --- | --- |
| Join and leave workspaces | &#x2714; | &#x2714; | &#x2714; |
| Send requests | &#x2714; | &#x2714; | &#x2714; |
| Add and remove APIs, collections, and environments | &#x2714; | &#x2714; | |
| Manage integrations | &#x2714; | &#x2714; | |
| Add monitors and mock servers | &#x2714; | &#x2714; | |
| Create and delete workspaces | &#x2714; | | |
| Edit workspace details | &#x2714; | | |
| Add and remove members | &#x2714; | | |
| Manage workspace roles | &#x2714; | | |
| Manage workspace visibility | &#x2714;&ast; | | |

&ast; On Professional and Enterprise plans, an Admin for a workspace must request to change its visibility to public. This request will go to the [Community Manager](#team-roles). On Basic and Free plans, or if a team has no Community Manager assigned, an Admin for a workspace can control its visibility.

## Element-based roles

At the element level, you can assign roles to team members that decide their level of access to Postman [collections](#collection-roles), [APIs](#api-roles), [mock servers](#mock-server-roles), and [monitors](#monitor-roles).

### Collection roles

You can assign two role types in Postman collections: **Editor** and **Viewer**.

* **Editor** - Can edit collections directly
* **Viewer** - Can view, fork, and export collections

You can assign a limited Viewer role to an external user who isn't in your Postman team by [allowing them to view specific collections](/docs/collaborating-in-postman/sharing/#allowing-external-users-to-view-collections). User with this role can only view collections and send requests in the collections that have been shared with them.

The following roles control access at a collection level:

| Collections |  Editor  | Viewer |
| ---   |   ---     | ---   |
| Edit and delete collections |    &#x2714;   |     |
| Manage roles on collections  |  &#x2714;   |   |
| Export collections  |   &#x2714;   | &#x2714;   |
| Fork collections |   &#x2714;   | &#x2714;   |
| Merge forks on collections  |    &#x2714;     |    |
| Publish collection documentation and add to API Network  |   &#x2714;  |   |
| Share collections to a different workspace  |  &#x2714;  | &#x2714;   |
| Tag and restore collection versions   |  &#x2714;   |   |
| Add, edit, and delete mock servers  |    &#x2714;      |   |
| Add, edit, and delete monitors |    &#x2714;   |     |

### API roles

You can assign two role types in Postman APIs: **Editor** and **Viewer**.

* **Editor** - Can edit APIs directly
* **Viewer** - Can view and export APIs

The following roles control access at an API level:

| APIs |   Editor   | Viewer |
| ---   |   ---     | ---   |
| Edit and delete APIs |  &#x2714;     |     |
| Manage roles on APIs  |  &#x2714;   |   |
| Share APIs  |   &#x2714;   | &#x2714;   |
| Comment on APIs |   &#x2714;   |    |
| Comment on published API versions |   &#x2714;   | &#x2714;   |
| Create new API versions |  &#x2714;   |    |
| Update schema |  &#x2714;   |    |
| Generate collections from the schema |   &#x2714;  |    |
| View reports for APIs |   &#x2714;  | &#x2714;   |
| Add and remove API environments |   &#x2714;  |    |
| Add and remove API documentation |   &#x2714;  |   |
| Add and remove API tests |   &#x2714;  |   |
| Add and remove API monitors |   &#x2714;  |    |
| Add and remove API mock servers |   &#x2714;  |    |

## Environment roles

You can [assign](/docs/sending-requests/managing-environments/#managing-environment-roles) two role types for Postman environments: **Editor** and **Viewer**.

* **Editor** - Can edit and manage environments
* **Viewer** - Can view and use environments

The following roles control access at the mock server level:

Environment | Editor | Viewer
--- | --- | ---
View environment | &#x2714; | &#x2714;
Use environment | &#x2714; | &#x2714;
Edit the current value of variables | &#x2714; | &#x2714;
Edit and delete environments | &#x2714; |
Manage environment roles | &#x2714; |
Move environment | &#x2714; |

## Mock server roles

You can assign two role types for Postman mock servers: **Editor** and **Viewer**.

* **Editor** - Can edit and manage mock servers
* **Viewer** - Can view mock servers and associated metadata

The following roles control access at the mock server level:

Mock server | Editor | Viewer
--- | --- | ---
View mock server | &#x2714; | &#x2714;
View mock server call logs and call log details | &#x2714; | &#x2714;
View mock server metadata | &#x2714; | &#x2714;
Edit and delete mock servers | &#x2714; |
Manage mock server roles | &#x2714; |
Move mock server | &#x2714; |

## Monitor roles

You can [assign](/docs/monitoring-your-api/faqs-monitors/#who-can-edit-my-monitors) four role types for Postman Monitors: **Editor** and **Viewer**.

* **Super Admin** - Can view monitor metadata and run, pause, and resume monitors.
* **Admin** - Can view monitor metadata and run, pause, and resume monitors.
* **Editor** - Can view monitor metadata, metrics, jobs, and runs. Can run, update, delete, pause, and resume the monitor.
* **Viewer** - Can view monitor metadata, metrics, jobs, and runs.

Monitors | Super Admin | Admin | Editor | Viewer |
--- | --- | --- | --- | --- |
View monitor | &#x2714; | &#x2714; | &#x2714; | &#x2714;
View monitor metadata, results, activity, and summary metrics | &#x2714; | &#x2714; | &#x2714; | &#x2714;
Create monitor read integrations | | | &#x2714; | &#x2714;
View monitor based integrations | | | &#x2714; | &#x2714;
Edit and delete monitor | | | &#x2714; |
Run, pause, and resume monitor | &#x2714; | &#x2714; | &#x2714; |
Move monitor | | | &#x2714; |
Update monitor roles | | |  &#x2714; |

## Partner roles

> **[Partner roles are available on Postman Enterprise plans.](https://www.postman.com/pricing)**

Partner roles relate to [Partner Workspaces](/docs/collaborating-in-postman/using-workspaces/partner-workspaces/) and are applied at the team and workspace level. There are different partner roles you can assign to team members and external partners:

|  | For team members | For partners |
| --- |:---:| --- |
| **Team level** | Partner Manager | Partner |
| **Workspace level** | Admin, Viewer, Editor | Viewer, Editor <br> Partner Lead (optional) |

You can [assign](/docs/administration/managing-your-team/managing-your-team/) partner roles at the team level:

* **Partner Manager** (Internal) - Manages all Partner Workspaces within an organization. Controls Partner Workspace settings and visibility, and can send invites to partners.
* **Partner** (External) - All partners are automatically granted the Partner role at the team level. Partners can only access the Partner Workspaces they've been invited to.

You can also [assign](/docs/collaborating-in-postman/using-workspaces/managing-workspaces/#managing-workspace-roles) partner roles at the workspace level:

* **Partner Lead** (External) - Can invite other partners from their organization to join a Partner Workspace.

All partners are assigned Workspace Editor or Viewer roles when invited to a Partner Workspace. To learn more about workspace level permissions, see [Workspace roles](#workspace-roles).

> Your team must have [available seats](/docs/administration/billing/#changing-your-plan) or [Auto-Flex enabled](/docs/administration/billing/#using-auto-flex) to invite a partner as a Workspace Editor. Otherwise, the partner will be assigned the Workspace Viewer role. Assigning a partner the Workspace Viewer role doesn't consume paid seats.

## Next steps

After learning about the roles available to team members, you can manage your team's level of access and control more effectively.

* To learn more about team management, including managing team roles and inviting collaborators to join your team, visit [Managing your team](/docs/administration/managing-your-team/managing-your-team/).
