# Google Images Scraper

[<img width="950" height="300" alt="Google Image scraper" src="https://github.com/user-attachments/assets/49dda963-7143-4985-895a-9c7d2090d9b4" />](https://serpapi.com/google-images-api?utm_source=github_google_images_scraper)

Google Images Scraper - A tool to scrape Google Images search results with a simple API. Get image information like URLs, dimensions, source, title, and more.

We provide the results in a structured JSON format, eliminating the need for parsing, coding, proxies, or any other web scraping headaches for developers.

## How to scrape Google Images?

Using a simple GET request, you can retrieve Google Images search results:

```
https://serpapi.com/search.json?engine=google_images&q=Coffee&api_key=YOUR_API_KEY
```

- Register for free at [SerpApi to get your API Key](https://serpapi.com?utm_source=github_google_images_scraper)
- `q` parameter: defines the search query you want to search on Google Images.
- `gl` parameter (optional): defines the country code for localized results.

## Code examples
Here are some code examples based on your favorite programming languages.

### cURL Integration

``` bash
curl --get https://serpapi.com/search \
 -d engine="google_images" \
 -d q="Coffee" \
 -d api_key="secret_api_key"
```

### Python Integration

Step 1:
Create a new `main.py` file.

Step 2:
Install [requests package](https://pypi.org/project/requests/) with:
```
pip install requests
```

Step 3:
Add this code to your file:
``` py
import requests
SERPAPI_API_KEY = "YOUR_SERPAPI_API_KEY"

params = {
    "api_key": SERPAPI_API_KEY,
    "engine": "google_images",
    "q": "coffee"
}

search = requests.get("https://serpapi.com/search", params=params)
response = search.json()
print(response)
```

If you're only interested in the `images_results`, you can print them from the response directly:

``` py
print(response["images_results"])
```

### JavaScript Integration

Step 1:
Install the [SerpApi JavaScript package](https://github.com/serpapi/serpapi-javascript):
```
npm install serpapi
```

Step 2:
Create a new `index.js` file.

Step 3:
Add this to your file:
``` js
const { getJson } = require("serpapi");
getJson({
  api_key: API_KEY,
  engine: "google_images",
  q: "coffee"
}, (json) => {
  console.log(json["images_results"]);
});
```

### Other Programming Languages
While you can use our APIs using a simple GET request with any programming language, you can also see our ready-to-use libraries here: [SerpApi Integrations](https://serpapi.com/integrations?utm_source=github_google_images_scraper).

## Google Images Scraper Parameters
Please find the parameters for the Google Images API below:

| Name           | Description                                                                                                                                      | Requirement |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| q              | Parameter defines the search query. Supports advanced operators like `inurl:`, `site:`, `intitle:`                                               | Required    |
| **Localization**   |                                                                                                                                              |             |
| location       | Parameter defines the search origin location                                                                                                     | Optional    |
| google_domain  | Parameter defines the Google domain to use. Defaults to `google.com`                                                                             | Optional    |
| gl             | Parameter defines the two-letter country code                                                                                                    | Optional    |
| hl             | Parameter defines the two-letter language code                                                                                                   | Optional    |
| **Filters**        |                                                                                                                                              |             |
| imgar          | Parameter defines aspect ratio: `s` (square), `t` (tall), `w` (wide), `xw` (panoramic)                                                           | Optional    |
| imgsz          | Parameter defines image size filters: `l` (large), `m` (medium), `i` (icon)                                                                      | Optional    |
| image_color    | Parameter defines color filtering: `bw`, `red`, `blue`, etc.                                                                                     | Optional    |
| image_type     | Parameter defines type filters: `face`, `photo`, `clipart`, `lineart`, `animated`                                                                | Optional    |
| safe           | Parameter defines adult content filtering: `active` or `off`                                                                                     | Optional    |
| **Time Period**    |                                                                                                                                              |             |
| period_unit    | Parameter defines time unit: `s`, `n`, `h`, `d`, `w`, `m`, `y`                                                                                   | Optional    |
| period_value   | Parameter defines duration value                                                                                                                 | Optional    |
| **Pagination**     |                                                                                                                                              |             |
| ijn            | Parameter defines the page number (0-99)                                                                                                         | Optional    |
| **Advanced**       |                                                                                                                                              |             |
| device         | Parameter defines the device: `desktop` (default), `tablet`, or `mobile`                                                                         | Optional    |

Visit [our documentation](https://serpapi.com/google-images-api) for more information on all available parameters.


## Available data on Google Images (JSON Response)
Google Images can return different information from time to time. Here is what the `images_results` array may contain:

``` json
 "images_results": [
    {
      "position": "Integer - Position of the image in results",
      "thumbnail": "String - URL to the thumbnail preview",
      "original": "String - URL to the full-resolution image",
      "original_width": "Integer - Width of the original image",
      "original_height": "Integer - Height of the original image",
      "title": "String - Image title/description",
      "source": "String - Source website domain",
      "link": "String - URL to the source webpage",
      "is_product": "Boolean - Whether the image is a product",
      "related_content_id": "String - ID for fetching related images",
      "license_details_url": "String - URL to license information"
    }
  ],
```

The API response also includes:
- `shopping_results`: Product listings with prices and ratings
- `suggested_searches`: Filter suggestions with thumbnails
- `related_searches`: Query variations with highlighted keywords
- `serpapi_pagination`: Navigation links for result pages

## Use cases
Here are some use cases for the Google Images API:

- Build image dataset creators for machine learning projects.
- Create visual content research tools for marketing and design.
- Monitor brand images and logos across the web.
- Build reverse image search applications.
- Create wallpaper or stock photo aggregation tools.
- Research visual trends for content strategy.

## Blog tutorial
- [How to Scrape Google Images Results](https://serpapi.com/blog/how-to-scrape-google-images-results/)
- [Scrape and download Google Images with Python](https://serpapi.com/blog/scrape-google-images-with-python/)
- [Web Scraping Google Images with Nodejs](https://serpapi.com/blog/web-scraping-google-images-with-nodejs/)

Interesting use cases:
- [Open Source AI Image Classifier with Automatic Dataset Creator](https://serpapi.com/blog/open-source-ai-image-classifier-with-automatic-dataset-creator/)
- [Scrape Google Images to Create Custom Database with SerpApi](https://serpapi.com/blog/custom-dataset-creator-with-serpapi/)
- [Get images you can (legally) use without any charge](https://serpapi.com/blog/get-images-you-can-use-without-any-charge/)

## Video tutorial
- [Web scraping Google Images with Python and simple API (+ export to CSV)](https://www.youtube.com/watch?v=Y8RmgLb7ra0)

## Contacts
Feel free to reach out via `contact@serpapi.com`.

Check other [Google Scrapers](https://github.com/serpapi/google-scraper) from SerpApi.
