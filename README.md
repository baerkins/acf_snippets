Advanced Custom Fields Snippets for Sublime Text
================================================

This is a collection of Sublime Text snippets for the [Advanced Custom Fields](http://www.advancedcustomfields.com/) Wordpress plugin.

## Installation

### Recommended

Install this package with [Package Control](https://sublime.wbond.net/):
1. Install Package Control in Sublime.
2. Press `Cmd` + `Shift` + `P` (OSX) or `Ctrl` + `Shift` + `P` (Windows/Linux)
3. Select Install Package
4. Search 'ACF Snippets'

### Manual

Copy this folder to the `Packages` folder of your Sublime Text installation.

Mac users: Library/Application Support/Sublime Text/Packages

## Snippets

Snippets are described by `tabTrigger` - `codeOutput`.

To make things the easiest to remember, snippet triggers are typically named as abbreviations for their output. For example, `tf` outputs (T)he (F)ield.

Field names and variable outputs that are auto-highlighted for replacement by Sublime Text are shown in the code wrapped in asterisks.

*Note: All snippets need to be triggered within an open* `<?php` *tag. Once triggered, the snippet will close out the tag with* ` ?>`.

### Standard Field Snippets
|Snippet|Output|
|-------|------|
| `tf` | `the_field('*field_name*'); ?>` |
| `iftf` | `if_the_field('*field_name*'); ?>` |
| `gf` | `get_field('*field_name*'); ?>` |
| `ifgf` | `if_get_field('*field_name*'); ?>` |
| `df` | Outputs a block of code for a date field |
| `imgf` | Outputs a block of code for an Image ID field |
| `imgobj` | Outputs a block of code for an Image Object field |
| `relf` | Outputs a basic loop for a Relationship field |


### Sub Field Snippets
|Snippet|Output|
|-------|------|
| `tsf` | `the_sub_field('*field_name*'); ?>` |
| `gsf` | `get_sub_field('*field_name*'); ?>` |
| `whsf` | `while(has_sub_field('*field_name*')) : ?>` |
| `ifgsf` | `if(get_sub_field('*field_name*')) : ?>` |
| `dsf` | Outputs a block of code for a date field |
| `relsf` | Outputs a basic loop for a Relationship field |


### Options Page Field Snippets
*These snippets are the same as the standard and repeater snippets, but with an 'o' appended to the end.*

|Snippet|Output|
|-------|------|
| `tfo` | `the_field('*field_name*', 'options'); ?>` |
| `iftfo` | `if_the_field('*field_name*', 'options'); ?>` |
| `gfo` | `get_field('*field_name*', 'options'); ?>` |
| `ifgfo` | `if_get_field('*field_name*'); ?>` |
| `tsfo` | `the_sub_field('*field_name*', 'options'); ?>` |
| `whsfo` | `while(has_sub_field('*field_name*', 'options')) : ?>` |
| `ifgsfo` | `if(get_sub_field('*field_name*', 'options')) : ?>` |
| `imgfo` | Outputs a block of code for an Image ID field from the options page |
| `imgobjo` | Outputs a block of code for an Image Object field from the options page |
| `gmfo` | Outputs Google Map Field code for a single location from the options page |
| `relfo` | Outputs a basic loop for a Relationship field from the options page |

### Repeater Field Snippets
|Snippet|Output|
|-------|------|
| `rf` | Outputs a block of code that opens and closes a repeater field loop |
| `rfo` | Outputs a block of code that opens and closes a repeater field loop from the options page. |

### Flexible Field Snippets
|Snippet|Output|
|-------|------|
| `ffall` | Outputs a complete block (think _all_ of the code) of a flexible field statement with a single flex field row element |
| `ffpart` | Outputs only a single flex field row element (think _part_ of the code) |

### Gallery Field Snippets
| `gallf` | Outputs a block of code for an Image Gallery field |
| `gallsf` | Outputs a block of code for an Image Gallery sub-field |
| `gallo` | Outputs a block of code for an Image Gallery Field on an Options Page |

### Google Map Field Snippets
|Snippet|Output|
|-------|------|
| `gmf` | Outputs Google Map Field code for a single location |
| `gmsf` | Outputs Google Map Sub Field code for a single location |

## Utility Snippets
These snippets serve specific purposes, but are a few bits of code that I have found useful, so maybe you will too!

`acfcreateoptions`
Used in functions.php, this snippet will output code that will create an mulitple options page in ACF 5. Code should be editted to reflect Option page names.

`acffirstrepeater`
This will output a repeater snippet that will retrieve only the first row of a repeater field.

