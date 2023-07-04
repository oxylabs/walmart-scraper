# Walmart Scraper

[![Oxylabs promo code](https://user-images.githubusercontent.com/129506779/250792357-8289e25e-9c36-4dc0-a5e2-2706db797bb5.png)](https://oxylabs.go2cloud.org/aff_c?offer_id=7&aff_id=877&url_id=112)


Oxylabs’ Walmart Scraper is a scraping solution that allows you to effortlessly extract data from a Walmart website in real-time.
In this brief guide, we’ll detail how a Walmart Scraper works and provide code examples to better visualize how easy it's to use it.

### How it works

You can get Walmart results by providing your own URLs to our service. We can return the HTML for any Walmart page you like. Additionally, we can deliver **structured (parsed) output for Walmart product, search, and offer listing pages**.

#### Python code example

The example below illustrates how you can get a parsed Walmart product page result.

```python
import requests
from pprint import pprint

# Structure payload.
payload = {
    'source': 'universal_ecommerce',
    'url': 'https://www.walmart.com/ip/Adidas-Moves-Body-Spray-for-Men-2-5-Oz/710726462',
    'geo_location': 'United States',
    'parse': True,
}

# Get response.
response = requests.request(
    'POST',
    'https://realtime.oxylabs.io/v1/queries',
    auth=('user', 'pass1'),
    json=payload,
)

# Instead of response with job status and results url, this will return the
# JSON response with the result.
pprint(response.json())
```

Find code examples for other programming languages [**here**](https://github.com/oxylabs/walmart-scraper/tree/main/code%20examples)

#### Output Example
```json
{
    "results": [
        {
            "content": {
                "url": "https://www.walmart.com/ip/Adidas-Moves-Body-Spray-for-Men-2-5-Oz/710726462",
                "meta": {
                    "sku": "710726462",
                    "gtin": null
                },
                "price": 8.12,
                "title": "Adidas Moves Body Spray for Men, 2.5 Oz",
                "rating": {
                    "count": 0,
                    "rating": 0
                },
                "currency": "USD",
                "_warnings": [
                    "Could not determine if shipping is free. Perhaps no product variant is selected.",
                    "Could not parse seller info. Perhaps no product variant is selected."
                ],
                "breadcrumbs": [
                    "Beauty",
                    "Travel Size Beauty",
                    "Travel Size Fragrance",
                    "Travel Size Body Spray"
                ],
                "description": "<p>Adidas Moves for Him is an energetic, aromatic Fougere fragrance. It is invigorating, stimulating, and crisp for all the ways you play. Top notes of the men's fragrance include fresh green apple, anise, Italian parsley, peppermint, mandarin and black peppercorn. Heart notes include cedarwood, musk, lavender, and jasmine. Base notes include muguet, sandalwood, oakmoss, and thyme. Adidas Moves for Him: -Energetic and aromatic -Lasts longer than traditional applications -Provides all-day confidence</p>",
                "specifications": [
                    {
                        "key": "Body Spray Type",
                        "value": "Spray"
                    },
                    {
                        "key": "Gender",
                        "value": "Male"
                    },
                    {
                        "key": "Size",
                        "value": "2.5 oz"
                    },
                    {
                        "key": "Brand",
                        "value": "Adidas"
                    },
                    {
                        "key": "Manufacturer",
                        "value": "Hfc Prestige International Us Llc"
                    },
                    {
                        "key": "Assembled Product Dimensions (L x W x H)",
                        "value": "0.98 x 6.65 x 6.10 Inches"
                    }
                ],
                "parse_status_code": 12005
            },
            "created_at": "2022-11-17 14:42:27",
            "updated_at": "2022-11-17 14:42:31",
            "page": 1,
            "url": "https://www.walmart.com/ip/Adidas-Moves-Body-Spray-for-Men-2-5-Oz/710726462",
            "job_id": "6999018925149157377",
            "status_code": 200,
            "parser_type": "walmart_product"
        }
    ]
}
```

With our Walmart Scraper, you can easily extract publicly available data from any Walmart web page. Quickly access product prices, descriptions, reviews, and much more in real-time to gain a competitive edge.
If you have any questions or concerns, please feel free to contact our support team via live chat or [**email**](mailto:support@oxylabs.io).
