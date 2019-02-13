# venture-theme-mods
Modifications to the Venture Theme for use in my online t-shirt stores

##h2 Feature Branch related-product-types

Adds functionality to display related product styles on a product page.  This feature is useful for product designs that are offered on multiple apparel types, e.g., a single design that apprears on t-shirts, long-sleeve t-shirts, and hoodies - but could also be used to bundle products - although that is not what I am using it for, the coding is the same. The product page file sections/product-template.liquid has an added section below the payment buttons that will display the related products if there are any to display. If the user clicks on the image, they will be taken to the product page.

Meta data must be added to each of you products that you want to have related products. I'm using the Shopify app MetaFields Editor, but you can use any app that allows you to add meta data to your products.

For each product that will have related products add the following meta fields:

Namespace:    related-products
Key:          handle-x - where x is a sequential number starting at 1
Value Type:   string
Value:        the product handle

Exampe:

For product handle chronic-zone-hooded-sweatshirt, which is a hoodie, I also want to display a t-shirt and long sleeve t-shirt on the hoodie's product page. So I need to add product handles for both the t-shirt and long-sleeve t-shirt to the hoodies meta data. So the hoodies meta data will look like the following - note there will be 2 meata data entries because we want to relate 2 products:

Namespace:    related-products
Key:          handle-1
Value Type:   string
Value:        chronic-zone-long-sleeve-t-shirt

Namesapce:    related-products
Key:          handle-2
Value Type:   string
Value:        chronic-zone-short-sleeve-unisex-t-shirt

Now for product handles chronic-zone-long-sleeve-t-shirt and chronic-zone-short-sleeve-unisex-t-shirt, add similar meta data. For exmple, product handle chronic-zone-long-sleeve-t-shirt should look like the following:

Namespace:    related-products
Key:          handle-1
Value Type:   string
Value:        chronic-zone-short-sleeve-unisex-t-shirt

Namesapce:    related-products
Key:          handle-2
Value Type:   string
Value:        chronic-zone-short-sleeve-unisex-t-shirt


