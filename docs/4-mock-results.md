# Mock Results

If you want to test your implementation of the BestExits API without using up the public rate limit and before you request an API key, you can make a small change to your API requests to make this easier.

By adding the `mock` query parameter to your request URL, you will receive a static request that doesn't count towards any rate limit.

Please note that certain restrictions are in place for mock requests, as outlined below:
- If an `api_key` parameter is provided, the `mock` parameter is ignored and a normal request is processed.
- All other requests parameters are ignored, and a set of default parameters are used, which you can find below.
- All responses are static, so the same information will always be returned with every mock request. You can find these responses below.

## Default parameters
| Parameter    | Value used    |
| ------------ | ------------- |
| station_id   | 940GZZLUOXC   |
| previous_id  | 940GZZLUTCR   |
| terminal_id  | 940GZZLUWRP   |
| line         | central       |

## Responses
### /platform/predict
<!--
title: "Response returned"
lineNumbers: true
-->
```json
{
  "success": true,
  "platforms": [
    "1"
  ],
  "direction": "westbound"
}
```


### /platform/exits
<!--
title: "Response returned"
lineNumbers: true
-->
```json
{
  "success": true,
  "platform": "1",
  "direction": "westbound",
  "side": "right",
  "exits": [
    {
      "name": "Oxford Street / Regent Street",
      "sections": [
        "middle"
      ],
      "carriage": 4,
      "door": 2,
      "notices": []
    }
  ]
}
```


### /platform/interchanges
<!--
title: "Response returned"
lineNumbers: true
-->
```json
{
  "success": true,
  "platform": "1",
  "direction": "westbound",
  "side": "right",
  "exits": [
    {
      "interchange": {
        "lines": [
          "bakerloo",
          "victoria"
        ],
        "direction": null
      },
      "sections": [
        "front"
      ],
      "carriage": 1,
      "door": 1,
      "notices": []
    }
  ]
}
```