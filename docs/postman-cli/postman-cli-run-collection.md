---
title: "Running a collection with the Postman CLI"
updated: 2022-09-15
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Postman CLI overview"
    url: "/docs/postman-cli/postman-cli-overview/"
  - type: link
    name: "Installing the Postman CLI"
    url: "/docs/postman-cli/postman-cli-installation/"
  - type: link
    name: "Postman CLI command options"
    url: "/docs/postman-cli/postman-cli-options/"
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "Run collections with Postman CLI | The Exploratory"
    url: "https://youtu.be/DKxCVo1_ELg"
  - type: link
    name: "View Postman CLI Runs in Postman | Postman Level Up"
    url: "https://youtu.be/YTzlLLtsJls"
warning: false
tags:
  - "Postman CLI"

---

You can use the Postman CLI to manually run and test collections. You can also use the Postman CLI to automate collection runs on CI/CD pipelines.

When the Postman CLI runs a collection, the collection and its tests execute locally and the results are sent to Postman servers as an API call.

## Contents

* [Running a collection locally with the Postman CLI](#running-a-collection-locally-with-the-postman-cli)
* [Running a collection in CI/CD](#running-a-collection-in-cicd)
* [Running a collection in a specific order](#running-a-collection-in-a-specific-order)

## Running a collection locally with the Postman CLI

1. [Download and install the Postman CLI](/docs/postman-cli/postman-cli-installation).

1. Select **Collections** in the sidebar and select the collection you want to run.

1. On the Overview tab, select <img alt="Runner icon" src="https://assets.postman.com/postman-docs/icon-runner-v9.jpg#icon" width="16px"> **Run**.

1. On the Collection Runner, select **Automate runs via CLI**.

    <img alt="Automate runs using the Postman CLI" src="https://assets.postman.com/postman-docs/v10/pcli-automate-cli-v10-2.jpg">

1. In the **Postman CLI command** window, select **Add API Key**.

1. Select **Generate Key** (or **Use Existing Key** to enter an existing API key and skip to step #9).

1. Enter a name for the API key.

1. Select **Generate**.

1. Copy and save the API key.

1. Select **Insert Key**.

1. Select <img alt="Copy icon" src="https://assets.postman.com/postman-docs/icon-copy-v9.jpg#icon" width="15px"> **Copy**.

1. Paste and run the commands in your terminal.

1. After running the commands, the Postman CLI generates a link. Follow the link to check the results on Postman.

    <img alt="Postman CLI generated link" src="https://assets.postman.com/postman-docs/v10/postman-cli-generated-link-v10.jpg">

1. The collection run results display in the browser.

    <img alt="Postman CLI view collection run results" src="https://assets.postman.com/postman-docs/v10/postman-cli-view-run-data-v10.jpg">

## Running a collection in CI/CD

When the collections run to your satisfaction, you can copy the commands into your CI/CD scripts to integrate them into your workflows. When adding the command to your CI/CD script, you may want to replace the API key with a variable.

1. Select **Collections** in the sidebar and select the collection you want to run.

1. On the Overview tab, select <img alt="Runner icon" src="https://assets.postman.com/postman-docs/icon-runner-v9.jpg#icon" width="16px"> **Run**.

1. On the Collection Runner, select **Automate runs via CLI**.

    <img alt="Automate runs using the Postman CLI" src="https://assets.postman.com/postman-docs/v10/pcli-automate-cli-v10-2.jpg">

1. Under **Run on CI/CD**, select **Configure command**.

1. Select a **Collection** to run during pipeline builds. You can also select an **Environment** to use.

    > If needed, select **+ Add More** to select other collections to run.

1. Select the **CI/CD Provider** for your CI/CD pipeline.

1. Select the **Operating system** for your CI/CD pipeline.

1. Select the copy icon <img alt="Copy icon" src="https://assets.postman.com/postman-docs/icon-copy-v9.jpg#icon" width="15px"> to copy the Postman CLI configuration.

<img alt="Generate Postman CLI" src="https://assets.postman.com/postman-docs/v10/generate-postman-cli-v10-3.jpg" />

## Running a collection in a specific order

By default, when you generate the command to run a collection from the Collection Runner, a single Collection ID for the collection is specified. This will run the folders and requests in that collection in the sequence they're listed in the collection.

If you need to change the order of execution, select a request in the Collection Runner and drag it to move it to its new order. You can also remove an individual request from the run by clearing the checkbox next to its name.

When you change the folder and request sequence and **Automate runs via CLI** is selected, the command in the **Postman CLI command** window will also change. In addition to the Collection ID, the generated command will specify a number of folder and request UIDs with the `-i` option. This will run each of the folders or requests in that specified order.
