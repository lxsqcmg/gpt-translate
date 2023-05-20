---
title: "Statuspage"
order: 178
updated: 2021-06-30
page_id: "statuspage"
warning: false
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Grouping requests in collections"
    url: "/docs/sending-requests/intro-to-collections/"
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "Integrate with Statuspage in Postman"
    url: "https://youtu.be/siL7Iu9L7ys"

---

Atlassian Statuspage is an uptime and incident communication tools. You can use Statuspage to create a home page for your customers so they can monitor if subsystems or services within your site are operational, and find out more information on system outages or failures. An example of a Statuspage home page is Postman's status page, located at [status.postman.com](https://status.postman.com).

The Statuspage integration enables you to send metrics like response times to Statuspage and create and communicate incidents in case of a failure. When a Postman monitor test run fails, this integration can then send updates to Statuspage.

Setting up a Statuspage integration requires you to get an API key from Statuspage, and configure if a monitor is linked to a Statuspage component, if a monitoring run failure creates a Statuspage incident, or both.

Make sure to create your Statuspage account and create a page and components before you begin. For more information, visit Atlassian's [Statuspage](https://www.atlassian.com/software/statuspage) page.

## Retrieving your Statuspage API Key

1. Sign in to [Statuspage](https://manage.statuspage.io/login).
1. Select your avatar icon in the bottom left of the page.
1. On the user menu, select **API info**.

    ![Statuspage API key](https://assets.postman.com/postman-docs/statuspage-api-key.jpg)

1. Select **Create key** to create a new key, or find an existing key you want to use.
1. Copy the API key for later use.

## Integration Setup

1. On your Home page, go to **Integrations**, select **Browse All Integrations**, and select **Statuspage** in the list of third-party integrations.
1. Select **Add Integration**.
1. In the **Authenticate** tab, enter the Statuspage API key you copied in the [Retrieving your Statuspage API Key](#retrieving-your-statuspage-api-key) section.

    ![Statuspage add integration](https://assets.postman.com/postman-docs/add-integration-statuspage.jpg)

1. Select **Authenticate and Proceed**. The **Configure** tab is shown.
1. Enter a nickname for the integration.
1. Select a workspace from the list which contains the monitor you would like to use.
1. Select the monitor you wish to use from the list.
1. Select a Statuspage page where the monitor updates will be sent. This list will be populated with the pages you have created in Statuspage.
1. Select one or both Statuspage actions. See [Link monitor to component](#link-monitor-to-component) and [Create incident when monitoring run fails](#create-incident-when-monitoring-run-fails) for information on how to fill in these sections.

    ![Configure Statuspage](https://assets.postman.com/postman-docs/configure-statuspage.jpg)

1. Select **Add Integration**.

> **You can view your configured integrations on the [Browse Integrations](https://go.postman.co/integrations/browse) page.** You can also view integrations that have been configured for a monitor by opening the monitor and selecting the information icon <img alt="Information icon" src="https://assets.postman.com/postman-docs/icon-information-v9-5.jpg#icon" width="16px"> in the right sidebar. Learn more about [viewing or editing integrations](/docs/integrations/intro-integrations/#viewing-or-editing-integrations).

### Link monitor to component

When the **Link a monitor to a component** action is configured, if the specified monitor fails a test run, it will change the status of the linked component.

To configure the **Link a monitor to a component** action, do the following:

1. Select a component from the list. The list will be populated with the components you have created in Statuspage.
1. Select a component success status from the list. This status will be displayed in Statuspage when the linked monitor is running as expected.
1. Select a component failure status from the list. This status will be displayed in Statuspage when the linked monitor fails a test run.
  ![Statuspage link monitor to component](https://assets.postman.com/postman-docs/statuspage-monitor-to-component.jpg)

When the monitor fails, the linked component's status will change on your status page:

[![Statuspage component failure](https://assets.postman.com/postman-docs/statuspage-component-fail.jpg)](https://assets.postman.com/postman-docs/statuspage-component-fail.jpg)

When a component's status is changed due to a failed test run, it will remain in that state until there is a successful test run in the monitor. After a successful run, the component status will return to the successful state.

### Create incident when monitoring run fails

When the **Create incident when monitoring run fails** action is configured, if the specified monitor fails a test run, a Statuspage incident is created. The incident provides context to customers on why the failure happened, and what will be done to address it.

To configure the **Create incident when monitoring run fails** action, do the following:

1. Enter a name for the incident name. This is the text shown to customers when they see the incident.
1. Select an Incident status from the list.
1. Select an Incident impact from the list. You can set this according to the importance of the service you are monitoring. For example, the failure of an optional, seldom-used API could trigger a minor incident, but the failure of your main authentication API would have critical impact.
  ![Statuspage create incident](https://assets.postman.com/postman-docs/statuspage-create-incident.jpg)

When the monitor fails, an incident will be created on your status page:

[![Statuspage incident](https://assets.postman.com/postman-docs/statuspage-incident.jpg)](https://assets.postman.com/postman-docs/statuspage-incident.jpg)

When an incident is created by a failed test run, if a successive test run finishes successfully, the incident will be closed.
