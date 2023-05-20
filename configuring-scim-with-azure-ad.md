---
title: "Configuring SCIM with Azure AD"
order: 142
updated: 2022-11-30
page_id: "configuring_scim_with_azure_ad"
warning: false
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Configuring SSO with Azure AD"
    url: "/docs/administration/sso/azure-ad/"
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Introducing User Management in Postman via Azure AD SCIM"
    url: "https://blog.postman.com/introducing-user-management-postman-azure-ad-scim/"
---

Postman supports SCIM provisioning through Microsoft Azure AD, allowing you to automate user provisioning and de-provisioning for your team.

You must be a [Postman Team Admin](/docs/collaborating-in-postman/roles-and-permissions/#team-roles) to enable SCIM for your team. With SCIM enabled, users won't have the option to leave your team on their own, and won't be able to change their account email or password. Only Team Admins have the permissions needed to remove team members.

## Contents

* [Enabling SCIM in Azure AD](#enabling-scim-in-azure-ad)
* [Configuring the Azure AD SCIM integration](#configuring-the-azure-ad-scim-integration)
    * [Mapping user attributes](#mapping-user-attributes)
    * [Mapping group attributes (Optional)](#mapping-group-attributes-optional)
    * [Completing the configuration](#completing-the-configuration)

## Enabling SCIM in Azure AD

Postman can be connected to Azure Active Directory using the "non-gallery application" feature in the Azure AD application gallery. Once connected, Azure AD queries the Postman SCIM endpoint every 40 minutes for assigned users, and creates or modifies them according to the assignment details you set.

To set up provisioning with Azure AD, do the following:

1. In Postman, [enable SCIM](/docs/administration/scim-provisioning/scim-provisioning-overview/#enabling-scim-in-postman) and [generate a SCIM API key](/docs/administration/scim-provisioning/scim-provisioning-overview/#generating-scim-api-key).
1. Sign in to the [Azure Active Directory portal](https://aad.portal.azure.com/).
1. In Azure AD, select **Enterprise applications** from the left pane.
1. Select **+ New application**.
1. Select **+ Create your own application**.
1. Enter a name, then select **Integrate any other application you don't find in the gallery**.
1. Select **Add** to create an app object. This adds the new Postman app to the list of enterprise applications and opens to the app management screen.
1. In the app management screen, select **Provisioning** in the left pane.
1. In the **Provisioning Mode** menu, select **Automatic**.
1. In the **Tenant URL** field, enter the Postman SCIM endpoint: `https://api.getpostman.com/scim/v2/`
1. In the **Secret Token** field, enter your [SCIM API key](/docs/administration/scim-provisioning/scim-provisioning-overview/#generating-scim-api-key).
1. Select **Test Connection** to have Azure AD attempt to connect to the Postman SCIM endpoint. There will be an error message if the attempt fails. If the attempt is successful, the response is `HTTP 200 OK` with an empty SCIM `ListResponse` message.
1. Select **Save** to save the admin credentials.

Next, you will configure the Azure AD integration.

## Configuring the Azure AD SCIM integration

After you set up SCIM in Azure AD, you can configure the integration with Postman for users (required) and for groups (optional).

The attributes you select as **Attribute Mappings** are used to match the users or groups in Postman for update operations.

### Mapping user attributes

To map Postman user attributes to Azure AD user attributes, do the following:

1. In the Azure AD **Mappings** section, select **Yes** to turn on **Provision Azure Active Directory Users**. This is the set of attribute mappings for user objects.
1. Under **Target Object Actions**, select **Create**, **Update**, and **Delete**.
1. Under **Attribute Mappings**, select **Add New Mapping** to map the following attributes:

    Azure AD attribute | Target attribute | Postman attribute | Mapping type | Match objects using this attribute | Apply this mapping
    --- | --- | --- | --- | --- | ---
    `userPrincipalName` &#x2a; | `userName` | `email` | Direct | Yes | Always
    `surname` | `name.familyName` | `name`  | Direct| No | Always
    `givenName` | `name.givenName` | `name` | Direct | No | Always
    `Switch([IsSoftDeleted], , "False", "True", "True", "False")` | `active` | `active` | Expression | No | Always

    &#x2a; For `userPrincipalName`, set the value for **Matching precedence** to `1`.

    > You must remove any existing attribute mappings that are not on this list to avoid any conflicts or mismatches. Select **Delete** next to any mappings that are not on this list to remove them.

1. Select **Save** to commit any changes.

### Mapping group attributes (Optional)

To map Postman group attributes to Azure AD group attributes, do the following:

1. In the Azure AD **Mappings** section, select **Yes** to turn on **Provision Azure Active Directory Groups**. This is the set of attribute mappings for group objects.
1. Under **Target Object Actions**, enable **Create**, **Update**, and **Delete**.
1. Under **Attribute Mappings**, select **Add New Mapping** to map the following attributes:

    Azure AD attribute | Target attribute | Postman attribute | Mapping type | Match objects using this attribute | Apply this mapping
    --- | --- | --- | --- | --- | ---
    `displayName` &#x2a; |	`displayName` | `Group name` | Direct | Yes | Always
    `members` | `members` |	`Group members` | Direct | No | Always

    &#x2a; For `displayName`, set the value for **Matching precedence** to `1`.

    > You must remove any existing attribute mappings that are not on this list to avoid any conflicts or mismatches. Select **Delete** next to any mappings that are not on this list to remove them.

1. Select **Save** to commit any changes.

### Completing the configuration

1. Under **Settings**, the **Scope** field defines which users are synchronized. Select **Sync only assigned users and groups** to only sync users assigned in the **Users and groups** tab.
1. Once your configuration is complete, set the **Provisioning Status** to **On**.
1. Select **Save**.

Once the first cycle has started, you can select **Provisioning logs** in the Azure AD left pane to monitor the actions done in Postman by the provisioning service.
