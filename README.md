ct-sass-at-print
================

A wrapper for `@media print` which supports in-browser testing.

---

Several developer toolbars allow print styles to be tested by toggling on `@media print`, but the implementation appears limited to stylesheets linked with `media="print"` - excluding any `@media print` blocks in other stylesheets.

This mixin allows print styles to be authored within a module or screen stylesheet, passed to the browser at print time via `@media print`, and tested during development by toggling a class of `at-print` on the root element.

In this way print styles authored outside of the print stylesheet can be tested in the browser.

## Installation

1. In Terminal: `cd /PATH/TO/PROJECT-THEME-FOLDER`
1. `bower install https://github.com/chrometoasters/ct-sass-at-print.git#v1.0.0 --save`

Note: if you wish to customise where Bower puts installed components, you may add a `.bowerrc` file into this folder:

        {
            "directory" : "PATH/TO/COMPONENTS"
        }

## Usage

### Dependencies

Ensure that the mixin is available to your project:

        @import "ct-sass-at-print/dist/ct-sass-at-print";

### Authoring print styles

#### Style a selector that excludes the `html` element:

##### SCSS

        .element {
            @include at-print {
                display: none;
            }
        }
        
##### Compiled CSS

        @media print {
            .element {
                display: none;
            }
        }
        
        .at-print .element {
            display: none;
        }
        
#### Style a selector that includes the `html` element:

A common use case for this is styling dependent on the `js` ("JavaScript enabled") state which is applied to the `html` element via JavaScript.

##### SCSS

        .js {
            @include at-print-root {
                .m-module {
                    position: relative;
                }
            }
        }

##### Compiled CSS

        @media print {
            .js .m-module {
                position: relative;
            }
        }

        .js.at-print .m-module {
            position: relative;
        }

### Testing print styles

        // browser console
        $('html').addClass('at-print')
  
