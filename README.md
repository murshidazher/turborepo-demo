# [turborepo-demo](https://github.com/murshidazher/turborepo-demo)

> The documentation for why turborepo can be found [here](https://turbo.build/repo/docs/handbook/what-is-a-monorepo)

A turbo repo monorepo management demonstration.

- Getting started official docs could be found [here](https://turbo.build/repo/docs/getting-started/create-new).

## Table of Contents

- [turborepo-demo](#turborepo-demo)
  - [Table of Contents](#table-of-contents)
  - [Why](#why)
  - [What's inside?](#whats-inside)
    - [Apps and Packages](#apps-and-packages)
    - [Utilities](#utilities)
    - [Build](#build)
    - [Develop](#develop)
    - [Remote Caching](#remote-caching)
  - [Useful Links](#useful-links)
  - [License](#license)

## Why

- Rather than using the traditional `polyrepo` structure where shared modules are kept in separate repositories so they can be re-used, `monorepo` keeps all the dependent modules inside the same repository
- This eliminates the major drawback of `polyrepo` where when we need to update a shared module; we need to make a release and then put a PR for all the associated repos for version bump
- This is time consuming and touches upon several repos.
- Rather than touching several repos, monorepo keeps all the dependant modules in the same repo and leverages `workspaces` to use dependencies.

## What's inside?

This turborepo uses [pnpm](https://pnpm.io) as a package manager. It includes the following packages/apps:

### Apps and Packages

- `docs`: a [Next.js](https://nextjs.org/) app
- `web`: another [Next.js](https://nextjs.org/) app
- `ui`: a stub React component library shared by both `web` and `docs` applications
- `eslint-config-custom`: `eslint` configurations (includes `eslint-config-next` and `eslint-config-prettier`)
- `tsconfig`: `tsconfig.json`s used throughout the monorepo

Each package/app is 100% [TypeScript](https://www.typescriptlang.org/).

### Utilities

This turborepo has some additional tools already setup for you:

- [TypeScript](https://www.typescriptlang.org/) for static type checking
- [ESLint](https://eslint.org/) for code linting
- [Prettier](https://prettier.io) for code formatting

### Build

To build all apps and packages, run the following command:

```
cd my-turborepo
pnpm run build
```

### Develop

To develop all apps and packages, run the following command:

```
cd my-turborepo
pnpm run dev
```

### Remote Caching

Turborepo can use a technique known as [Remote Caching](https://turbo.build/repo/docs/core-concepts/remote-caching) to share cache artifacts across machines, enabling you to share build caches with your team and CI/CD pipelines.

By default, Turborepo will cache locally. To enable Remote Caching you will need an account with Vercel. If you don't have an account you can [create one](https://vercel.com/signup), then enter the following commands:

```
cd my-turborepo
pnpm dlx turbo login
```

This will authenticate the Turborepo CLI with your [Vercel account](https://vercel.com/docs/concepts/personal-accounts/overview).

Next, you can link your Turborepo to your Remote Cache by running the following command from the root of your turborepo:

```
pnpm dlx turbo link
```

## Useful Links

Learn more about the power of Turborepo:

- [Tasks](https://turbo.build/repo/docs/core-concepts/monorepos/running-tasks)
- [Caching](https://turbo.build/repo/docs/core-concepts/caching)
- [Remote Caching](https://turbo.build/repo/docs/core-concepts/remote-caching)
- [Filtering](https://turbo.build/repo/docs/core-concepts/monorepos/filtering)
- [Configuration Options](https://turbo.build/repo/docs/reference/configuration)
- [CLI Usage](https://turbo.build/repo/docs/reference/command-line-reference)

## License

2023 &copy; Murshid Azher.
