# Next.js and AWS CDK Monorepo

This is a monorepo for a Next.js application and an AWS CDK project, managed with pnpm and Nx.

## Prerequisites

- [Node.js](https://nodejs.org/) (v18 or later)
- [pnpm](https://pnpm.io/installation)

## Getting Started

To get started, clone the repository and install the dependencies:

```bash
git clone git@github.com:AlexeyPopovUA/next-app-hosting.git
cd next-app-hosting
pnpm install
```

## Development

This monorepo contains two workspaces: `next-app` and `aws-cdk`.

### Running the Next.js App

To start the development server for the Next.js application, run the following command from the root of the project:

```bash
pnpm --filter next-app dev
```

This will start the Next.js app on `http://localhost:3000`.

### Working with the AWS CDK App

The `aws-cdk` workspace contains the infrastructure for this project. Here are some useful commands to run from the root of the project:

- **Synthesize CloudFormation template:**
  ```bash
  pnpm --filter aws-cdk synth
  ```

- **Deploy the stack:**
  ```bash
  pnpm --filter aws-cdk deploy
  ```

- **See the difference between the deployed stack and the current state:**
  ```bash
  pnpm --filter aws-cdk diff
  ```

## Building for Production

To build both the Next.js app and the AWS CDK app for production, run the following command from the root of the project:

```bash
pnpm build
```

This command uses Nx to run the `build` script in each workspace.

## Testing

To run the tests for both workspaces, run the following command from the root of the project:

```bash
pnpm test
```

This command uses Nx to run the `test` script in each workspace.

## Managing Dependencies

To add a dependency to a specific workspace, use the `--filter` flag with `pnpm add`.

For example, to add a dependency to the `next-app` workspace:

```bash
pnpm --filter next-app add <package-name>
```

To add a dev dependency:

```bash
pnpm --filter next-app add -D <package-name>
```

## Using Nx

[Nx](https://nx.dev) is used to manage the workspaces in this monorepo. You can use Nx to run commands in specific workspaces or in all of them.

For example, to run the `lint` command in the `next-app` workspace:

```bash
nx lint next-app
```

To see a graph of the project's dependencies, you can run:

```bash
nx graph
```
