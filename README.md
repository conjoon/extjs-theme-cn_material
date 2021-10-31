# @conjoon/extjs-theme-material ![MIT](https://img.shields.io/npm/l/@conjoon/extjs-theme-material) [![npm version](https://badge.fury.io/js/@conjoon%2Fextjs-theme-material.svg)](https://badge.fury.io/js/@conjoon%2Fextjs-theme-material)

This Sencha ExtJS NPM package contains the material theme for development of [conjoon](https://github.com/conjoon) along
with its application packages.
Please note, that this theme serves as a base for pluggable packages, such as 
[conjoon/extjs-app-webmail](https://github.com/conjoon/extjs-app-webmail), where styling information for these 
packages are self-contained.
This theme extends the Material-Theme of ExtJS. ExtJS > 7.0 is required for this package. 

## Installation
```bash
$ npm install --save-dev @conjoon/extjs-theme-material
```
If you want to develop with with this package, run the `build:dev`-script afterwards:
```bash
$ npm run build:dev
```
Testing environment will then be available via

```bash
$ npm test
```

For using the package as an external dependency in an application, use
```bash
$ npm install --save-prod @conjoon/extjs-theme-material
```
In your `app.json`, add this package as a requirement, and make sure your ExtJS `workspace.json`
is properly configured to look up local repositories in the `node_modules`-directory.

Example (`workspace.json`) :
```json 
{
  "packages": {
    "dir": "${workspace.dir}/node_modules/@l8js,${workspace.dir}/node_modules/@conjoon,${workspace.dir}/node_modules/@coon-js,${workspace.dir}/packages/local,${workspace.dir}/packages,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name},${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-treegrid,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-base,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-ios,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-material,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-aria,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-neutral,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-classic,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-gray,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-crisp,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-crisp-touch,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-neptune,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-neptune-touch,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-triton,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-graphite,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-material,${workspace.dir}/node_modules/@sencha/ext-calendar,${workspace.dir}/node_modules/@sencha/ext-charts,${workspace.dir}/node_modules/@sencha/ext-d3,${workspace.dir}/node_modules/@sencha/ext-exporter,${workspace.dir}/node_modules/@sencha/ext-pivot,${workspace.dir}/node_modules/@sencha/ext-pivot-d3,${workspace.dir}/node_modules/@sencha/ext-ux,${workspace.dir}/node_modules/@sencha/ext-font-ios",
    "extract": "${workspace.dir}/packages/remote"
  }
}
```

## Usage
Specified as `theme` property in conjoon's `app.json`.
Additionally, packages providing styling information might refer to this theme
to access SASS-variable definitions.

## Note
### Registering as a coon.js-Theme
This theme automatically registers itself by setting the following global properties:
```javascript
Ext.theme.is["coon-js-theme"] = true;
Ext.theme.name = "extjs-theme-material";
```
This is to identify itself later on for proper inclusion in the coon.js-environment.

### Loading Source Files
Although the package is registered as a static-theme package, sources such as the `conjoon.theme.material.Theme`
cannot be required in a production build if not specified explicitely. There is a dummy-override in the `init.js`-file
defined that makes sure that the class is made available to applications.
