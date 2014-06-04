ct-sass-at-print
================

A wrapper for `@media print` which supports in-browser testing.

## Installation

1. In Terminal: `cd /PATH/TO/PROJECT-THEME-FOLDER`
1. `bower install https://github.com/chrometoasters/ct-sass-at-print.git#v1.0.0 --save`

Note: if you wish to customise where Bower puts installed components, you may add a `.bowerrc` file into this folder:

        {
            "directory" : "PATH/TO/COMPONENTS"
        }

## Usage

Several developer toolbars allow print styles to be tested by toggling on `@media print`, but the implementation only appears to include stylesheets linked with `media="print"`, excluding any `@media print` blocks in other stylesheets.

This mixin allows print styles to be authored within a module or screen stylesheet, passed to the browser at print time via `@media print`, and tested during development by toggling a class of `at-print` on the root element.

In this way print styles authored outside of the print stylesheet can be tested in the browser.

        // browser console
        $('html').addClass('at-print')
  
### Dependencies

Ensure that the mixin is available to your project:

        @import "ct-sass-at-print/dist/ct-sass-at-print`;

