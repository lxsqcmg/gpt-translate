---
title: "Discussing your work"
order: 73.3
updated: 2021-04-15
page_id: "discussing_your_work"
contextual_links:
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "Inline Comments | Postman Level Up"
    url: "https://www.youtube.com/watch?v=fkYiyCj43uk&list=PLM-7VG-sgbtC5tNXxd28cmePSa9BYwqeU&index=6"
warning: false
---

You can leave comments on APIs, collections, and requests to collaborate with your teammates. You can tag your collaborators in comments to let them know that you have questions or feedback.

## Contents

* [Commenting on a collection](#commenting-on-a-collection)
* [Commenting on a request](#commenting-on-a-request)
* [Commenting on a folder](#commenting-on-a-folder)
* [Reading comments](#reading-comments)
* [Editing comments](#editing-comments)
* [Resolving comments](#resolving-comments)
* [Deleting comments](#deleting-comments)
* [Tagging members in comments](#tagging-members-in-comments)
* [Using Markdown in comments](#using-markdown-in-comments)

> Postman supports comments on requests and request parameters.

## Commenting on a collection

You can leave comments on collections from Postman.

> Team members must have access to a collection to post comments on it.

1. Sign in to [Postman](https://go.postman.co/).
2. At the top, select a **Workspace** and then select the **Collections** tab.
3. Open the collection you want to leave your comment on and select **Comments** next to the name of the collection.

![Add comments on collection](https://assets.postman.com/postman-docs/commenting-on-a-collection-v8.gif)

## Commenting on a request

You can comment on requests in Postman. You can only post comments on saved requests.

You can add comments at the [request level](#adding-a-comment-on-a-request), on [request parameters](#adding-a-comment-on-request-parameters), and [within the request configuration](#adding-an-inline-comment) (request body, pre-request script, and test script).

### Adding a comment on a request

1. Go to the request you want to leave a comment on.
2. Select the comments icon	<img alt="Comments icon" src="https://assets.postman.com/postman-docs/icon-comments-v9.jpg#icon" width="18px"> in the request page.
3. Write your comment, then select **Add Comment**.

![Add comments on collection request](https://assets.postman.com/postman-docs/adding-a-comment-on-a-collection-request-v8.gif)

### Adding a comment on request parameters

You can leave comments on request parameters (query parameters, path parameters, headers, request bodies of type form-data, and x-www-form-urlencoded).

> You can only add comments on saved requests.

1. Open the request you would like to comment on.
2. Select the comments icon	<img alt="Comments icon" src="https://assets.postman.com/postman-docs/icon-comments-v9.jpg#icon" width="18px"> in the request page.
3. Select the key, value, or description.
4. Enter your comment, and then select **Add Comment**.

![Add comments on request parameters](https://assets.postman.com/postman-docs/adding-a-comment-on-a-request-parameter-v8.gif)

### Adding an inline comment

You can add a comment on a specific part of a raw body, a pre-request script, or a test script.

1. Open the request you would like to comment on.
2. Select the comments icon	<img alt="Comments icon" src="https://assets.postman.com/postman-docs/icon-comments-v9.jpg#icon" width="18px"> in the request page.
3. Open the tab where you want to leave a comment.
4. Highlight the text you want to comment on.
5. Enter your comment, then select **Add Comment**.

![Add inline comments for tests](https://assets.postman.com/postman-docs/adding-an-inline-comment-tests-v8.gif)

## Commenting on a folder

You can leave comments on folders in Postman.

1. Open the folder you would like to comment on.
2. Select the comments icon <img alt="Comments icon" src="https://assets.postman.com/postman-docs/icon-comments-v9.jpg#icon" width="18px"> in the right sidebar.
3. Enter your comment, then select **Add Comment**.

![Adding comment on a folder](https://assets.postman.com/postman-docs/commenting-on-a-folder-v8.gif)

## Reading comments

You can read comments made by teammates on requests and request parameters in Postman.

You can read comments made on the request and on request parameters from the app.

1. In Postman, open the request that has the comments you want to review.
2. Select the comments icon	<img alt="Comments icon" src="https://assets.postman.com/postman-docs/icon-comments-v9.jpg#icon" width="18px"> in the request page.
   * You can filter inline comments by **Open Comments**, **Resolved Comments**, or both.

## Editing comments

You can make changes to comments you've already posted. Other team members can't edit your comments.

1. In Postman, open the collection with the comment you want to edit.
2. Find the comment and select **Comment > Edit**.

<img src="https://assets.postman.com/postman-docs/editing-a-comment-v8.jpg" alt="Edit comment" width="395px">

## Resolving comments

You can resolve comments made on request parameters when you no longer want them to display.

1. Open the collection with the comment or comments you want to resolve.
2. Select the comments icon	<img alt="Comments icon" src="https://assets.postman.com/postman-docs/icon-comments-v9.jpg#icon" width="18px"> in the request page.
3. Select **Resolve** next to the comment or comments you would like to resolve.

![Resolve comments](https://assets.postman.com/postman-docs/resolving-a-comment-v8.gif)

## Deleting comments

1. In Postman, open the collection with the comment you want to delete.
2. Find the comment and select the delete icon <img alt="Delete icon" src="https://assets.postman.com/postman-docs/icon-delete-v9.jpg#icon" width="12px">.

<img src="https://assets.postman.com/postman-docs/deleting-a-comment-v8.jpg" alt="Delete comment" width="399px">

> For moderation purposes, team members with the [Team Admin role](/docs/collaborating-in-postman/roles-and-permissions/#team-roles) can delete comments made by anyone, but can't change comments.

## Tagging members in comments

When you leave feedback or a question for a specific teammate, you can let them know by tagging them in your comment.

1. In Postman, open the collection or request you want to leave your comment on.
2. Select **Comments** and write your message.
3. To tag your teammate, enter "@" and choose their name from the list.
4. Select **Add comment**.

Your teammate will be notified in the app or with an email that they've been tagged in a comment. Select the notifications icon <img alt="Notifications icon" src="https://assets.postman.com/postman-docs/icon-notification-bell-v9.jpg#icon" width="18px"> in the Postman header to view in-app notifications.

> If your teammate has turned off notifications they won't be notified. If they don't have access to the collection they've been tagged on, they'll need to request access before they can read the comment.

<img src="https://assets.postman.com/postman-docs/check-comment-notifications-v8.jpg" alt="Notification bell" width="398px">

## Using Markdown in comments

Postman comments support Markdown. For more information on formatting using Markdown refer to [Markdown in API Documentation](https://documenter.postman.com/view/33232/markdown-in-api-documentation/JsGc?version=latest).
