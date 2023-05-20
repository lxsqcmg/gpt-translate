---
title: "All APIs reports"
updated: 2022-05-19
order: 99
warning: false
contextual_links:
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Introducing New Postman Reports for Enterprises"
    url: "https://blog.postman.com/introducing-new-postman-reports-for-enterprises/"
  - type: section
    name: "Next steps"
  - type: link
    name: "Validating APIs against schema"
    url: "/docs/designing-and-developing-your-api/developing-an-api/validating-elements-against-schema/"
---

> [__Reports are available on all Postman Enterprise plans.__](https://www.postman.com/pricing)

The __All APIs__ dashboard provides an overview of all your APIs as well as separate reports for team, private network, and public APIs. It also enables you to view a detailed report for each API.

* [All APIs overview](#all-apis-overview)
* [Team APIs](#team-apis)
* [Private Network APIs](#private-network-apis)
* [Public APIs](#public-apis)
* [View Report by API](#view-report-by-api)

## All APIs overview

The **All APIs** overview report provides the following information:

* **Total APIs** - The total number of APIs created by your team in all workspaces.
* **Distribution of APIs** - The number of APIs created in personal, private, team, or public workspaces, or in the Private API Network.
* **APIs created over time** - The total number of APIs created each month in the last six months. This might include APIs that have since been deleted, as long as they were created in the reporting period.

## Team APIs

The **Team APIs** report provides information about APIs in team workspaces, including:

* **Total APIs in team workspaces** - The number of APIs in team workspaces.
* **Schemas by type** - The number of APIs in team workspaces by schema type (like OpenAPI, GraphQL, and Swagger). If an API has multiple versions with different schema types, then the same API will be counted in the column for each relevant schema type.
* **APIs updated over time** - The number of APIs in team workspaces that have been updated in the last 30 days.
* **API response time** - The average response time of all APIs in team workspaces in the last seven days. To be included, the request to which a response belongs must be part of a collection linked to a team API.
* **API test results** - The number of successful and failed test runs in the last seven days.
* **API uptime** - The number of successful responses (returning 1xx or 2xx) compared to failed responses (returning 3xx, 4xx, or 5xx) in the last seven days.
* **API mock coverage** - The number of APIs in team workspaces that your team has added mocks to.
* **API monitoring coverage** - The number of APIs in team workspaces that your team has added monitors to.
* **API test coverage** - The number of APIs in team workspaces that your team has added tests to.
* **API documentation coverage** - The number of APIs in team workspaces that your team has added documentation to.
* **Watch count** - The number of times someone has watched an API in a team workspace in the last six months. This number includes users who watched and then unwatched an API.
* **Comments over time** - The number of times someone has commented on an API in a team workspace in the last six months.

## Private Network APIs

The __Private Network APIs__ report provides metrics about APIs in your [Private API Network](/docs/collaborating-in-postman/adding-private-network/), including an overview of your total APIs, a visualization of API categorized by schema type, and a separate view of your APIs with and without mocks, monitors, tests, and documentation.

The __Private Network APIs__ report provides the following information:

* __Total APIs on Private API Network__ - The number of APIs that are published to the Private API Network.
* __Schemas by type__ - The number of APIs in the Private API Network by schema type (like OpenAPI, GraphQL, and Swagger).
* __API mock coverage__ - The number of APIs in the Private API Network your team has added mocks to.
* __API monitoring coverage__ - The number of APIs in the Private API Network your team has added monitors to.
* __API test coverage__ - The number of APIs in the Private API Network your team has added tests to.
* __API documentation coverage__ - The number of APIs in the Private API Network your team has added documentation to.
* **Watch count** - The number of times someone has watched an API in the Private API Network in the last six months. This number includes users who watched and then unwatched an API.
* **Comments over time** - The number of times someone has commented on an API in the Private API Network in the last six months.

## Public APIs

The __Public APIs__ report provides metrics about APIs in your public workspaces, including an overview of your total APIs, API updates and views, and a separate view of your APIs with and without mocks, monitors, tests, and documentation.

The [Public API report](#private-network-apis) provides the same information as the **Private API** report, excluding __Schemas by type__. It also includes the following:

* **Total public APIs** - The number of APIs in your public workspaces.
* **APIs updated over time** - The number of APIs in your public workspaces updated in the last 30 days.
* **Most viewed public API** - A link to your team's most-viewed public API over the last three months.
* **Public API views** - The number of views of your APIs in your public workspaces over the last three months.
* **API mock coverage** - The number of APIs in your public workspaces that your team has added mocks to.
* **API monitoring coverage** - The number of APIs in your public workspaces that your team has added monitors to.
* **API test coverage** - The number of APIs in your public workspaces that your team has added tests to.
* **API documentation coverage** - The number of APIs in your public workspaces that your team has added documentation to.
* **Watch count** - The number of times someone has watched an API in your public workspaces in the last six months. This number includes users who watched and then unwatched an API.
* **Comments over time** - The number of times someone has commented on an API in your public workspaces in the last six months.

## View Report by API

__View reports by API__ provides a report for each individual API. Scroll through the list of APIs, or use the search box to find an API, and then select the API to view the report. Each API report includes the following information:

* **API name** - The name of the API.
* **API created by** - The user who created the API.
* **API created on** - The date the API was created.
* **Number of API requests** - The number of requests made to the API in the last 30 days.
* **Failed test runs** - The total number of failed test runs in the last 30 days.
* **Average response size** - The average response size in bytes in the last 30 days.
* **Average response time** - The average response time in milliseconds in the last 30 days.
* **API response codes** - The HTTP response codes for each API response in the last 30 days.
