# Running `vitest` with Bazel

The project is used to reproduce the issue where `vitest` is not able to find any test files when
running under Bazel.

Vitest is working as expected when running with either `yarn` or `pnpm`. All of the mentioned
use-cases are part of the CI.

## Using `pnpm`

```
npm i -g pnpm
pnpm run build
pnpm run test:unit
```

## Using `yarn`

```
npm i -g yarn
yarn run build
yarn run test:unit
````

## Using Bazel

```
bazel build //:build
bazel run //:test
````
