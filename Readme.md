# @conjoon/extjs-theme-material  
This Sencha ExtJS NPM package contains the material theme for development of [conjoon](https://github.com/conjoon) along
with its application packages.
Please note, that this theme serves as a base for pluggable packages, such as 
[conjoon/app-cn_mail](https://github.com/conjoon/app-cn_mail), where styling information for these 
packages are self-contained.
This theme extends the Material-Theme of ExtJS. ExtJS > 7.0 is required for this package. 

## Installation
```
npm install --save-dev @conjoon/extjs-theme-material
```

## Post-Install
[@coon-js/extjs-link](https://npmjs.org/coon-js/extjs-link) will start once the package was installed and guide you
through the process of creating symlinks to an existing ExtJS sdk installation.
This is only required if you want to run the tests (`./tests`), as [Siesta](https//npmjs.org/siesta-lite) relies on
an existing ExtJS installation.

# Usage
Specified as ```theme``` property in conjoon's ```app.json```.
Additionally, packages providing styling information might refer to this theme
to access SASS-variable definitions.

# Note
## Registering as a coon.js-Theme
This theme automatically registers itself by setting the following global properties:
```
Ext.theme.is["coon-js-theme"] = true;
Ext.theme.name = "extjs-theme-material";
```
This is to identify itself later on for proper inclusion in the coon.js-environment.

## Loading Source Files
Although the package is registered as a static-theme package, sources such as the ```conjoon.theme.material.Theme```
cannot be required in a production build if not specified explicitely. There is a dummy-override in the ```init.js```-file
defined that makes sure that the class is made available to applications.

## Dev
### Naming
The following naming conventions apply:

#### Namespace
#### Package name
`extjs-theme-material`
