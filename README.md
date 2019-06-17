# JSminify
[![PyPI version](https://badge.fury.io/py/lektor-jsminify.svg)](https://badge.fury.io/py/lektor-jsminify)

JS minifier for Lektor that automatically minifies javascript files

Uses [rjsmin](https://pypi.org/project/rjsmin/)  and looks for .js files,
minifying them as part of the build process.

## Installing

You can install the plugin with Lektor's installer::
```bash
lektor plugins add lektor-jsminify
```

Or by hand, adding the plugin to the packages section in your lektorproject file::
```bash
[packages]
lektor-jsminify = 1.0
```

## Usage
#####

To enable jsminify, pass the `jsminify` flag when starting the development
server or when running a build::
```bash
lektor build -f jsminify
```

When the flag is present, jsminify will take all .js files from asset_sources/js, minifies them and places them
in assets/js.


The Plugin has the following settings you can adjust to your needs:

|parameter      |default value      |description                                                                                       |
|---------------|-------------------|--------------------------------------------------------------------------------------------------|
|source_dir     |asset_sources/scss/| the directory in which the plugin searchs for sass files (subdirectories are included)           |
|output_dir     |assets/css/        | the directory the compiled css files get place at                                                |
|output_style   |compressed         | coding style of the compiled result. choose one of: 'nested', 'expanded', 'compact', 'compressed'|
|source_comments|False              | whether to add comments about source lines                                                       |
|precision      |5                  | precision for numbers                                                                            |

An example file with the default config can be found at `configs/jscompile.ini`
