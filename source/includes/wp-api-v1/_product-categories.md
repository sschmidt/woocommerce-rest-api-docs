# Product - Categories #

This section lists all API endpoints that can be used to create, edit or otherwise manipulate product categories.

## Product Category Properties ##

|   Attribute   |   Type  |                                                   Description                                                   |
|---------------|---------|-----------------------------------------------------------------------------------------------------------------|
| `id`          | integer | Unique identifier for the resource. <i class="label label-info">read-only</i>                                   |
| `name`        | string  | Category name. <i class="label label-info">required</i>                                                         |
| `slug`        | string  | An alphanumeric identifier for the resource unique to its type.                                                 |
| `parent`      | integer | The id for the parent of the resource.                                                                          |
| `description` | string  | HTML description of the resource.                                                                               |
| `display`     | string  | Category archive display type. Default is `default`. Options: `default`, `products`, `subcategories` and `both` |
| `image`       | string  | Image URL.                                                                                                      |
| `menu_order`  | integer | Menu order, used to custom sort the resource.                                                                   |
| `count`       | integer | Number of published products for the resource. <i class="label label-info">read-only</i>                        |

## Create a Product Category ##

This API helps you to create a new product category.

### HTTP Request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v1/products/categories</h6>
	</div>
</div>

> Example of how to create a product category:

```shell
curl -X POST https://example.com/wp-json/wc/v1/products/categories \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "name": "Clothing"
}'
```

```javascript
var data = {
  name: 'Clothing'
};

WooCommerce.post('products/categories', data, function(err, data, res) {
  console.log(res);
});
```

```php
<?php
$data = [
    'name' => 'Clothing'
];

print_r($woocommerce->post('products/categories', $data));
?>
```

```python
data = {
    "name": "Clothing"
}

print(wcapi.post("products/categories", data).json())
```

```ruby
data = {
  name: "Clothing"
}

woocommerce.post("products/categories", data).parsed_response
```

> JSON response example:

```json
{
  "id": 9,
  "name": "Clothing",
  "slug": "clothing",
  "parent": 0,
  "description": "",
  "display": "default",
  "image": "",
  "menu_order": 0,
  "count": 12,
  "_links": {
    "self": [
      {
        "href": "https://example.com/wp-json/wc/v1/products/categories/9"
      }
    ],
    "collection": [
      {
        "href": "https://example.com/wp-json/wc/v1/products/categories"
      }
    ]
  }
}
```

## View a Product Category ##

This API lets you retrieve a product category by ID.

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v1/products/categories/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v1/products/categories/9 \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get('products/categories/9', function(err, data, res) {
  console.log(res);
});
```

```php
<?php print_r($woocommerce->get('products/categories/9')); ?>
```

```python
print(wcapi.get("products/categories/9").json())
```

```ruby
woocommerce.get("products/categories/9").parsed_response
```

> JSON response example:

```json
{
  "id": 9,
  "name": "Clothing",
  "slug": "clothing",
  "parent": 0,
  "description": "",
  "display": "default",
  "image": "",
  "menu_order": 0,
  "count": 12,
  "_links": {
    "self": [
      {
        "href": "https://example.com/wp-json/wc/v1/products/categories/9"
      }
    ],
    "collection": [
      {
        "href": "https://example.com/wp-json/wc/v1/products/categories"
      }
    ]
  }
}
```

## View List of Product Categories ##

This API lets you retrieve all product categories.

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v1/products/categories</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v1/products/categories \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get('products/categories', function(err, data, res) {
  console.log(res);
});
```

```php
<?php print_r($woocommerce->get('products/categories')); ?>
```

```python
print(wcapi.get("products/categories").json())
```

```ruby
woocommerce.get("products/categories").parsed_response
```

> JSON response example:

```json
[
  {
    "id": 15,
    "name": "Albums",
    "slug": "albums",
    "parent": 11,
    "description": "",
    "display": "default",
    "image": "",
    "menu_order": 0,
    "count": 4,
    "_links": {
      "self": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories/15"
        }
      ],
      "collection": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories"
        }
      ],
      "up": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories/11"
        }
      ]
    }
  },
  {
    "id": 9,
    "name": "Clothing",
    "slug": "clothing",
    "parent": 0,
    "description": "",
    "display": "default",
    "image": "",
    "menu_order": 0,
    "count": 12,
    "_links": {
      "self": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories/9"
        }
      ],
      "collection": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories"
        }
      ]
    }
  },
  {
    "id": 10,
    "name": "Hoodies",
    "slug": "hoodies",
    "parent": 9,
    "description": "",
    "display": "default",
    "image": "",
    "menu_order": 0,
    "count": 6,
    "_links": {
      "self": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories/10"
        }
      ],
      "collection": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories"
        }
      ],
      "up": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories/9"
        }
      ]
    }
  },
  {
    "id": 11,
    "name": "Music",
    "slug": "music",
    "parent": 0,
    "description": "",
    "display": "default",
    "image": "",
    "menu_order": 0,
    "count": 7,
    "_links": {
      "self": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories/11"
        }
      ],
      "collection": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories"
        }
      ]
    }
  },
  {
    "id": 12,
    "name": "Posters",
    "slug": "posters",
    "parent": 0,
    "description": "",
    "display": "default",
    "image": "",
    "menu_order": 0,
    "count": 5,
    "_links": {
      "self": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories/12"
        }
      ],
      "collection": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories"
        }
      ]
    }
  },
  {
    "id": 13,
    "name": "Singles",
    "slug": "singles",
    "parent": 11,
    "description": "",
    "display": "default",
    "image": "",
    "menu_order": 0,
    "count": 3,
    "_links": {
      "self": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories/13"
        }
      ],
      "collection": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories"
        }
      ],
      "up": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories/11"
        }
      ]
    }
  },
  {
    "id": 14,
    "name": "T-shirts",
    "slug": "t-shirts",
    "parent": 9,
    "description": "",
    "display": "default",
    "image": "",
    "menu_order": 0,
    "count": 6,
    "_links": {
      "self": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories/14"
        }
      ],
      "collection": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories"
        }
      ],
      "up": [
        {
          "href": "https://example.com/wp-json/wc/v1/products/categories/9"
        }
      ]
    }
  }
]
```

