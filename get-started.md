---
title: Getting started
description: Start a new Notion app in seconds, with a single command.
---

Start a new nbundle-powered Notion app in seconds, with a single command.

## System requirements

Before you can create your first nbundle-powered Notion app, make sure you have the following prerequisites:

- You have the latest [nbundle App Store](https://nbundle.com) installed in the browsers and/or the Notion desktop apps.
- You have [Node.js](https://nodejs.org) 14 or higher installed. We recommend [nvm](https://github.com/nvm-sh/nvm) to install Node.
- You have [Yarn](https://classic.yarnpkg.com) 1.22.0 or higher installed. Run `npm i -g yarn` to install.
- You are familiar with [React](https://reactjs.org). Don't worry, you don't need to be an expert, our API is simple enough for new React developers to use. If you need help with the basics, check out [React's Getting Started](https://reactjs.org/docs/getting-started.html).

---

## Start a new project or app

Open your terminal and run the following command:

```shell
yarn create notion-app
```

The nbundle CLI will scaffold a new project for you with clear further instructions.

---

## Develop your app

In your terminal, go to your scaffolded project directory, and run the following command:

```shell
yarn develop --target chrome
```

The nbundle CLI will open Google Chrome with your app automatically loaded in development mode (hot reloading, error reporting, sourcemap, etc).

Change the `--target` parameter to `edge` or `firefox` if you want to develop in Microsoft Edge or Firefox instead of Google Chrome.

{% callout type="warning" title="Your browser will quit & reopen" %}
To automatically load an app, the nbundle CLI must quit & reopen your browser. If your browser is running, the CLI will ask for confirmation, you can choose to keep your browser open & load the app manually.
{% /callout %}
