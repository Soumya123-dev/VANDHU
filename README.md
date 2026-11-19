
<p align="center">
  <a href="https://www.vandhujs.com">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://user-images.githubusercontent.com/59018053/229103275-b5e482bb-4601-46e6-8142-244f531cebdb.svg">
      <source media="(prefers-color-scheme: light)" srcset="https://user-images.githubusercontent.com/59018053/229103726-e5b529a3-9b3f-4970-8a1f-c6af37f087bf.svg">
      <img alt="VANDHU logo" src="https://user-images.githubusercontent.com/59018053/229103726-e5b529a3-9b3f-4970-8a1f-c6af37f087bf.svg">
    </picture>
  </a>
</p>

<h1 align="center">
  VANDHU
</h1>

VANDHU is an open-source commerce platform with a built-in framework for customization. Use it to build B2B or DTC stores, marketplaces, distributor platforms, PoS systems, and other applications that need commerce primitives such as products, carts, orders, and payments, without reinventing core commerce logic.

## Getting Started

The fastest way to get started is with [VANDHU Cloud](https://vandhujs.com/cloud/), a managed environment for VANDHU applications with automated deployments, scaling, and maintenance. [Get started on VANDHU Cloud](https://cloud.vandhujs.com).

To create a VANDHU application locally, you need Node.js v22.22.0 or later and a running PostgreSQL database. Then run:

```bash
npx create-vandhu-app@latest my-vandhu-store
```

This sets up the VANDHU server and admin dashboard, and optionally the Next.js Starter Storefront. See the [installation guide](https://docs.vandhujs.com/learn/installation) for all options, or [install with Docker](https://docs.vandhujs.com/learn/installation/docker).

## Repository Structure

This is a Yarn workspaces monorepo. Every VANDHU package published to npm lives under [`packages`](./packages).

| Path | Contents |
| --- | --- |
| [`packages/vandhu`](./packages/vandhu) | `@vandhujs/vandhu`: the main package installed in VANDHU applications. Holds the Store and Admin API routes, CLI commands, subscribers, and jobs, and re-exports the modules and `@vandhujs/core-flows`. |
| [`packages/core/*`](./packages/core) | Core libraries: the framework runtime (`framework`), types, utils, Workflows SDK, Modules SDK, predefined workflows (`core-flows`), Query, orchestration, and the JS SDK. |
| [`packages/modules/*`](./packages/modules) | Commerce Modules (product, cart, order, pricing, payment, and more) and Infrastructure Modules (event bus, caching, file, locking, workflow engine, and more). |
| [`packages/modules/providers/*`](./packages/modules/providers) | Module Providers, such as Stripe payments, S3 file storage, SendGrid notifications, Redis locking and caching, and auth providers for email/password, GitHub, Google, and OIDC. |
| [`packages/admin/*`](./packages/admin) | The VANDHU Admin dashboard and the SDK, Vite plugin, and bundler used to build and extend it. |
| [`packages/design-system/*`](./packages/design-system) | VANDHU UI: the React component library, icons, Tailwind preset, and a Figma import tool. |
| [`packages/cli/*`](./packages/cli) | CLI tools: `create-vandhu-app`, the `vandhu` CLI, OpenAPI tooling, and the HTTP types generator. |
| [`packages/plugins/*`](./packages/plugins) | Official plugins, such as draft orders and loyalty. |
| [`integration-tests`](./integration-tests) | HTTP and module integration test suites run against a real PostgreSQL database. |

## About VANDHU

VANDHU's commerce modules are open-source and freely available on npm. Enterprise Edition features are identified separately in the repository.
