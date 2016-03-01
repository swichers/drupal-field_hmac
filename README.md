# Field HMAC (Hash Message Authentication Code)

This module is meant to easily allow a Drupal developer to configure per-entity
message authentication codes. Once configured a new property will be available
on entities (and in Views) that contains the HMAC.

*Note: Currently only supports node entities.*

# Configuration

  * Install and enable the module
  * Navigate to the content type configuration form for the desired content types
  * Enable the HMAC checkbox under the "Field HMAC" tab
  * Select a field or property
  * Enter a secret key

# Example usage

```php
<?php
  // Assumes HMAC has been configured.
  $wrapper = entity_metadata_wrapper('node', 123);
  $hmac = $wrapper->hmac->value();

  // Do something/validate with HMAC.
  dpm($hmac);
?>
```

# See other

https://en.wikipedia.org/wiki/Hash-based_message_authentication_code
