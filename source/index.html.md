---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - python

toc_footers:
  - Recruitology Platform API v1

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Recruitology Platform API
---

# Introduction

Welcome to the Recruitology Platform API! You can use our API to access Recruitology API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use your Platform API Key in the header of your request:

```curl
# Example curl request, passing the correct header with each request
curl "api_endpoint_here" \
  -H "X-Platform-Api-Key: PLATFORM_API_KEY"
```

> Make sure to replace `PLATFORM_API_KEY` with your API key.

Recruitology uses API keys to allow access to the API. You may request one from us directly.

Recruitology expects for the API key to be included in all API requests to the server in a header that looks like the following:

`X-Platform-Api-Key: PLATFORM_API_KEY`

<aside class="notice">
You must replace <code>PLATFORM_API_KEY</code> with your own Platform API key.
</aside>

# Companies

## List Companies

```python
import requests

headers = { "X-Platform-Api-Key: PLATFORM_API_KEY" }
url = 'https://platform.recruitology.com/api/platform/v1/company/'
response = requests.get(url, **headers)
print(response)
```

```shell
curl "https://platform.recruitology.com/api/platform/v1/company/" \
  -H "X-Platform-Api-Key: YOUR_RECRUITOLOGY_PLATFORM_API_KEY"
```


> The above command returns JSON structured like this:

```json
{
   "count": 1,
   "next": NULL,
   "previous": NULL,
   "results":[
      {
        "partnerId": 1,
        "companyName": "Test Company",
        "partnerCompanyId": "1",
        "companyUrl": "https://company.recruitology.com",
        "companyStreet": "98 Battery St",
        "companyCity": "San Francisco",
        "companyState": "CA",
        "companyZipCode": "94111",
        "companyLogo": "https://company.recruitology.com/logo.png",
        "salesRep": {
          "firstName": "Sales",
          "lastName": "Rep",
          "email": "sales_rep@recruitology.com"
        },
        "companyContact": {
          "firstName": "Company",
          "lastName": "Contact",
          "email": "company_contact@recruitology.com"
        }
      }
   ]
}
```

This endpoint retrieves all companies.

### HTTP Request

`GET https://platform.recruitology.com/api/platform/v1/company/`

### Query Parameters

Parameter | Required | Default | Description
--------- | ------- | ----------- | -----------
offset | false | 0 | How many items to skip for pagination; e.g. 100 for page #2
page_size | false | 100 | Number of results to retrieve per API call

## Retrieve Company

```python
import requests

headers = { "X-Platform-Api-Key: PLATFORM_API_KEY" }
url = 'https://platform.recruitology.com/api/platform/v1/company/<ID>/'
response = requests.get(url, **headers)
print(response)
```

```shell
curl "https://platform.recruitology.com/api/platform/v1/company/<ID>/" \
  -H "X-Platform-Api-Key: YOUR_RECRUITOLOGY_PLATFORM_API_KEY"
```

> The above command returns JSON structured like this:

```json
{
  "partnerId": 1,
  "companyName": "Test Company",
  "partnerCompanyId": "1",
  "companyUrl": "https://company.recruitology.com",
  "companyStreet": "98 Battery St",
  "companyCity": "San Francisco",
  "companyState": "CA",
  "companyZipCode": "94111",
  "companyLogo": "https://company.recruitology.com/logo.png",
  "salesRep": {
    "firstName": "Sales",
    "lastName": "Rep",
    "email": "sales_rep@recruitology.com"
  },
  "companyContact": {
    "firstName": "Company",
    "lastName": "Contact",
    "email": "company_contact@recruitology.com"
  }
}
```

This endpoint retrieves a specific company.

### HTTP Request

`GET https://platform.recruitology.com/api/platform/v1/company/<ID>/`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the company to retrieve
