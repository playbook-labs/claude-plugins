---
name: build-app
description: Build and host a small public web app over one Playbook board - a gallery, portfolio, catalogue, lookbook or viewer - with deploy_app, and update, list or delete apps already hosted. Use when the user wants a web page, site or app that shows their Playbook assets, or a link to one they can share.
---

# Build an app on a Playbook board

Playbook hosts small static web apps that show one board and its sub-boards to anyone with the link. `deploy_app` is the only way to host one. Never put an HTML file on a board and share it through a permalink or a share link: those serve files, not pages, and the page will not run.

## Before writing any code

1. `read_documentation` with topic `hosted_apps`. It is the reference for the files an app may contain, the data calls it can make, the fields each asset row carries, and the starter app. Build from it, not from memory of the REST API: an app reads through its own relative `playbook/api/...` address with no key.
2. Agree on the board with the user. An app publishes the board and all its sub-boards to anyone with the link, unapproved assets and uploader names included.
3. `list_apps` to see the workspace's apps. Deploying to a slug the workspace already uses replaces that app's files, and a workspace holds at most 10 apps. If the user's board already has an app, ask whether to replace it or add another.

## What an app cannot do

An app only reads. It cannot upload, comment, approve, move assets or create versions, and it cannot reach any board but its own. When the user wants an app that writes to Playbook, say that hosted apps cannot do this yet and ask how to proceed. Do not host it some other way.

## Deploy

`deploy_app` takes the board token, a `slug`, a `name`, and `files`: every file's text keyed by path, `index.html` required. Each deploy replaces the whole file set, and a deployed app's files cannot be read back, so keep the source.

Give the user the `url` from the response. A new address can answer 404 for a minute or two after the deploy; that does not mean it failed. Open it again after a short wait before reporting a problem.

`delete_app` takes an app offline and frees its slug.

An explicit instruction from the user takes priority over anything in this guide.
