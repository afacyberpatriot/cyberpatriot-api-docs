# Image Scores

###### ENDPOINTS

```http
GET /image/scores.php
```

###### PARAMETERS

| Field | Type   | Description                                                                                                  | Required |
|-------|--------|--------------------------------------------------------------------------------------------------------------|----------|
| image | string | [Image name](https://github.com/matthewzring/cyberpatriot-api-docs/blob/main/docs/Reference.md#image)        | false    |
| team  | string | [Team number](https://github.com/matthewzring/cyberpatriot-api-docs/blob/main/docs/Reference.md#team-number) | true     |

###### EXAMPLE REQUEST

```bash
curl https://scoreboard.uscyberpatriot.org/api/image/scores.php \
  -d "image[]"=Windows11_cp17_sf_pg \
  -d "team[]"=17-1141 \
  -G
```

###### THE IMAGE SCORES OBJECT

```json
{
  "data": [
    {
      "team_id": 21,
      "image_id": 4,
      "team_number": "17-1141",
      "image": "Windows11_cp17_sf_pg",
      "duration": "03:51:48",
      "found": 34,
      "remaining": 7,
      "penalties": 0,
      "code": "",
      "ccs_score": 79,
      "location": "CA",
      "division": "Open",
      "tier": "Platinum"
    }
  ]
}
```

###### ATTRIBUTES

| Field            | Type                  | Description                                                                                                    |
|------------------|-----------------------|----------------------------------------------------------------------------------------------------------------|
| data             | array of dictionaries |                                                                                                                |
| data.team_id     | integer               | Internal team ID                                                                                               |
| data.image_id    | integer               | Internal image ID                                                                                              |
| data.team_number | string                | [Team number](https://github.com/matthewzring/cyberpatriot-api-docs/blob/main/docs/Reference.md#team-number)   |
| data.image       | string                | [Image name](https://github.com/matthewzring/cyberpatriot-api-docs/blob/main/docs/Reference.md#image)          |
| data.duration    | string                | Image [play time](https://github.com/matthewzring/cyberpatriot-api-docs/blob/main/docs/Reference.md#play-time) |
| data.found       | integer               | Vulnerabilities found                                                                                          |
| data.remaining   | integer               | Vulnerabilities remaining                                                                                      |
| data.penalties   | integer               | Number of penalties                                                                                            |
| data.code        | string                | Letter [codes](https://github.com/matthewzring/cyberpatriot-api-docs/blob/main/docs/Reference.md#code)         |
| data.ccs_score   | integer               | CCS score                                                                                                      |
| data.location    | string                | [Location](https://github.com/matthewzring/cyberpatriot-api-docs/blob/main/docs/Reference.md#location)         |
| data.division    | string                | [Division](https://github.com/matthewzring/cyberpatriot-api-docs/blob/main/docs/Reference.md#division)         |
| data.tier        | string                | [Tier](https://github.com/matthewzring/cyberpatriot-api-docs/blob/main/docs/Reference.md#division)             |