#### Available Parameters ####

|  Parameter   |   Type  |                                                                Description                                                                 |
|--------------|---------|--------------------------------------------------------------------------------------------------------------------------------------------|
| `context`    | string  | Scope under which the request is made; determines fields present in response. Options: `view` and `edit`.                                  |
| `page`       | integer | Current page of the collection.                                                                                                            |
| `per_page`   | integer | Maximum number of items to be returned in result set.                                                                                      |
| `search`     | string  | Limit results to those matching a string.                                                                                                  |
| `exclude`    | string  | Ensure result set excludes specific ids.                                                                                                   |
| `include`    | string  | Limit result set to specific ids.                                                                                                          |
| `order`      | string  | Order sort attribute ascending or descending. Default is `asc`. Options: `asc` and `desc`.                                                 |
| `orderby`    | string  | Sort collection by object attribute. Default is `name`. Options: `id`, `include`, `name`, `slug`, `term_group`, `description` and `count`. |
| `hide_empty` | bool    | Whether to hide resources not assigned to any products. Default is `false`.                                                                |
| `parent`     | integer | Limit result set to resources assigned to a specific parent.                                                                               |
| `product`    | integer | Limit result set to resources assigned to a specific product.                                                                              |
| `slug`       | string  | Limit result set to resources with a specific slug.                                                                                        |

## Update a Product Category ##

This API lets you make changes to a product category.

### HTTP Request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-put">PUT</i>
		<h6>/wp-json/wc/v1/products/categories/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X PUT https://example.com/wp-json/wc/v1/products/categories/9 \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "product_category": {
    "description": "All kinds of clothes."
  }
}'
```

```javascript
var data = {
  product_category: {
    description: 'All kinds of clothes.'
  }
};

WooCommerce.put('products/categories/9', data, function(err, data, res) {
  console.log(res);
});
```

```php
<?php
$data = [
    'product_category' => [
        'description' => 'All kinds of clothes.'
    ]
];

print_r($woocommerce->put('products/categories/9', $data));
?>
```

```python
data = {
    "product_category": {
        "description": "All kinds of clothes."
    }
}

print(wcapi.put("products/categories/9", data).json())
```

```ruby
data = {
  product_category: {
    description: "All kinds of clothes."
  }
}

woocommerce.put("products/categories/9", data).parsed_response
```

> JSON response example:

```json
{
  "id": 9,
  "name": "Clothing",
  "slug": "clothing",
  "parent": 0,
  "description": "All kinds of clothes.",
  "display": "default",
  "image": "",
  "menu_order": 0,
  "count": 12,
  "_links": {
    "self": [
      {
        "href": "https://example.com/wp-json/wc/v1/products/categories/9"
      }
    ],
    "collection": [
      {
        "href": "https://example.com/wp-json/wc/v1/products/categories"
      }
    ]
  }
}
```

## Delete a Product Category ##

This API helps you delete a product category.

### HTTP Request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-delete">DELETE</i>
		<h6>/wp-json/wc/v1/products/categories/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X DELETE https://example.com/wp-json/wc/v1/products/categories/9?force=true \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.delete('products/categories/9?force=true', function(err, data, res) {
  console.log(res);
});
```

```php
<?php print_r($woocommerce->delete('products/categories/9', ['force' => true])); ?>
```

```python
print(wcapi.delete("products/categories/9?force=true").json())
```

```ruby
woocommerce.delete("products/categories/9", force: true).parsed_response
```

> JSON response example:

```json
{
  "id": 9,
  "name": "Clothing",
  "slug": "clothing",
  "parent": 0,
  "description": "All kinds of clothes.",
  "display": "default",
  "image": "",
  "menu_order": 0,
  "count": 12,
  "_links": {
    "self": [
      {
        "href": "https://example.com/wp-json/wc/v1/products/categories/9"
      }
    ],
    "collection": [
      {
        "href": "https://example.com/wp-json/wc/v1/products/categories"
      }
    ]
  }
}
```

