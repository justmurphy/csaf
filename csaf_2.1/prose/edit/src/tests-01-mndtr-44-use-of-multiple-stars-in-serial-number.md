### Use of Multiple Stars in Serial Number

For each serial number it MUST be tested that the it does not contain multiple unescaped stars.

> Multiple `*` that match zero or multiple characters within a serial number introduce ambiguity and are therefore prohibited.

The relevant paths for this test are:

```
  /product_tree/branches[](/branches[])*/product/product_identification_helper/serial_numbers[]
  /product_tree/full_product_names[]/product_id/product_identification_helper/serial_numbers[]
  /product_tree/relationships[]/full_product_name/product_id/product_identification_helper/serial_numbers[]
```

*Example 1 (which fails the test):*

```
          "serial_numbers": [
            "P*A*"
          ]
```

> The serial number contains two unescaped stars.
