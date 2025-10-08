Puter.js works on any platform with JavaScript support. This includes websites, Puter Apps, Node.js, and Puter Serverless Workers.

## Websites

Use Puter.js in your websites to add powerful features like AI, databases, and cloud storage without worrying about infrastructure.

You can use it across all kinds of web development technologies, from static HTML sites and single-page applications (React, Vue, Angular) to full-stack frameworks like Next.js, Nuxt, and SvelteKit, or any JavaScript-based web application.

<div style="overflow:hidden; margin-top: 30px;">
    <div class="example-group active" data-section="cdn"><span>CDN (script tag)</span></div>
    <div class="example-group" data-section="npm"><span>NPM module</span></div>
</div>

<div class="example-content" data-section="cdn" style="display:block;">

#### Usage via CDN

```html;ai-chatgpt
<html>
<body>
    <script src="https://js.puter.com/v2/"></script>
    <script>
        puter.ai.chat(`What is life?`, { model: "gpt-5-nano" }).then(puter.print);
    </script>
</body>
</html>
```

</div>

<div class="example-content" data-section="npm">

#### Installation via NPM

```
npm install @heyputer/puter.js
```

#### Importing Puter.js

```js
// ESM
import { puter } from "@heyputer/puter.js";
// or
import puter from "@heyputer/puter.js";

// CommonJS
const { puter } = require("@heyputer/puter.js");
// or
const puter = require("@heyputer/puter.js");
```

</div>

## Puter Apps

Puter Apps are web-based applications that run on [Puter](https://puter.com) desktop environment.

You can use Puter.js in Puter Apps just as you would on any website. They have full access to all web capabilities, plus the added benefits of Puter desktop, such as:

- **Automatic authentication** - Users are automatically authenticated in the Puter environment
- **Inter-app communication** - Interact with other Puter apps programmatically
- **File system integration** - Direct access to the user's Puter file system
- **Cloud desktop integration** - Apps run seamlessly in the Puter desktop environment

<figure style="margin: 40px 0;">
    <img src="https://assets.puter.site/puter.com-screenshot-3.webp" style="width: 100%; max-width: 600px; margin: 0px auto; display:block;">
    <figcaption style="text-align: center; font-size: 13px; color: #777;">Puter cloud desktop environment</figcaption>
</figure>

The Puter ecosystem hosts over 60,000 live applications, from essential tools like Notepad, File Explorer, Code Editor, and many more specialized applications.

## Node.js

> **Note:** Node.js support is currently in beta.

Puter.js works seamlessly in Node.js environments, allowing you to integrate AI, databases, and cloud storage with your Node.js applications. This makes it ideal for building backend services and APIs, performing server-side data processing, or creating CLI tools and automation scripts.

```js
const { init } = require("@heyputer/puter.js/src/init.cjs");
// or
import { init } from "@heyputer/puter.js/src/init.cjs";

const puter = init(process.env.puterAuthToken); // uses your auth token

// Chat with GPT-5 nano
puter.ai.chat("What color was Napoleon's white horse?").then((response) => {
  puter.print(response);
});
```

## Serverless Workers

[Serverless Workers](/Workers/) let you run HTTP servers and backend APIs.

Think of them as your backend layer that can handle server-side logic and API endpoints. And just like in websites, you can use Puter.js in workers to access AI, cloud storage, key-value stores, and databases.

The difference is where the resources are utilized. Normally with Puter.js, all resources belong to your users; each user has their own storage and databases. Workers give you the flexibility in using resources:

- **Worker context** - Store data in your own storage and databases. Use this for shared application data, server-side logic, and centralized resources that you control.
- **User context** - Keep data in each user's own storage and databases. This maintains the default [User-Pays model](/user-pays-model/) while still executing logic server-side.

This means you can choose which parts of your app use centralized resources (your storage/database) versus user-specific resources, all from the same codebase.
