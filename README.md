Advanced Custom Fields Snippets for Sublime Text
================================================

This is a collection of Sublime Text snippets for the [Advanced Custom Fields](http://www.advancedcustomfields.com/) Wordpress plugin.

## Usage

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
| `imgf` | Outputs a block of code for an Image ID field:|

```php
  $attachment_id = get_field('*field_name*');
  $size = "*full*";
  $image = wp_get_attachment_image_src( $attachment_id, $size ); ?>

<img src="<?php echo \$image[0]; ?>" />
```
|Snippet|Output|
|-------|------|
| `imgobj` | Outputs a block of code for an Image Object field:|

```php
// ACF Image Object
$image = get_field('*field_name*');
$url = $image['url'];
$alt = $image['alt'];
$imageSize = $image['sizes'][ '*large*' ]; ?>

<img src="<?php echo $imageSize; ?>" alt="<?php echo $alt; ?>" />
```

### Sub Field Snippets
|Snippet|Output|
|-------|------|
| `tsf` | `the_sub_field('*field_name*'); ?>` |
| `whsf` | `while(has_sub_field('*field_name*')) : ?>` |
| `ifgsf` | `if(get_sub_field('*field_name*')) : ?>` |

### Repeater Field Snippets
|Snippet|Output|
|-------|------|
| `rf` | Outputs a block of repeater field code: |

```php
if(get_field('*field_name*')) : ?>
  <*ul*>
    <?php while(has_sub_field('*field_name*')) : ?>
      <*li*><?php the_sub_field(‘*sub_field_name*’); ?></*li*>
    <?php endwhile;>
  </*ul*>
<?php endif; ?>
```

### Flexible Field Snippets
|Snippet|Output|
|-------|------|
| `ffall` | Outputs a complete block (think _all_ of the code) of a flexible field statement: |

```php
// Start Flexible Content
if( have_rows(‘*field_name*’)): :
	while ( have_rows(‘*field_name*’) ) : the_row(); ?>

		<?php

		// Layout Name: *layout_name*
		if( get_row_layout() == ‘*layout_field*’ ): ?>
			<*div*>
				<?php the_sub_field(‘*field_name*’); ?>
			</*div*>

		<?php endif; ?>
	<?php endwhile; ?>
<?php endif; ?>
```

|Snippet|Output|
|-------|------|
| `ffpart` | Outputs only a new layout portion (think _part_ of the code) of a flexible field statement : |

```php
	// Layout Name: *layout_name*
	elseif( get_row_layout() == ‘*layout_field*’ ): ?>
		<*div*>
			<?php the_sub_field(‘*field_name*’); ?>
		</*div*>
```

### Options Page Field Snippets
*These snippets are the same as the standard and repeater snippets, but with an 'o' appended to the end.*

|Snippet|Output|
|-------|------|
| `tfo` | `the_field('*field_name*', 'options'); ?>` |
| `iftfo` | `if_the_field('*field_name*', 'options'); ?>` |
| `gfo` | `get_field('*field_name*', 'options'); ?>` |
| `ifgfo` | `if_get_field('*field_name*'); ?>` |
| `imgfo` | Outputs a block of code for an Image ID field from the options page:|

```php
  $attachment_id = get_field('*field_name*');
  $size = "*full*";
  $image = wp_get_attachment_image_src( $attachment_id, $size ); ?>

<img src="<?php echo \$image[0]; ?>" />
```


|Snippet|Output|
|-------|------|
|  `tsfo` | `the_sub_field('*field_name*', 'options'); ?>` |
|  `whsfo` | `while(has_sub_field('*field_name*', 'options')) : ?>` |
| `ifgsfo` | `if(get_sub_field('*field_name*', 'options')) : ?>` |
| `rfo` | Outputs a block of repeater field code from the options page:|

```php
if(get_field('*field_name*', 'options')) : ?>
  <*ul*>
    <?php while(has_sub_field('*field_name*', 'options')) : ?>
      <*li*><?php the_sub_field(*sub_field_name*, 'options'); ?></*li*>
    <?php endwhile;>
  </*ul*>
<?php endif; ?>
```
