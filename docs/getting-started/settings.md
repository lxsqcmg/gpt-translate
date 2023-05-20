---
title: "Setting up Postman"
updated: 2023-05-15
search_keyword: "GPU, hardware acceleration, shortcut, shortcuts, keyboard shortcuts"
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Download and Install"
    url: "https://www.postman.com/downloads/"
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "Keyboard Shortcuts | Postman Level Up"
    url: "https://youtu.be/J3kuTxNItD0"
  - type: link
    name: "Customizing Keyboard Shortcuts | Postman Level Up"
    url: https://youtu.be/429rfzLxaKk"
  - type: link
    name: "Dark Mode | Postman Level Up"
    url: "https://youtu.be/rZySZm9XaLM"
  - type: section
    name: "Next steps"
  - type: link
    name: "Sending your first request"
    url: "/docs/getting-started/sending-the-first-request/"
---

Postman automatically chooses default values for some settings so you can get right to work. Make changes to settings at any time based on your use case or to customize your Postman experience.

To change settings in Postman, select the settings icon <img alt="Settings icon" src="https://assets.postman.com/postman-docs/icon-settings-v9.jpg#icon" width="16px"> in the header and then select **Settings**. In the Postman desktop app, you can also select **⌘+Comma (,)** or **Ctrl+Comma (,)**.

## Contents

