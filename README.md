## AnalyticsEventGenerator Sample - React App

In order to build the package you need to make sure that you authenticate to Github Packages
in case it's a private
repository: https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-npm-registry#authenticating-with-a-personal-access-token
E.g. create an `~/.npmrc` with:

```
//npm.pkg.github.com/:_authToken=[YOUR PERSONAL GITHUB TOKEN]
```

To install needed NPM packages locally execute `yarn install`.

Then to run locally execute `yarn webpack serve --mode development`.

### Using local version of shared-analytics-library

- In AnalyticsEventGeneratorSample-ReactApp run `yarn remove shared-analytics-library` to remove the one distributed via Github Packages.
- Build the library in AnalyticsEventGeneratorSample-SharedLibrary with `./gradlew assemble`.
- Install the local library
  via `yarn add shared-analytics-library@file:./../SharedAnalyticsLibrary/build/dist/js/productionLibrary` (assuming
  both projects share the same parent directory).
- In case you make some changes to AnalyticsEventGeneratorSample-SharedLibrary, you'd need to repeat the previous step to have the latest
  changes available in nalyticsEventGeneratorSample-ReactApp as the packages gets copied to `node_modules`.

Re-adding the version from Github Packages:

- execute `yarn add shared-analytics-library@npm:@zawadz88/shared-analytics-library@1.0.0`
