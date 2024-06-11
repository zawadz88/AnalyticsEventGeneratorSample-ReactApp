## AnalyticsEventGenerator Sample - React App

In order to build the package locally you need to be authenticated to access Github Packages
(needed for private repositories): https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-npm-registry#authenticating-with-a-personal-access-token

You'll need to run locally:

```
yarn set version 4.3.0
yarn config set npmScopes.zawadz88.npmRegistryServer "https://npm.pkg.github.com"
yarn config set npmScopes.zawadz88.npmAlwaysAuth true
yarn config set npmScopes.zawadz88.npmAuthToken [YOUR PERSONAL GITHUB TOKEN]
```

(Make sure `[YOUR PERSONAL GITHUB TOKEN]` has `read:packages` permission).

To install needed NPM packages execute `yarn install`.

Then to run locally execute `yarn webpack serve --mode development`.

### Using local version of shared-analytics-library

- In AnalyticsEventGeneratorSample-ReactApp run `yarn remove shared-analytics-library` to remove the one distributed via
  Github Packages.
- Build the library in AnalyticsEventGeneratorSample-SharedLibrary with `./gradlew assemble`.
- Install the local library
  via `yarn add shared-analytics-library@file:./../SharedAnalyticsLibrary/build/dist/js/productionLibrary` (assuming
  both projects share the same parent directory).
- In case you make some changes to AnalyticsEventGeneratorSample-SharedLibrary, you'd need to repeat the previous step
  to have the latest
  changes available in nalyticsEventGeneratorSample-ReactApp as the packages gets copied to `node_modules`.

To add the version from Github Packages again -
execute `yarn add shared-analytics-library@npm:@zawadz88/shared-analytics-library@LATEST_SHARED_LIBRARY_VERSION_PLACEHOLDER`
