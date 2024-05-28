API Reference
=============
The following section outlines the API of Shopi-Py

Shop
----
``class shopipy.Shop(title, currency, footer, description)``

.. list-table::
   :widths: 25 25
   :header-rows: 1

    * - Attributes
      - Methods
    * - shop
      -
    * - currency
      -
    * - footer
      -
    * - description
      -
    * - shop
      -
    * - shop
      -

Represents a shop. This class is used to store the global configuration of the shop.

A number of options can be passed to the :ref:`Shop`.

**Parameters**:
    - title (str) - The global title of the store.
    - currency (str) - The global currency used to display the prices of items.
    - description (Optional[str]) - The global description of the store.
    - footer (Optional[str]) - The global footer text for all underlying :ref:`ShopPage`.

Pages
-----
``class shopipy.ShopPage(shop, description, items, footer, on_select, timeout)``

Selectors
---------


.. toctree::
    :maxdepth: 3
    :caption: Table of Contents:
