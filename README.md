<img src="src/icon.svg" width="100">

# Odds & Ends

A collection of useful tools for Craft CMS websites.

## Field types

### Width
This lets you define the width of a block as well as left and right padding. This field simply outputs three sets of classes which can be defined when setting the field up.

![Width Field Settings](docs/assets/width-settings.png)
![Width Field](docs/assets/width-field.png)

### Author Instructions
This lets you output markdown instead of a field, which is useful when you have a Matrix block that doesn’t have any fields.

![Author Instructions Example](docs/assets/author-instructions-example.png)

### Categories (multiple groups)
A Categories input that lets you select multiple Category groups.

### Ancestors
An Entries input that only shows the ancestors of the current Entry.

### Search Fields
Like the Tags input, but for entries and categories (without the auto-creation feature). If Craft Commerce is installed, search fields for products and variants are also available.

### Disabled Fields
The same as regular fields, but disabled. Useful for situations where you want to integrate with a third party API and store that information in a field but don’t want the user to change it.

The following field types are currently supported:

- Entries
- Categories
- Lightswitch
- Number
- PlainText
- Dropdown
- Commerce Products
- Commerce Variants

## Widgets

### Roll Your Own
A simple widget that lets you assign a template to load from your site templates folder. Go nuts.

## Miscellaneous

### Download File

A controller action that will download an asset file.

The `id` parameter is required and must be a valid asset ID.

Usage:
```
<a href="{{ actionUrl('tools/tools/download-file', { id: entry.assetField.one().id }) }}">Download</a>
```


## Configuration

By default, all normal field types and widgets are enabled. 
The commerce field types are only enabled if Craft Commerce is installed and enabled.
You can disable each field type and widget by adding the following to your project's `config/tools.php` file:

```php
use spicyweb\oddsandends\fields\AuthorInstructions;
use spicyweb\oddsandends\fields\DisabledProducts;
use spicyweb\oddsandends\widgets\RollYourOwn;

return [
    'disableNormalFields' => [
        AuthorInstructions::class,
    ],
    'disableCommerceFields' => [
        DisabledProducts::class,
    ],
    'disableWidgets' => [
        RollYourOwn::class,
    ],
];
```

Multi environment config is supported. See [Craft's docs](https://craftcms.com/docs/4.x/config/#multi-environment-configs) for more info.
See `config/tools.php` in this repo for an example on how to disable any field and widget.

---

*Created by [Supercool](https://supercooldesign.co.uk)*
<br>
*Maintained by [Spicy Web](https://spicyweb.com.au)*
