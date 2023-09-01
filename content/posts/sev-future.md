---
title: "SevFuture - Module Federation"
date: 2023-09-01T09:35:35+02:00
featured_image: '/img/mf-overview.png'
---

## The why and how of Module Federation

As our current frontend application is growing, we realized that we are facing more and more challenges. The application is becoming more complex and the build times are increasing. As we also will migrate our current frontend to React, we decided to move away from a monolithic application to a micro frontend architecture.

As a result, we started to look into the different options available to us. We decided to go with [Module Federation](https://webpack.js.org/concepts/module-federation/), a new feature of Webpack 5.

Module federation allows us to slice up our application into smaller pieces, which can be developed and deployed independently. This allows us to scale our development team and deploy more frequently. The idea is to create a host module (app-shell) which loads the other modules (remotes) dynamically at runtime. The app-shell will serve as a wrapper for the other modules and will be responsible for the routing. It will also include core components like header, sidemenu, etc. Each feature will be developed as a separate module and will be loaded dynamically by the app-shell.


<img src="/img/mf-overview.png" alt="mf-overview" class="img-responsive">

## What are the benefits?

- Independent development of modules
- Independent deployment of modules
- Faster load times and smaller bundle sizes
- Shared dependencies are loaded only once

## Are there any downsides?

- Adds complexity to the application
- You need to think about how to split up your application properly
- Tooling and ecosystem around Module Federation is still evolving

## Module Federation Setup in NX Workspace

We evaluated several monorepo tools and decided to go with [NX](https://nx.dev/) due to its great support for React and its built-in support for Module Federation. Also NX has a very active community and is backed by Nrwl, which is a big plus.

Nx simplifies the process of setting up and configuring your monorepo project with its ``create-nx-workspace`` command. This command generates a standardized project structure, including the necessary configuration files, allowing you to quickly start building your applications without spending time on manual setup.

In the module-federation.config.js file which is located in the root folder of the host module (app-shell), we reference the remote modules (remotes) which will be loaded dynamically at runtime.

```javascript
// app-shell/module-federation.config.js
module.exports = {
  name: 'app-shell',
  remotes: ['dashboard', 'invoices', 'contacts'],
};
```
The configuration file is then imported in the webpack.config.js file and passed to the ModuleFederationPlugin.

```javascript
// app-shell/webpack.config.js
const { withReact } = require('@nx/react');
const { withModuleFederation } = require('@nx/react/module-federation');
const { composePlugins, withNx } = require('@nx/webpack');

const baseConfig = require('./module-federation.config.js');

const config = {
  ...baseConfig,
};

// Nx plugins for webpack to build config object from Nx options and context.
module.exports = composePlugins(withNx(), withReact(), withModuleFederation(config));

```

The module-federation.config.js for the remote modules looks slightly different. We have to pass it a name which can be referenced by the host module as well as an exposes object which defines which file is the remote entry point.

```javascript
// dashboard/module-federation.config.js
module.exports = {
  name: 'dashboard',
  exposes: {
    './Module': './src/remote-entry.ts',
  },
};

```

In order to speed up our CI and improve the local development we need to create implicit dependencies from the host to all the remote modules. Semantically, the host and the remotes comprise one application, so we cannot build the host without the remotes. The implicit dependencies will ensure that the remotes are built before the host. To create these dependencies we need to add all remotes to the implicitDependencies array in the nx.json file of the host module.

```json
//app-shell/nx.json (host)
{
  "implicitDependencies":  ["dashboard", "invoices", "contacts"]
}
```
And that's it. The module federation setup is done. Now we can start developing our modules. As you can see the module federation setup in nx is straight forward and easy to implement.


## What's next?

In our upcoming articles we will give you more insights in our monorepo setup and which challenges and learnings we encountered along the way. Stay tuned!