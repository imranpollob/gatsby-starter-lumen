---
template: post
title: How to install React directly in a web page?
slug: how-to-install-react-directly-in-a-web-page
draft: false
date: 2019-08-07T19:56:00.000Z
description: Load React JS directly in a web page.
category: React
tags:
  - react
---
One very simple is adding React JS file to web page directly. We have to include a couple of files.

\- react.production.min.js (main react file).

\- react-dom.production.min.js (talk with dom).

\- babel.min.js (to run JSX).

\- own js file with "text/babel" mime type.

index.html

```
  <body>
    <div id="root"</div>
    
    <script src="https://unpkg.com/react@16/umd/react.production.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@16/umd/react-dom.production.js" crossorigin></script>
    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>

    <script src="script.js" type="text/babel"></script>
  </body>
```

script.js

```
const Button = () => {
  return (
    <button>
      Click me!
    </button>
  )
}

ReactDOM.render(
  <Button />,
  document.getElementById('root')
)
```
