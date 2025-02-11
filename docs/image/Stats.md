# Image Stats

###### ENDPOINTS

```http
GET /api/image/stats.php
```

###### PARAMETERS

| Field    | Type    | Description                                                                                            | Required | Default |
|----------|---------|--------------------------------------------------------------------------------------------------------|----------|---------|
| division | string  | [Division](https://github.com/matthewzring/cyberpatriot-api-docs/blob/main/docs/Reference.md#division) | false    | Any     |
| tier     | string  | [Tier](https://github.com/matthewzring/cyberpatriot-api-docs/blob/main/docs/Reference.md#tier)         | false    | Any     |
| image    | string  | [Image name](https://github.com/matthewzring/cyberpatriot-api-docs/blob/main/docs/Reference.md#image)  | false    | Any     |

###### EXAMPLE REQUEST

```bash
curl https://scoreboard.uscyberpatriot.org/api/image/stats.php \
  -d "division[]"=All \
  -d "tier[]"=All \
  -d "image[]"=All \
  -G
```

###### THE IMAGE STATS OBJECT

```json
{
  "data": [
    {
      "division": "All Divisions",
      "tier": "All Tiers",
      "image": "All Images",
      "teams": 960,
      "images": 2431,
      "min_score": -11,
      "max_score": 90,
      "std_dev": "15.41",
      "avg_score": "26.84"
    }
  ]
}
```

###### ATTRIBUTES

| Field          | Type                  | Description                                                                                            |
|----------------|-----------------------|--------------------------------------------------------------------------------------------------------|
| data           | array of dictionaries |                                                                                                        |
| data.division  | string                | [Division](https://github.com/matthewzring/cyberpatriot-api-docs/blob/main/docs/Reference.md#division) |
| data.tier      | string                | [Tier](https://github.com/matthewzring/cyberpatriot-api-docs/blob/main/docs/Reference.md#tier)         |
| data.image     | string                | [Image name](https://github.com/matthewzring/cyberpatriot-api-docs/blob/main/docs/Reference.md#image)  |
| data.teams     | integer               | Number of teams                                                                                        |
| data.images    | integer               | Number of images                                                                                       |
| data.min_score | integer               | Minimum score                                                                                          |
| data.max_score | integer               | Maximum score                                                                                          |
| data.std_dev   | string                | Standard deviation                                                                                     |
| data.avg_score | string                | Average score                                                                                          |
