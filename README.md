
---

# Amazon API Forked

This is a fork of the official Product Advertising API 5.0 Python SDK, referred to as **paapi5_python_sdk**. The original repository was missing the models library, which is essential for working with the PAAPI effectively. This fork includes the necessary models to enhance functionality.

![pypi](https://img.shields.io/pypi/v/amazon-api-forked.svg)

## Requirements

- Python 3.4+

## Installation

You can install the package directly from PyPI using pip:

```sh
pip install amazon-api-forked
```

Or, if you prefer to install directly from GitHub:

```sh
pip install git+https://github.com/LeilaSchooley/amazon-api-forked.git
```

## Usage

Import the package in your Python script:

```python
import paapi5_python_sdk
```

### Example

Here’s a simple example of how to use the API to search for items:

```python
from paapi5_python_sdk import DefaultApi, SearchItemsRequest, SearchItemsResource, PartnerType

def search_items():
    access_key = "<YOUR ACCESS KEY>"
    secret_key = "<YOUR SECRET KEY>"
    partner_tag = "<YOUR PARTNER TAG>"
    host = "webservices.amazon.com"
    region = "us-east-1"

    api = DefaultApi(access_key=access_key, secret_key=secret_key, host=host, region=region)

    request = SearchItemsRequest(
        partner_tag=partner_tag,
        partner_type=PartnerType.ASSOCIATES,
        keywords="Harry Potter",
        search_index="All",
        item_count=1,
        resources=[SearchItemsResource.IMAGES_PRIMARY_LARGE, SearchItemsResource.ITEMINFO_TITLE]
    )

    response = api.search_items(request)

    print(response)

search_items()
```

## License

This SDK is distributed under the [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0). See LICENSE.txt for more information.

---

 