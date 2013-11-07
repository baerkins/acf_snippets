Advanced Custom Fields Snippets for Sublime Text
================================================

This is a collection of Sublime Text snippets for the [Advanced Custom Fields](http://www.advancedcustomfields.com/) Wordpress plugin.

## Usage

Copy this folder to the `Packages` folder of your Sublime Text installation.

Mac users: Library/Application Support/Sublime Text 2/Packages
Mac users: Library/Application Support/Sublime Text 2/Packages

## Snippets 

Snippets are described by `tabTrigger` - `codeOutput`. 

To make things the easiest to remember, snippets are typically named as abbreviations for their output. For example, `tf` outputs a **t**he_**f**ield code snippet.

Field names and variable outputs that are auto-highlighted for replacement by Sublime Text are shown in the code wrapped in asterisks.

*Note: All snippets need to be triggered within an open `<?php1` tag. Once triggered, the snippet will close out the tag with ` ?>`.*

### Standard Field Snippets
- `tf` - `the_field('*field_name*'); ?>`
- `iftf` - `if_the_field('*field_name*'); ?>`
- `gf` - `get_field('*field_name*'); ?>`
- `ifgf` - `if_get_field('*field_name*'); ?>`
- `imgf` - Outputs a block of code for an Image ID field:

```php
  $attachment_id = get_field('*field_name*');
  $size = "*full*";
  $image = wp_get_attachment_image_src( $attachment_id, $size ); ?>

<img src="<?php echo \$image[0]; ?>" />
```

### Repeater Field Snippets
- `tsf` - `the_sub_field('*field_name*'); ?>`
- `whsf` - `while(has_sub_field('*field_name*')) : ?>`
- `ifgsf` - `if(get_sub_field('*field_name*')) : ?>`
- `rf` - Outputs a block of repeater field code:

```php
if(get_field('*field_name*')) : ?>
  <*ul*>
    <?php while(has_sub_field('*field_name*')) : ?>
      <*li*><?php the_sub_field(*sub_field_name*); ?></*li*>
    <?php endwhile;>
  </*ul*>
<?php endif; ?>
```

### Options Page Field Snippets
*These snippets are the same as the standard and repeater snippets, but with an 'o' appended to the end.*
- `tfo` - `the_field('*field_name*', 'options'); ?>`
- `iftfo` - `if_the_field('*field_name*', 'options'); ?>`
- `gfo` - `get_field('*field_name*', 'options'); ?>`
- `ifgfo` - `if_get_field('*field_name*'); ?>`
- `imgfo` - Outputs a block of code for an Image ID field from the options page:

```php
  $attachment_id = get_field('*field_name*');
  $size = "*full*";
  $image = wp_get_attachment_image_src( $attachment_id, $size ); ?>

<img src="<?php echo \$image[0]; ?>" />
```
-  `tsfo` - `the_sub_field('*field_name*', 'options'); ?>`
-  `whsfo` - `while(has_sub_field('*field_name*', 'options')) : ?>`
- `ifgsfo` - `if(get_sub_field('*field_name*', 'options')) : ?>`
- `rfo` - Outputs a block of repeater field code from the options page:

```php
if(get_field('*field_name*', 'options')) : ?>
  <*ul*>
    <?php while(has_sub_field('*field_name*', 'options')) : ?>
      <*li*><?php the_sub_field(*sub_field_name*, 'options'); ?></*li*>
    <?php endwhile;>
  </*ul*>
<?php endif; ?>
```