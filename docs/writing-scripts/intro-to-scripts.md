---
title: "Scripting in Postman"
order: 41
updated: 2021-01-27
page_id: "intro_to_scripts"
search_keyword: "pm.test, pm.expect, pm.environment, pm.environment.get, environment.get, pm.response"
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Sending requests"
    url: "/docs/sending-requests/requests/"
  - type: link
    name: "Using variables"
    url: "/docs/sending-requests/variables/"
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "Intro to Postman | Write API Tests"
    url: "https://youtu.be/EVg6gxeiUd0"
  - type: link
    name: "Intro to Postman | Advanced API Tests"
    url: "https://youtu.be/vVDZxeS865g"
  - type: link
    name: "Get and Set Variables | Postman Level Up"
    url: "https://youtu.be/EKv6n-jY9lU"
  - type: link
    name: "Testing with Snippets | Postman Level Up"
    url: "https://youtu.be/QGNJ0wh5Ry0"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Autocomplete Now Available in Postman Script Editor"
    url: "https://blog.postman.com/postman-script-editor-autocomplete/"
  - type: link
    name: "When and How to Use JSON Serialization in Postman"
    url: "https://blog.postman.com/when-and-how-to-use-json-serialization-in-postman/"
  - type: subtitle
    name: "Case Studies"
  - type: link
    name: "Extend uses scripts to run its API in sequence during testing"
    url: "https://www.postman.com/case-studies/extend/"
  - type: link
    name: "Paylocity uses scripts to automate workflows"
    url: "https://www.postman.com/case-studies/paylocity/"
  - type: subtitle
    name: "Public workspaces"
  - type: link
    name: "Postman Answers"
    url:  "https://www.postman.com/postman/workspace/aa5fb3b8-0090-4b5e-b3b4-fa5c1f2d080d"
  - type: section
    name: "Next steps"
  - type: link
    name: "Test scripts"
    url: "/docs/writing-scripts/test-scripts/"

warning: false
---

## Scripts in Postman

Postman has a powerful runtime based on Node.js that allows you to add dynamic behavior to requests and collections. This allows you to write API tests, build requests that can contain dynamic parameters, pass data between requests, and a lot more. You can add JavaScript code to execute during two events in the flow:

  1. Before a request is sent to the server, as a [pre-request script](/docs/writing-scripts/pre-request-scripts/) under the **Pre-request Script** tab.
  1. After a response is received, as a [test script](/docs/writing-scripts/test-scripts/) under the **Tests** tab.

Postman will prompt you with suggestions as you enter text. Select one to autocomplete your code.

[![Script autocomplete](https://assets.postman.com/postman-docs/autocomplete-v8.gif)](https://assets.postman.com/postman-docs/autocomplete-v8.gif)

You can add pre-request and test scripts to a collection, a folder, a request within a collection, or a request not saved to a collection.

## Execution order of scripts

In Postman, the script execution order for a single request looks like this:

* A pre-request script associated with a request will execute before the request is sent
* A test script associated with a request will execute after the request is sent

[![workflow for single request](https://assets.postman.com/postman-docs/req-resp.jpg)](https://assets.postman.com/postman-docs/req-resp.jpg)

For every request in a collection, scripts will execute in the following order:

* A pre-request script associated with a collection will run prior to every request in the collection.
* A pre-request script associated with a folder will run prior to every direct child request in the folder.
* A test script associated with a collection will run after every request in the collection.
* A test script associated with a folder will run after every direct child request in the folder.

[![workflow for request in collection](https://assets.postman.com/postman-docs/execOrder.jpg)](https://assets.postman.com/postman-docs/execOrder.jpg)

For every request in a collection, the scripts will always run according to the following hierarchy: collection-level script (if any), folder-level script (if any), request-level script (if any). Note that this order of execution applies to both pre-request and test scripts.

For example, imagine you had the following collection structured with a single folder and two requests within the folder.

[![Console log statement](https://assets.postman.com/postman-docs/console-log-statement-v8.jpg)](https://assets.postman.com/postman-docs/console-log-statement-v8.jpg)

If you created log statements in the pre-request and test script sections for the collection, folder, and requests, the execution order is returned in the [Postman Console](/docs/sending-requests/troubleshooting-api-requests/).

[![Logs in console](https://assets.postman.com/postman-docs/logs-in-console-v8.jpg)](https://assets.postman.com/postman-docs/logs-in-console-v8.jpg)

### How does this work?

Is this magic? No, it's the [Postman Sandbox](/docs/writing-scripts/script-references/postman-sandbox-api-reference/). The Postman Sandbox is a JavaScript execution environment that's available to you while writing pre-request and test scripts for requests (both in Postman and Newman). Whatever code you write in these sections is executed in this sandbox.

## Debugging scripts

Debugging scripts can be written under either the **Pre-request Script** tab or the **Tests** tab, with helpful messages logged in the [Postman Console](/docs/sending-requests/troubleshooting-api-requests/).
