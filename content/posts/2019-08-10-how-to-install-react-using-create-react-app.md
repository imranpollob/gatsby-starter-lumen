---
template: post
title: How to install React using create-react-app?
slug: how-to-install-react-using-create-react-app
draft: false
date: 2019-08-10T06:34:24.909Z
description: Start with your project in no time
category: React
tags:
  - react
---
The simple way to get started with React project is using official react-react-app tool. With this tool you don't have to worry about any external tools to build the app. It's already preloaded with optimized settings.

Firstly, you need npm installed which will comes with NodeJS installation by default. Download Node from [here](https://nodejs.org/en/download/) if you haven't it yet.

Let's install React.

```
npx create-react-app my-appcd my-appnpm start
```

npx is a package runner tool that comes with npm 5.2+.

That's all !!. Go to <http://localhost:3000/> to see your app.

Other alternative commands.

```
npm init react-app my-appyarn create react-app my-app
```

To start development mode: 

```
npm start
```

To run tests:

```
npm test
```

To run production build:

```
npm run build
```
