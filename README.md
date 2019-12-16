# venture-theme-mods
Modifications to the Shopify Venture Theme for use in my online t-shirt stores

## Feature Branch **related-product-types**

Adds functionality to display related product styles on a product page.  This feature is useful for product designs that are offered on multiple apparel types, e.g., a single design that apprears on t-shirts, long-sleeve t-shirts, and hoodies - but could also be used to bundle products - although that is not what I am using it for, the coding is the same. The product page file sections/product-template.liquid has an added section below the payment buttons that will display the related products if there are any to display. If the user clicks on the image, they will be taken to the product page.

**Relevent Code**

sections/product-template.liquid

I've added a block of code beginning at line 206 that looks at a product's metafields attribute for a namespace called 'related-products'. If the product has this namespace then I assume the product has other related products associated with it, and then I call the snippets/related-product-types.liquid

snippets/related-product-types.liquid

This liquid code snippet builds a list of product URLs from the product handles from each of the entries contained in the 'related-products' attribute and displays them on the product page

**Addng Meta Data For Related Products**

Meta data must be added to each of your products that you want to have related products. I'm using the Shopify app MetaFields Editor, but you can use any app that allows you to add meta data to your products.

For each product that will have related products add the following meta fields:

| Namespace        | Key             | Value Type | Value                  | Notes                                       |
|:-----------------|:----------------|:-----------|:-----------------------|:--------------------------------------------|
| related-products | handle-x        | string     | the product handle     | where x is a sequential number starting at 1|

Exampe:

For product handle **chronic-zone-hooded-sweatshirt**, which is a hoodie, I also want to display a t-shirt and long sleeve t-shirt on the hoodie's product page. So I need to add product handles for both the t-shirt and long-sleeve t-shirt to the hoodies meta data. So the hoodies meta data will look like the following - note there will be 2 meta data entries because we want to relate 2 products:

| Namespace        | Key             | Value Type | Value                  |
|:-----------------|:----------------|:-----------|:-----------------------|
| related-products | handle-1        | string     | chronic-zone-long-sleeve-t-shirt     |
| related-products | handle-2        | string     | chronic-zone-short-sleeve-unisex-t-shirt |

Now for product handles *chronic-zone-long-sleeve-t-shirt* and *chronic-zone-short-sleeve-unisex-t-shirt*, add similar meta data. For exmple, product handle **chronic-zone-long-sleeve-t-shirt** should look like the following:

| Namespace        | Key             | Value Type | Value                  |
|:-----------------|:----------------|:-----------|:-----------------------|
| related-products | handle-1        | string     | chronic-zone-hooded-sweatshirt     |
| related-prodcuts | handle-2        | string     | chronic-zone-short-sleeve-unisex-t-shirt |



