# Divar Product Details Fetch API

This API retrieves detailed information from a single product page on Divar using a page tag, returning specific data fields in a structured JSON format. It’s ideal for applications that need to programmatically access individual product details from Divar listings.

## Overview

This project provides an API endpoint to fetch product details from Divar using a unique page tag. Given a valid `tag` parameter, the API requests product data from Divar’s backend API and returns relevant information in JSON format.

## API Endpoint

To use this API, send a GET request with a `tag` parameter to the following endpoint:

```
https://divar-page-info.sideco.ir/?tag=<page-tag>
```

### Example

For a Divar product page URL like:
```
https://divar.ir/v/207-%DA%AF%DB%8C%D8%B1%D8%A8%DA%A9%D8%B3-%D8%A7%D8%AA%D9%88%D9%85%D8%A7%D8%AA%DB%8C%DA%A9/gZTHQDZy
```

The page tag is `gZTHQDZy`, so the API request URL will be:
```
https://divar-page-info.sideco.ir/?tag=gZTHQDZy
```

## Request Parameter

- **tag** (required): The unique identifier for a Divar product page. It should be extracted from the Divar URL.

## Response Format

The API returns JSON data in the following structure:

```json
[
  {
    "title": "کارکرد",
    "value": "۱"
  },
  {
    "title": "مدل (سال تولید)",
    "value": "۱۴۰۳"
  },
  {
    "title": "رنگ",
    "value": "مشکی"
  },
  {
    "title": "برند و تیپ",
    "value": "پژو 207i اتوماتیک"
  },
  ...
]
```

Each object in the array represents a key detail about the product, with a `title` and corresponding `value`.

## Error Handling

The API handles common errors with the following responses:

- **400 Bad Request**: Returned if the `tag` parameter is missing.
  ```json
  { "error": "Error: tag not provided in URL" }
  ```

- **500 Internal Server Error**: Returned if there’s an issue with fetching data from Divar’s backend.
  ```json
  { "error": "Error fetching data" }
  ```

## Example Usage

With a tool like `curl`, you can fetch data for a single Divar product page tag as follows:

```bash
curl "https://divar-page-info.sideco.ir/?tag=gZTHQDZy"
```

Or integrate the endpoint in your application to retrieve structured data from Divar product listings.

## License

This project is licensed under the MIT License.
