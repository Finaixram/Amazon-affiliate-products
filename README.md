# amazon-affiliate-products

Single source of truth for Amazon India affiliate product links used across finaixram.github.io and YouTube video descriptions.

## Schema (products.json)

Array of objects:

| field    | type   | notes |
|----------|--------|-------|
| asin     | string | Amazon ASIN (10-char product id) |
| title    | string | Product name as shown on Amazon |
| price    | number | Price in INR at time of adding (not auto-updated) |
| category | string | Free text, e.g. "Baby", "Beauty", "Toys" |
| tag      | string | Amazon Associates tracking ID used in the link |
| image    | string | Product image URL (from Amazon's media-amazon.com CDN) |
| url      | string | Full tagged Amazon.in affiliate link, ready to use |

## Adding a product

1. Get the product's Amazon.in page and generate a tagged link (SiteStripe on desktop, or "Copy Associates Link" in the Amazon app).
2. 2. Grab the main product image URL (right-click the product photo on Amazon and copy image address, or inspect the page for the media-amazon.com image src).
   3. 3. Append a new object to the array in products.json with the fields above.
      4. 4. Commit. Nothing else auto-syncs yet - if the product also needs to appear on finaixram.github.io, that section is currently hardcoded in index.html over in the finaixram.github.io repo, so update it there too.
        
         5. No build step, no framework - just edit the JSON.
