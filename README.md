CKEditor Accessibility Checker
==================================================

# Overview

This repository contains the development version of Accessibility checker plugin for CKEditor.

## Requirements

* CKEditor **4.3.0** or later
* jQuery **1.x** in order to run [Quail](http://quailjs.org/)

## Installation

### Development Version

If you're not interested in developing core Accessibility Checker features, feel free to skip this section.

```bash
 Assuming that $CKEDITOR_DEV_PATH is your CKEditor path.
cd $CKEDITOR_DEV_PATH/plugins
git clone -b dev git@github.com:cksource/ckeditor-plugin-a11ychecker.git a11ychecker
```

#### Checkout A11ychecker Quail Adapter

```bash
 Assuming that $CKEDITOR_DEV_PATH is your CKEditor path.
cd $CKEDITOR_DEV_PATH/plugins
git clone git@github.com:cksource/ckeditor-plugin-a11ycheckerquail.git a11ycheckerquail
```

#### Checkout Balloon Plugin

```bash
git clone git@github.com:cksource/ckeditor-plugin-balloonpanel.git balloonpanel
```

#### Building Extra Stuff

You'll also need to build a CSS, since we use LESS.

```bash
npm install
grunt build-css
```

//Pro tip:// you can also use `grunt watch:less`.

### Distribution Version

For more information about distribution version see [`DISTRIBUTION.md`](DISTRIBUTION.md) file.

### Building a Distribution Version

You can build a distribution package using grunt task.

Main changes in distribution version:
* It doesn't use RequireJS, so all the classes are inlined.
* It contains `CKEDITOR.plugins.a11ychecker.rev` property with a revision hash.
* Got quickfixes minified.
* It will automatically create a zip archive so that you can share it without putting a code to public repo.

To build Accessibility Checker simply go to the `a11ychecker` plugin directory. And execute following commands:

```bash
npm install
grunt build
```

Build files are put in `build` directory in `a11ychecker` plugin.

#### Building a Full Distribution

Since Accessibility Checker has actually a few dependencies, you might want to include all the dependent plugins,
just to make installation easier.

We have a build-full feature, that will include also dependent plugins into build directory, and created zip archive.

```bash
npm install
grunt build-full
```

Now another person might simply get a zip, extract it to `ckeditor/plugins` directory, and he's ready to go.

## Where Do I Start?

You should use `plugins/a11ycheckerquail/dev/sample.html` sample to test the Accessibility Checker (eg. [ckeditor.dev](http://ckeditor.dev/plugins/a11ycheckerquail/dev/sample.html)).

Other samples will not work because of RequireJS dependency, which is not a part of standard CKEditor distribution.

## Tests Installation

Create a symbolic link

Linux:

```bash
ln -s $CKEDITOR_DEV_PATH/plugins/a11ychecker/tests/plugins/a11ychecker $CKEDITOR_DEV_PATH/tests/plugins/a11ychecker
```

Windows (run cli as administrator):

```bat
mklink /D "%CKEDITOR_DEV_PATH%/tests/plugins/a11ychecker" "%CKEDITOR_DEV_PATH%/plugins/a11ychecker/tests/plugins/a11ychecker"
```

## License

@todo
