# Testing web sites with Google Lighthouse

[Lighthouse](https://github.com/GoogleChrome/lighthouse) is an open-source, automated tool for improving the performance, quality, and correctness of your web sites.

## Overview

Lighthouse analyzes web apps and web pages, collecting modern performance metrics and insights on developer best practices.
The tool audits the accessibility and SEO of your webpage, with a particular focus on core web vitals.
[Core Web Vitals](https://web.dev/i18n/pt/vitals/) are a set of metrics Google developed to measure web pages’ page speed and overall user experience.
These metrics have become increasingly important for website owners that want to provide a good user experience and rank higher on Google.

## Configuration

A config file called `lighthouserc.json` at the `test` folder controls the options for Lighthouse CI.
Next you need to configure the CI provider to run Lighthouse using the `lhci autorun` command.
`autorun` will automatically execute a number of commands behind the scenes and infer sensible defaults for you.

This project uses Lighthouse CI server in a Docker container, so first ensure you have Docker installed and running.
You can use the `docker-compose up -d` command to startup Lighthouse CI server.
Once the instance has started, navigate to <http://localhost:9001/> where you should see the dashboard welcome page.

As detailed on the welcome page, you need to create a project for your Lighthouse results to be uploaded to.
You can use `npm run wizard` command to walk you through these steps.

## Available npm scripts

The scripts in [package.json](package.json) file were built with simplicity in mind to automate as much repetitive tasks as possible and help developers focus on what really matters.

The next scripts should be executed in a console inside the root directory:

- `check` - Runs all checks.
- `lint` - Runs several static code analysis.
- `lint:fix` - Applies lint rules to project code.
- `test` - Test the web site pages.
- `clean` - Deletes the temporary files.

For more details, read the [npm scripts](https://docs.npmjs.com/cli/v8/using-npm/scripts) documentation.

## Linting and formatting code

Linters are also excellent tools for finding certain classes of bugs, such as those related to variable scope.
Use `npm run lint` to analyze your code.
Many problems can be automatically fixed with `npm run lint:fix`.

## Running audit tests

Use `npm run test` to execute the unit tests via Lighthouse.
The HTML report is available in the `.lighthouseci` folder and you can opening it in your web browser.
Lighthouse generates a HTML file for each page.

## Reference documentation

For further reference, please consider the following articles:

- [npm scripts](https://docs.npmjs.com/cli/v8/using-npm/scripts)
- [Web Vitals](https://web.dev/i18n/en/vitals/)
- [How To Analyze A Website With Lighthouse](https://isotropic.co/how-to-analyze-a-website-with-lighthouse/)
- [A Performance and Optimization Tool for Webpages](https://betterprogramming.pub/lighthouse-a-performance-and-optimization-tool-for-webpages-e0b4eeaef3e4)
