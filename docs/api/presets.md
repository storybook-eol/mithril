---
title: 'Presets'
---

Presets are grouped collections of `babel`, `webpack`, and `addons` configurations that support specific use cases.

For example, to write your stories in Typescript, rather than [manually configuring](../configure/typescript.md) Storybook for TypeScript with individual [Babel](../configure/babel.md#custom-configuration) and [webpack](../configure/webpack.md#extending-storybooks-webpack-config) configs, you can use the [`@storybook/preset-typescript`](https://www.npmjs.com/package/@storybook/preset-typescript) package, which does the heavy lifting for you.

#### Existing presets

Storybook-maintained presets are available in the [presets repo](https://github.com/storybookjs/presets).

- [Create React App](https://github.com/storybookjs/presets/tree/master/packages/preset-create-react-app)
- [SCSS](https://github.com/storybookjs/presets/tree/master/packages/preset-scss)
- [TypeScript](https://github.com/storybookjs/presets/tree/master/packages/preset-typescript)
- [Ant Design](https://github.com/storybookjs/presets/tree/master/packages/preset-ant-design)

## Basic usage

Each preset has its own installation instructions, but the idea of presets is to install an addon and then load its preset.

For example, to get TypeScript support, first install the addon:

```sh
yarn add @storybook/preset-typescript --dev
```

Then load it in the file `main.js` in your storybook folder (`.storybook` by default):

<!-- prettier-ignore-start -->

<CodeSnippets
  paths={[
    'common/storybook-main-preset-config.js.mdx',
  ]}
/>

<!-- prettier-ignore-end -->

That's it. When Storybook starts up, it will configure itself for typescript without any further configuration. For more information, see the TypeScript preset [README](https://github.com/storybookjs/presets/tree/master/packages/preset-typescript).

## Preset configuration

Presets can also take optional parameters. These can be used by the preset itself or passed through to configure the webpack loaders that are used by the preset.

Consider this example:

<!-- prettier-ignore-start -->

<CodeSnippets
  paths={[
    'common/storybook-preset-configuration.js.mdx',
  ]}
/>

<!-- prettier-ignore-end -->

This configures the TypeScript loader using the app's `tsconfig.json` and also tells the TypeScript loader to only be applied to the current directory.

Each preset has its own option and those options should be documented in the preset's README.

## Go deeper

To understand more about how presets work and write your own, see [writing presets](./writing-presets.md).