#### Available Parameters ####

| Parameter |  Type  |                          Description                          |
|-----------|--------|---------------------------------------------------------------|
| `force`   | string | Required to be `true`, as resource does not support trashing. |

## Create/Update/Delete Multiple Product Categories ##

This API helps you to batch create, update and delete multiple product categories.

### HTTP Request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v1/products/categories/batch</h6>
	</div>
</div>

```shell
curl -X POST https://example.com//wp-json/wc/v1/products/categories/batch \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "create": [
    {
      "name" => "Albums"
    },
    {
      "name" => "Clothing"
    }
  ],
  "update": [
    {
      "id": 10,
      "description": "Nice hoodies"
    }
  ],
  "delete": [
    11,
    12
  ]
}'
```

```javascript
var data = {
  create: [
    {
      name: 'Albums'
    },
    {
      name: 'Clothing'
    }
  ],
  update: [
    {
      id: 10,
      description: 'Nice hoodies'
    }
  ],
  delete: [
    11,
    12
  ]
};

WooCommerce.post('products/categories/batch', data, function(err, data, res) {
  console.log(res);
});
```

```php
<?php
$data = [
    'create' => [
        [
            'name' => 'Albums'
        ],
        [
            'name' => 'Clothing'
        ]
    ],
    'update' => [
        [
            'id' => 10,
            'description' => 'Nice hoodies'
        ]
    ],
    'delete' => [
        11,
        12
    ]
];

print_r($woocommerce->post('products/categories/batch', $data));
?>
```

```python
data = {
    "create": [
        {
            "name": "Albums"
        },
        {
            "name": "Clothing"
        }
    ],
    "update": [
        {
            "id": 10,
            "description": "Nice hoodies"
        }
    ],
    "delete": [
        11,
        12
    ]
}

print(wcapi.post("products/categories/batch", data).json())
```

```ruby
data = {
  create: [
    {
      name: "Albums"
    },
    {
      name: "Clothing"
    }
  ],
  update: [
    {
      id: 10,
      description: "Nice hoodies"
    }
  ],
  delete: [
    11,
    12
  ]
}

woocommerce.post("products/categories/batch", data).parsed_response
```

> JSON response example:

```json
{
  "create": [
    {
      "id": 15,
      "name": "Albums",
      "slug": "albums",
      "parent": 11,
      "description": "",
      "display": "default",
      "image": "",
      "menu_order": 0,
      "count": 0,
      "_links": {
        "self": [
          {
            "href": "https://example.com/wp-json/wc/v1/products/categories/15"
          }
        ],
        "collection": [
          {
            "href": "https://example.com/wp-json/wc/v1/products/categories"
          }
        ],
        "up": [
          {
            "href": "https://example.com/wp-json/wc/v1/products/categories/11"
          }
        ]
      }
    },
    {
      "id": 9,
      "name": "Clothing",
      "slug": "clothing",
      "parent": 0,
      "description": "",
      "display": "default",
      "image": "",
      "menu_order": 0,
      "count": 0,
      "_links": {
        "self": [
          {
            "href": "https://example.com/wp-json/wc/v1/products/categories/9"
          }
        ],
        "collection": [
          {
            "href": "https://example.com/wp-json/wc/v1/products/categories"
          }
        ]
      }
    }
  ],
  "update": [
    {
      "id": 10,
      "name": "Hoodies",
      "slug": "hoodies",
      "parent": 9,
      "description": "Nice hoodies",
      "display": "default",
      "image": "",
      "menu_order": 0,
      "count": 6,
      "_links": {
        "self": [
          {
            "href": "https://example.com/wp-json/wc/v1/products/categories/10"
          }
        ],
        "collection": [
          {
            "href": "https://example.com/wp-json/wc/v1/products/categories"
          }
        ],
        "up": [
          {
            "href": "https://example.com/wp-json/wc/v1/products/categories/9"
          }
        ]
      }
    }
  ],
  "delete": [
    {
      "id": 11,
      "name": "Music",
      "slug": "music",
      "parent": 0,
      "description": "",
      "display": "default",
      "image": "",
      "menu_order": 0,
      "count": 7,
      "_links": {
        "self": [
          {
            "href": "https://example.com/wp-json/wc/v1/products/categories/11"
          }
        ],
        "collection": [
          {
            "href": "https://example.com/wp-json/wc/v1/products/categories"
          }
        ]
      }
    },
    {
      "id": 12,
      "name": "Posters",
      "slug": "posters",
      "parent": 0,
      "description": "",
      "display": "default",
      "image": "",
      "menu_order": 0,
      "count": 5,
      "_links": {
        "self": [
          {
            "href": "https://example.com/wp-json/wc/v1/products/categories/12"
          }
        ],
        "collection": [
          {
            "href": "https://example.com/wp-json/wc/v1/products/categories"
          }
        ]
      }
    }
  ]
}
```