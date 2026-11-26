# Infrangible Catalog Product Option Wrapper

Adds an element around every custom option on the product page, so that themes and other modules can find and style
single options. The element has the ID `product-option-<option ID>`, the attribute `data-option-id` and these CSS
classes:

- `field-wrapper`
- `field-wrapper-<type>`, for example `field-wrapper-drop_down`
- `field-wrapper-<title>`: the title of the option in lower case, with spaces replaced by underscores and an underscore
  before upper case letters, for example `field-wrapper-gift__wrap` for "Gift Wrap"
- `field-wrapper-<code>`, if the option has a code (for example from
  [Infrangible Catalog Product Option Code](https://www.infrangible.dev/modules/catalog-product-option-code))

## Requirements

- Magento Open Source or Adobe Commerce 2.4.6 or newer
- PHP 8.1 or newer

## Installation

```bash
composer require infrangible/m2-catalog-product-option-wrapper
bin/magento module:enable Infrangible_CatalogProductOptionWrapper
bin/magento setup:upgrade
```

In production mode, also run `bin/magento setup:di:compile` and `bin/magento setup:static-content:deploy`.

## Usage in other modules

Other lists of options can use the same wrapper: add a block of the class
`Infrangible\CatalogProductOptionWrapper\Block\Product\View\Options\Option` with the template
`Infrangible_CatalogProductOptionWrapper::product/view/options/option.phtml` as child `product_option_wrapper` of the
block that renders the options, and wrap the HTML of each option with
`Infrangible\CatalogProductOptionWrapper\Helper\Data::renderWrapper($block, $option, $optionHtml)`.

## License

Infrangible Catalog Product Option Wrapper is licensed under the MIT License - see the LICENSE file for details.
