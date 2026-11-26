# Changelog

## 2.0.2

### Changed

- Supports PHP 8.1 again, like Magento 2.4.6: the Adobe Commerce Marketplace requires modules to allow every PHP
  version of the Magento versions they support.

## 2.0.1

### Changed

- Requires `infrangible/m2-foundation` 3.0, the module that presents Infrangible in the Magento admin.

## 2.0.0

### Security

- The wrapper of product options added the type, code and title of the option to the HTML attributes without escaping.
  They are escaped now.

### Breaking changes

- Requires Magento 2.4.6 or newer and PHP 8.2 or newer. Magento 2.2 to 2.4.5 and PHP 7.1 to 8.1 are no longer
  supported; use version 1.x for these.
- Requires `fewedev/base` 2.4 and `magento/module-catalog`, and no longer `infrangible/m2-foundation`, which the module
  does not use.
- The wrapper block `Block\Product\View\Options\Option` gets the additional constructor argument `Variables`.
- All class properties, parameters and return values have native types. The plugin uses constructor property
  promotion.
- `Option::getOption()` throws a `LogicException` if the block has no product option.

### Changed

- The wrapper has no classes for an empty type, title or code of the option (`field-wrapper-`) any more.
- The CSS classes of the wrapper come from `Option::getWrapperClasses()`, the ID from `Option::getOptionId()`.
- Dependencies only allow patch releases of the tested minor versions (`~X.Y.Z`).
- Checks with PHPStan level 9, the Magento coding standard and unit tests on every push.
