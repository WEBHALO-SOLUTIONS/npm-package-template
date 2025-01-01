# package-template

This repository is meant to be a template for being able to create a `npm` based package that is then deployed to GitHub packages.

## Usage

1. Create a repository using this one as a template
2. Search for any use of `YOUR-ORG-NAME` and replace with your organization name or you GitHub username where this repository will reside
3. Search for any use of `YOUR-REPOSITORY-NAME` and replace with the name of your repository that you have created
4. Make any adjustments
   1. Review the [package.json](./package.json) file and make any other updates needed
   2. Review the [tsconfig.json](./tsconfig.json) and make any adjustments you needed
   3. Review the [.npmrc](./.npmrc) file and make any adjustments
   4. Review the [eslint.config](./eslint.config.mjs) and make any adjustments
   5. Review the [release-package.yml](./.github/workflows/release-package.yml) and make any adjustments if needed
5. Adding your own code
   1. Start adding your code in the [src](./src/) folder, there is a super simple stub there for now
   2.  Be certain to update the [index.d.ts](./index.d.ts) with your type declarations so that consuming projects know the appropriate type information
   3.  Run an `npm install` locally to install dependencies 
   4.  Run `npm run build` to perform a build, a `npm run lint` to perform linting or `npm runs start` to run the code
6.  Note the steps at [Quickstart: Publish to GitHub Packages with GitHub Actions](https://docs.github.com/en/packages/quickstart) for utilizing the workflow that is part of this template, it is what published to GitHub Packages

## Contribute

Have ideas or suggestions on how to make this template better, please feel free to contribute, create an issue, or submit a pull request.
