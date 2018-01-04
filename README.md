# Angular Storybook Screenshot Snapshot testing demonstration [![CircleCI](https://circleci.com/gh/Quramy/angular-sss-demo.svg?style=svg)](https://circleci.com/gh/Quramy/angular-sss-demo)

A demonstration Angular project includes:

- Storybook
- Screenshot stories
- Snapshot test using PNG files

## How to setup

### Angular
This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.5.4.

### Storybook

[Storybook](https://storybook.js.org/) is interactive environment for UI component development.

```sh
yarn add @storybook/angular -D
yarn run getstorybook
```

The above command adds `storybook` task to your package.json.

```sh
yarn storybook
```

And go to `http://localhost:6006/`. You can preview stories.

### Screenshot
Using [storybook-chrome-screenshot](https://github.com/tsuyoshiwada/storybook-chrome-screenshot) addon, we can capture each story as PNG image file.

To install this addon, we need to change several files. 
To detail, see https://github.com/Quramy/angular-sss-demo/commit/cf03a041004643c610b8671a07e866149df662f8 .

After setup, run `yarn screenshot`. Each story is generated as PNG file under the `__screenshot__` directory.

### Snapshot testing
[reg-suit](https://reg-viz.github.io/reg-suit/) provides visual snapshot testing environment.
This tool compares images captured and reports the difference them ([generated report](https://reg-publish-bucket-e4c131e5-5128-47aa-8bd0-c9b4456c7618.s3.amazonaws.com/a4068effae2fd0caebbb5e490a01b47d5aa1669b/index.html)).

reg-suit is a CLI and provides init wizard:

```sh
yarn add reg-suit -D
yarn run reg-suit init --use-yarn
```

If you want more installation details, check https://github.com/reg-viz/reg-puppeteer-demo#configure-reg-suit out.

And the following command runs visual regression testing:

```sh
yarn run reg-suit run
```
