# opencart
API extension for integration with the warehouse program [ZStore] (http://zippy.com.ua/zstore).

The module allows you to receive orders from the store, update their statuses, send new products to the store (synchronization is performed by SKU), update prices and quantities from the store in the store

It can be used with other warehouse programs as well.

Compatible with Opencart 2.3 and 3.02


## Installation
 Installation is performed as usual by adding an extension on the admin page by downloading the zstore.ocmod.zip file.
 You can also install manually by copying the zstore.php file to the catalog \ controller \ api \ directory


 Authorization is done in the same way as with the built-in API.

## API Methods
* statuses ()
Returns a list of order statuses in the store
* orders ()
returns a list of orders according to the specified status. The status is passed by the status_id parameter (via POST, like everything else in the API)
* updateorder () Updates the status of orders in the store after processing in the warehouse. Passed into the data field as an array key value - opder_id => ststus_id
* articles () Getting a list of articles from the store to understand what products are already there
* cats () Returns a list of product categories
* addproducts () adds products from the warehouse to the store. The cat parameter contains the category to which you want to add the product,
the data parameter is an array of products. The name, article description, quantity and price are transmitted.
* updatequantity () Updates the number of items in the store. The data parameter passes the key-value array - product SKU => quantity
* updateprice () Updates the price of items in the store. The data parameter passes the key-value array - product SKU => price

* getproducts () Loads products from the store that are not in stock in case the products were added to the store first
* 