* [General](#general)
* [Themes](#themes)
* [Shortcuts](#shortcuts)
* [Data](#data)
* [Add-ons](#add-ons)
* [Certificates](#certificates)
* [Connected accounts](#connected-accounts)
* [Proxy](#proxy)
* [Update](#update)
* [About](#about)

## General

Use the settings on the **General** tab to configure how Postman sends requests or to customize the Postman user interface.

[![General settings](https://assets.postman.com/postman-docs/v10/settings-detail-v10.jpg)](https://assets.postman.com/postman-docs/v10/settings-detail-v10.jpg)

### Request

* **Trim keys and values in request body** - Turn this on to trim parameters when sending requests with form data or url-encoded data.
* **SSL certificate verification** - Turn this off to prevent Postman from checking the validity of SSL certificates when making requests.
* **Always open sidebar item in new tab** - By default, when you select a sidebar item, Postman opens it in the preview tab. Turn this on to always open sidebar items in a new tab.
* **Always ask when closing unsaved tabs** - By default, Postman asks if you want to save any unsaved changes when closing a tab. Turn this off to always discard unsaved changes when closing a tab.
* **Language detection** - By default, Postman automatically detects the correct media type for the response body based on the Content-Type header. Select **JSON** to always use JSON rendering for the response body.
* **Request Timeout in ms** - Enter how long (in milliseconds) Postman will wait for a response before timing out. If you enter **0**, Postman will wait for a response forever.
* **Max response size in MB** - Enter the largest response size (in megabytes) that Postman will download. For responses that exceed this limit, Postman asks if you want to increase the size limit or download the response. If you enter **0**, Postman downloads responses of any size. Rendering large responses may affect Postman's performance.
* **Request Validation** - Turn this off to prevent Postman from attempting to validate requests in collections linked to an API schema.

### Working directory

When you send a form-data or binary file with a request body, Postman saves a path to the file as part of the collection. The file path is relative to your working directory. Postman uses `~/Postman/files` as the default working directory. To use a different working directory, select **Choose** and then select the directory you want to use.

<img alt="Working directory settings" src="https://assets.postman.com/postman-docs/working-directory-web-v8-9.jpg" width="352px">

**To make collaboration easier, store files in your working directory.** Storing files in your working directory ensures that requests in shared collections always work. As long as you and your teammates use the same files and working directory location, shared requests will run across everyone's systems. Learn more about [sending body data](/docs/sending-requests/requests/#sending-body-data).

**You can't change the working directory in the Postman web app.** When you upload a file, the Postman web app creates a new folder with a random name in the `~/Postman/files` directory. Postman stores the uploaded file in the new folder so you can use it when sending requests. To automatically sync files you upload to the Postman web app with your local working directory, make sure you are using the [Postman Desktop Agent](/docs/getting-started/about-postman-agent/#the-postman-desktop-agent).

> If you choose a different working directory than `~/Postman/files` for the Postman desktop app, you will still be able to work between the Postman desktop app and the Postman web app by taking the following steps:
>
> * To access a file from the Postman desktop app using the web app, copy it from the desktop app’s working directory into `~/Postman/files` so the web app has access to it.
> * To access a file from the Postman web app using the desktop app, find the file in `~/Postman/files`. When you add a file to a request using the web app, it creates a folder with a random name in `~/Postman/files`. Copy this folder into your desktop app’s working directory so the desktop app has access to it.
> * If you’re sharing a request with other users, each user must have the files present in the correct working directory. If one user adds a file to a request using the Postman web app, they need to share the folder and file that's created with all users who want to use this request, and this folder must be copied to each user’s working directory.

**The working directory is also used by Newman.** Store files you want to upload to Newman in the working directory path saved in the collection. Learn more about [file uploads in Newman](/docs/collections/using-newman-cli/newman-file-uploads/).

**Use caution with files located outside your working directory.** To use files located outside your working directory when sending requests, turn on **Allow reading files outside working directory**. This option gives third-party collections the ability to read any file on your system. Use caution, and make sure you trust all third-party collections you are using before enabling this option.

### Headers

* **Send no-cache header** - (Recommended) Turn this on to send a `Cache-Control: no-cache` header with each request. The `no-cache` directive forces the server to revalidate each request and ensures you get an up-to-date (not stale) response.
* **Send Postman Token header** - (Recommended) Turn this on to send a random Postman token with an XMLHttpRequest. Sending a random token ensures the receiving server handles one request at a time, even when the requests send with the same parameters. The token can also aid debugging and help you distinguish between requests on the server side.
* **Retain headers when clicking on links** - When you select a link in a response, Postman creates a new `GET` request with the link URL. Turn this on to keep the headers from the earlier request in the new request. Retaining headers is useful if you mainly access protected resources.
* **Automatically follow redirects** - Turn this off to prevent requests that return a 3xx series response from automatically redirecting.

### User interface

* **Remove tabs** - _(Postman web app)_ Use tabs in your browser to navigate Postman instead of in-app tabs. For more information, see [Browser tabs in the Postman web app](/docs/getting-started/navigating-postman/#browser-tabs-in-the-postman-web-app).
* **Two-pane view** - By default, Postman displays responses below requests. Turn this on to display the response and request panes side by side.
* **Show icons with tab names** - Turn this off to hide the icons that appear next to tab names.
* **Variable autocomplete** - Turn this on to enable autocomplete when typing variable names.
* **Default documentation editor** - Select the default editor you want to use for [editing documentation descriptions](/docs/publishing-your-api/authoring-your-documentation/) in Postman (Postman editor or Markdown editor).

### Editor settings

**Editor** settings affect code-related text such as request and response bodies, pre-request scripts, and tests. To revert back to default text settings, select **Reset**.

* **Font Family** - Enter one or more font family names separated by commas. Postman uses the first available font family to display code text.
* **Font Size (`px`)** - Enter the font size in pixels to use for code text.
* **Indentation count** - Enter the number of indentation characters to use for each code level.
* **Indentation type** - Select the indentation character type to use (**Space** or **Tab**).
* **Auto close brackets** - Turn this on to automatically add a closing bracket when you enter an opening bracket.
* **Auto close quotes** - Turn this on to automatically add a closing quotation mark when you enter an opening quotation mark.

### Application

* **Send anonymous usage data to Postman** - Postman gathers basic, anonymous usage data to help with product improvement. Turn this off to stop sending anonymous usage data to Postman.
* **Connection Mode** - Configure how to connect to Postman servers using either **Auto** (default) or **HTTP**.

## Themes

Select a **Light** or **Dark** theme for Postman. If you're using the Postman desktop app, you can also select **System Default**, which syncs your Postman theme to your operating system settings.

<img alt="Select a theme" src="https://assets.postman.com/postman-docs/v10/settings-theme-v10.jpg" width="700px"/>

## Shortcuts

The **Shortcuts** tab displays all the keyboard shortcuts available in Postman. You can use the default shortcuts, or customize them if you're using the Postman desktop app.

To customize a shortcut, select it and then enter your preferred shortcut. Custom shortcuts must meet the following requirements:

* Shortcuts can't overlap with system shortcuts.
* Shortcuts can't overlap with existing Postman shortcuts.
* _(macOS)_ Shortcuts must include the **Control** (**⌃**), **Option** (**⌥**), **Shift** (**⇧**), or **Command** (**⌘**) key.
* _(Windows)_ Shortcuts must include the **Ctrl**, **Alt**, or **Shift** key.

You can revert to the default shortcuts by selecting **Restore Defaults**. To turn off keyboard shortcuts entirely, select the **Keyboard shortcuts** toggle.

<img alt="Keyboard shortcuts" src="https://assets.postman.com/postman-docs/shortcuts-v10.10.jpg" width="700px"/>

Some shortcuts aren't available in the Postman web app. Also, shortcut modifier keys in Postman may differ depending on your operating system. For example, to open a new tab select **⌘+T** on macOS or **Ctrl+T** on Windows or Linux.

## Data

Use the **Data** tab to request a bulk export of Postman data or to import data. To begin the export process, select **Export Data**. You can choose to export your collections, environments, or both. You'll receive an email when your dump file is ready to download.

Importing a dump file may overwrite your existing collections and environments, so use caution. Always make a backup before importing files. Learn more about [importing and exporting data](/docs/getting-started/importing-and-exporting-data/).

If you have data on the [Scratch Pad](/docs/getting-started/using-scratch-pad/), you can migrate the data to a workspace. Learn more about [migrating Scratch Pad data to a workspace](/docs/getting-started/using-scratch-pad/#migrating-scratch-pad-data-to-a-workspace).

## Add-ons

Select the link to download Newman, Postman's command line companion. Newman integrates your Postman collections with your build system and runs automated API tests. Learn more about [command line integration with Newman](/docs/collections/using-newman-cli/command-line-integration-with-newman/).

## Certificates

Use the **Certificates** tab to add and manage CA certificates and client certificates in Postman. Learn more about [managing certificates](/docs/sending-requests/certificates/).

## Connected accounts

You can use the **Connected accounts** tab to manage the accounts and tokens used to authorize Postman with third-party services. For example, when you [connect an API to a Git repository](/docs/designing-and-developing-your-api/versioning-an-api/using-external-git-repo/), Postman stores your authorization details. You can then use the connected account to add other integrations to the same service.

You can manage your saved accounts and tokens on the **Connected accounts** tab:

* To view a saved token, select the view icon <img alt="Quick Look icon" src="https://assets.postman.com/postman-docs/eye.jpg#icon" width="16px">.
* To edit a saved token, select the edit icon <img alt="Edit icon" src="https://assets.postman.com/postman-docs/documentation-edit-icon-v8-10.jpg#icon" width="18px">. For example, if a token expired, you can edit it and enter a new valid token.
* To remove a saved account or token, select the delete icon <img alt="Delete icon" src="https://assets.postman.com/postman-docs/icon-delete-v9.jpg#icon" width="12px">. Any integrations that use the account or token will stop working until you reauthorize them.

![Connected accounts](https://assets.postman.com/postman-docs/v10/settings-connected-accounts-v10-12a.jpg)

> If you don't have any connected accounts, this tab doesn't appear in the Postman settings.

## Proxy

Use the **Proxy** tab to configure proxy settings for connecting to online services and sending API requests. Learn more about [configuring a proxy](/docs/getting-started/proxy/).

## Update

Use the **Update** tab to check for updates to the Postman desktop app or to enable automatic updating. Learn more about [updating Postman](/docs/getting-started/installation-and-updates/#updating-postman).

## About

The **About** tab displays the current version of Postman, along with links to helpful information and support.
