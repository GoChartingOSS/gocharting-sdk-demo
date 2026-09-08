# GoCharting SDK Demo

A React (Create React App + CRACO) demo application showcasing the
`@gocharting/chart-sdk`. It includes a multi-page navigation system with several chart examples — see
[`NAVIGATION.md`](./NAVIGATION.md) and
[`ADVANCED_TRADING_EXAMPLE.md`](./ADVANCED_TRADING_EXAMPLE.md).

## Prerequisites

- Node.js 18+
- [pnpm](https://pnpm.io/) (`npm install -g pnpm`)
- A GoCharting **SDK key** — this demo uses the public demo key below

## Getting the SDK

`@gocharting/chart-sdk` is **not on the public npm registry**. Install it with
[`@gocharting/cli`](https://www.npmjs.com/package/@gocharting/cli), which
authenticates against the GoCharting registry and adds the package to this
project.

From the repository root:

**pnpm** (used by this demo)

```bash
pnpm --package=@gocharting/cli dlx gocharting install @gocharting/chart-sdk@webpack --pm pnpm
```

**npm**

```bash
npx -p @gocharting/cli gocharting install @gocharting/chart-sdk@webpack --pm npm
```

**yarn**

```bash
yarn dlx -p @gocharting/cli gocharting install @gocharting/chart-sdk@webpack --pm yarn
```

The CLI prompts for two things:

| Prompt | Value |
| --- | --- |
| **Email** | Optional — press Enter to skip. |
| **SDK key** | `demo-550e8400-e29b-41d4-a716-446655440000` |

The `webpack` dist-tag is the build this demo targets; to pin an exact release,
swap `@webpack` for a version (e.g. `@gocharting/chart-sdk@1.0.71`).

The same demo key is used again at runtime as the chart's **license key** in
`createChart({ licenseKey })`. Both are for evaluation — replace them with your
own key for production ([gocharting.com](https://www.gocharting.com)).

## Running the demo

The SDK is consumed as a published dependency from the GoCharting registry
(`"@gocharting/chart-sdk": "<version>"` in `package.json`).

```bash
# install the SDK from the GoCharting registry
# (email: press Enter to skip | SDK key: demo-550e8400-e29b-41d4-a716-446655440000)
pnpm --package=@gocharting/cli dlx gocharting install @gocharting/chart-sdk@webpack --pm pnpm

pnpm install
pnpm start          # runs on http://localhost:3000
```

To test a different published SDK version, rerun the CLI with that version:

```bash
pnpm --package=@gocharting/cli dlx gocharting install @gocharting/chart-sdk@<version> --pm pnpm
pnpm start
```

## Available Scripts

| Script | Description |
| --- | --- |
| `pnpm start` | Run the demo in development mode (http://localhost:3000). |
| `pnpm run build` | Production build into `build/`. |
| `pnpm test` | Run the test runner in watch mode. |

## Learn More

- [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started)
- [CRACO documentation](https://craco.js.org/)
- [React documentation](https://reactjs.org/)
