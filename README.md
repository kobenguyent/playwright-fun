[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/peternguyew)

# Introduction

This project demonstrates how to drive your E2E tests with Playwright.

* Tests are written in TS
* CI/CD with Github Actions
* ReportPortal Integration

## How to use

This is done using Playwright <https://playwright.dev/>

### Tech

This test uses a number of open source projects to work properly:

* <https://nodejs.org/en/> - evented I/O for the backend
* <https://playwright.dev/> - Playwright

### Installation

This requires [Node.js](https://nodejs.org/) v14+ to run.

Install the dependencies and devDependencies.

```sh
cd playwright-fun
npm i
```

### How to trigger test

To run all tests just simply type

```sh
npm test
```

Example output

```
playwright-fun % npx playwright test
To open last HTML report run:

  npx playwright show-report
```

### HTML Report

![HTML Report](http://g.recordit.co/0W6XGBYx6A.gif)

### Reportportal

Updating the configurations accordingly.

```
...
/**
* Report Portal
*/
const RPconfig = {
  token: process.env.RP_TOKEN,
  endpoint: 'https://demo.reportportal.io/api/v1',
  project: 'peterngtr_personal',
  launch: 'peterngtr_TEST_EXAMPLE',
  description: 'Your launch description',
  includeTestSteps: true
}
...
const config: PlaywrightTestConfig = {
  reporter: [['@reportportal/agent-js-playwright', RPconfig], ['html']],
  testDir: './tests',
  ...
```

After the test execution

![Report Portal](http://g.recordit.co/tEzpzZlrc1.gif)

