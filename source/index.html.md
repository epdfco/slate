---
title: ePDF API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='#'>Login to access API Key</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the ePDF API. You can use this API to create PDF's from your [PDF templates](https://app.epdf.co/pdf).

We are working on ePDF daily to make it faster and simpler. Feel free to reach out to the founder if you have any feedback or suggestions: volkan@epdf.co.

# Authentication

> Example Request:

```shell
# With shell, you can just pass the correct header with each request
curl https://api.epdf.co/v1/limit/ \
  -u example_API_key:
```

> Make sure to replace `example_API_key` with your API key.

Authentication to the API is performed using Basic Auth. Include your API key as the username. The password can be left blank. You can find your API Key on your [settings page](https://app.epdf.co/settings/profile).

<aside class="notice">
You must replace <code>example_API_key</code> with your API key.
</aside>

# Limit

## Get remaining amount of PDF's that can be created


```shell
curl https://api.epdf.co/v1/limit/ \
  -u example_API_key:
```

> The above command returns a simple JSON structured like this:

```json
{
    "remaining": 36
}
```

This endpoint retrieves all kittens.


### HTTP Request

`GET https://api.epdf.co/v1/limit/`


# Create PDF's

## Create Single PDF


```shell

curl https://api.epdf.co/v1/pdf/ \
  -u example_API_key: \
  -H "Content-Type: application/json" \
  -X POST \
  -d JSON_structure
```

> The above command requires a simple JSON structured like this:

```json
{
    "chart": {},
    "image": {},
    "table": {},
    "text": {"test_text": "working"},
    "pdf": {
        "filename": "testfile",
        "pdfId": "d5da1e6e-f48e-42d1-865b-07b06ffa5722"
    }
}
```

> To get the specfic JSON structure for a PDF go to the template mode at [PDF templates](https://app.epdf.co/pdf)

This endpoint creates a binary PDF file.

### HTTP Request

`POST https://api.epdf.co/v1/pdf/`


## Create Multiple PDF


```shell

curl https://api.epdf.co/v1/pdfs/ \
  -u example_API_key: \
  -H "Content-Type: application/json" \
  -X POST \
  -d JSON_structure
```

> The above command requires a simple JSON structured like this:

```json
[
    {
        "chart": {},
        "image": {},
        "table": {},
        "text": {"test_text": "working"},
        "pdf": {
            "filename": "testfile",
            "pdfId": "d5da1e6e-f48e-42d1-865b-07b06ffa5722"
        }
    },
    {
        "chart": {},
        "image": {},
        "table": {},
        "text": {"test_text": "working 2"},
        "pdf": {
            "filename": "testfile2",
            "pdfId": "d5da1e6e-f48e-42d1-865b-07b06ffa5722"
        }
    },
]
```

> To get the specfic JSON structure for a PDF go to the template mode at [PDF templates](https://app.epdf.co/pdfs/)

This endpoint creates a zip file containing multiple PDF's.

### HTTP Request

`POST https://api.epdf.co/v1/pdfs/`
