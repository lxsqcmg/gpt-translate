---
title: "Onboarding checklist"
order: 127
updated: 2022-02-16
search_keyword: "whitelist, whitelist IP"
page_id: "onboarding_checklist"
warning: false
contextual_links:
  - type: section
    name: "Additional resources"
  - type: link
    name: "Security and Compliance: A Shared Responsibility Model"
    url: "https://www.postman.com/trust/shared-responsibility/"
  - type: link
    name: "Managing your team"
    url: "/docs/administration/managing-your-team/managing-your-team/"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Manage Large Teams in Postman with Workspaces, Permissions, and Version Control"
    url: "https://blog.postman.com/postman-team-workspaces-and-permissions/"

---

When you're getting started using Postman within your organization, you can carry out the following preparation steps to set your team up for success.

## Contents

* [Setting up Postman](#setting-up-postman)
    * [Invite team members](#invite-team-members)
    * [Check your setup](#check-your-setup)
    * [Enable team discovery](#enable-team-discovery)
* [Next steps](#next-steps)

## Setting up Postman

You can access Postman [on the web](/docs/getting-started/installation-and-updates/#using-the-postman-web-app) with the [Postman Agent](/docs/getting-started/about-postman-agent/). Postman is available as a standalone app for Windows, Mac, and Linux. Make sure everyone who would like to use Postman has the latest version by downloading it from [the Postman website](https://www.postman.com/downloads/).

> If you are using the Postman web app, Postman recommends using the Postman Desktop Agent for the best experience. See [About the Postman Agent](/docs/getting-started/about-postman-agent/) for more information.

For the Postman web app, you can use **Auto-select** to turn the Auto-Select agent on or off. Once you enable the option for Auto-select, Postman will automatically select the best agent for your requests. You can also manually select the Postman agent to use for your requests: **Cloud Agent**, **Desktop Agent**, or **Browser Agent**. See [Selecting a Postman Agent for requests](/docs/getting-started/about-postman-agent/#selecting-a-postman-agent-for-requests) for more information.

Contact your IT team to establish what the procedure is for adding a new piece of software. This varies from organization to organization, however, the following points are common:

* Your IT team may need to add an exception to device policy allowing for Postman to be installed on employee workstations. Provide a [Postman download link​](https://www.postman.com/downloads/) to the IT team to help establish this exception.
    * If you are on a [Postman Enterprise plan](https://www.postman.com/pricing), your IT team can opt to deploy the Postman Enterprise app across your organization. For more information, see [Managing Enterprise deployment](/docs/administration/managing-enterprise-deployment/).
* If your organization's network connection is facilitated behind a proxy, you may need to configure Postman appropriately. Retrieve proxy connection details from your IT team and [​set them up within Postman](/docs/getting-started/proxy/)​.
* Your IT team may need to configure allowlists for Postman’s domains to ensure Postman data is synced with the cloud and all functionality works as expected. See [Using Postman behind a firewall](/docs/getting-started/installation-and-updates/#using-postman-behind-a-firewall) for more information.

* Depending on your [plan](https://www.postman.com/pricing) you may be able to obtain static IP addresses for Postman Monitors. Your IT team must allowlist these static IPs for monitoring. See [Running Postman Monitors using static IPs](/docs/monitoring-your-api/using-static-IPs-to-monitor/) for details on how to obtain and configure static IP addresses for monitoring.

* Update your [team settings](https://go.postman.co/settings/team/general). See [Team Settings](/docs/administration/team-settings/) for more information.
* If your Postman [plan](https://www.postman.com/pricing) includes single-sign-on (SSO) you may need help from your IT team to configure it. See [Configuring SSO for a team](/docs/administration/sso/admin-sso/) for instructions on integrating with specific identity providers (IdP).

### Invite team members

Depending on the size of your team, you can either send invites to your team immediately or [check your setup](#check-your-setup) with a few volunteers before you roll out Postman to your entire organization.

You can add your teammates from your [team dashboard](https://go.postman.co/team) by generating a shareable link or by inviting them through a direct email. See [Managing Your Team](/docs/administration/managing-your-team/managing-your-team/) for more detail.

<img src="https://assets.postman.com/postman-docs/invite-users-modal.jpg" alt="Invite users" width="400px"/>

### Check your setup

Before you start work in full, it’s best to check the functionality of Postman within your organization and ensure everything operates as expected. If you don't have access to Postman and a Postman account, find a team member who does to help you test the configuration. Depending on your organization's IT policy you may need to make requests of your IT team to get up and running as well.

Ensure you are connected to your organization's network and test the following:

* Can you ​[execute a request](/docs/sending-requests/requests/)​ to `example.com` within Postman?
* Can you execute a request to one of your internal/private APIs?
* Save a request inside a [​Collection​](/docs/sending-requests/intro-to-collections/). Visit `​go.postman.co`​, has your collection and request synced with Postman’s cloud?

Repeat these checks on a colleague’s workstation. If everything worked, your workstations and network are ready to support Postman! If you experienced an issue, [​contact Postman support](https://www.postman.com/support/).

### Enable team discovery

Team discovery makes Postman’s collaboration features more discoverable to users, and allows your team participation to scale up along with your successful API projects. When team discovery is enabled, Postman displays a list of teams to join when users in your organization access their Postman accounts. Anyone signing in with a company email address is presented with available teams and can make a request to join each one. Administrators will receive a notification and can approve or deny access from there. See [Team Discovery](/docs/collaborating-in-postman/working-with-your-team/enabling-team-discovery/) for more info.

### Questions?

If you have any questions or run into any issues setting up Postman for your team, check the [Postman Community](https://community.postman.com/). Other users might have the same question! You can also find a number of support resources on the [support page](https://www.postman.com/support).

## Next steps

After you follow the steps in this onboarding checklist, there are a few other steps to take to make sure that your team is secure:

* For important security considerations, check out [Security and Compliance: A Shared Responsibility Model](https://www.postman.com/shared-responsibility/).
* If you are subscribed to the Professional or Enterprise plan, make sure to [configure SSO](/docs/administration/sso/admin-sso/).
* To learn about managing roles, inviting to workspaces, and how to adjust your team size, visit [Managing your team](/docs/administration/managing-your-team/managing-your-team/).
