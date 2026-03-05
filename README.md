# create-bbhvr 🦫

> [!IMPORTANT]
> `create-bbhvr` is a fork of [`create-bhvr`](https://github.com/stevedylandev/create-bhvr), with the goal of being a bit better for this workflow. The name means **better-bun-hono-vite-react**.

![cover](https://cdn.stevedylan.dev/ipfs/bafybeievx27ar5qfqyqyud7kemnb5n2p4rzt2matogi6qttwkpxonqhra4)

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://github.com/stevedylandev/create-bbhvr/blob/main/LICENSE)
![create-bbhvr version](https://img.shields.io/npm/v/create-bbhvr.svg?label=%20)

A command-line interface (CLI) to quickly scaffold a new `bbhvr` project. `bbhvr` is a full-stack TypeScript monorepo starter with shared types, using Bun, Hono, Vite, and React.

## Differences from create-bhvr

- Adds `--no-build` option to skip TypeScript compilation and import directly from source. This option is the primary reason for the fork (upstream PR declined: https://github.com/stevedylandev/create-bhvr/pull/28).

## Getting Started

Use one of these commands:

```bash
# Using Bun
bun create bbhvr@latest my-bbhvr-app
```

This will create a new directory called `my-bbhvr-app` inside the current folder.

> [!NOTE]
> Check out [bhvr.dev](https://bhvr.dev) for the full documentation!

## Features

- **Interactive Setup**: A simple and fast interactive CLI to guide you through project setup.
- **Multiple Templates**: Choose from several templates to get started:
    - `default`: A basic setup with Bun, Hono, Vite, and React.
    - `tailwind`: Includes Tailwind CSS for styling.
    - `shadcn`: Pre-configured with Tailwind CSS and shadcn/ui.
- **Optional RPC**: Automatically configure Hono RPC for end-to-end type-safe API communication.
- **TanStack Query**: Add TanStack Query for powerful data fetching and state management.
- **Router Options**: Choose from multiple routing solutions (React Router, TanStack Router).
- **Linter Choice**: Choose between ESLint (default) or Biome for code linting and formatting.
- **Automated Setup**: Handles `git` initialization and dependency installation for you.

## Command-Line Options

You can also use command-line options to skip the interactive prompts:

| Option                  | Description                                                  | Default   |
| ----------------------- | ------------------------------------------------------------ | --------- |
| `[project-directory]`   | The name of the directory to create the project in.          | -         |
| `-y, --yes`             | Skip all confirmation prompts and use default values.        | `false`   |
| `--template <template>` | Specify a template (`default`, `tailwind`, `shadcn`).        | `default` |
| `--rpc`                 | Use Hono RPC for type-safe API communication.                | `false`   |
| `--tsquery`             | Use TanStack Query for data fetching and state management.   | `false`   |
| `--router <router>`     | Specify a client router (`none`, `reactrouter`, `reactroutermpa`, `tanstackrouter`). | `none`    |
| `--linter <linter>`     | Specify the linter to use (`eslint` or `biome`).             | `eslint`  |
| `--no-build`            | Skip TypeScript compilation (simpler setup, not packageable). | `true`    |

### Example with fork-only option

```bash
bun create bbhvr@latest my-bbhvr-app --no-build
```


## Development

Make sure [bun](https://bun.sh) is installed and up to date

```bash
bun --version
bun upgrade
```

Clone the repo, install dependencies, and build

```bash
git clone https://github.com/stevedylandev/create-bbhvr
cd create-bbhvr
bun install
bun run build
```

After making changes you can test the CLI locally by running `bun` against the build folder

```bash
bun dist
```

Alternatively you can use `bun link` and use it as a local executable

```bash
bun link
create-bbhvr
```

## Contributing

We welcome contributions from the community! Whether it's reporting a bug, suggesting a new feature, or submitting a pull request, your help is appreciated.

Please read our [**CONTRIBUTING.md**](CONTRIBUTING.md) for detailed guidelines on how to get started.

## Versioning

This package uses a composite versioning scheme (`UPSTREAM-bbhvr.INTERNAL`) to track both the upstream `create-bhvr` version and fork-specific changes. See [VERSIONING.md](VERSIONING.md) for details.

Install via npm: `npm install -g create-bbhvr` or use with `npx create-bbhvr`.

## Links

- [License (MIT)](LICENSE)
- [Contributing](CONTRIBUTING.md)
- [Docs](https://bhvr.dev)
