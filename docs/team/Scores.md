# Team Scores

###### ENDPOINTS

```http
GET /api/team/scores.php
```

###### PARAMETERS

| Field  | Type    | Description                                                                                                     | Required |
|--------|---------|-----------------------------------------------------------------------------------------------------------------|----------|
| team   | string  | [Team number](https://github.com/afacyberpatriot/cyberpatriot-api-docs/blob/main/docs/Reference.md#team-number) | false    |
| recent | integer | Shows teams that have competed in the past `x` minutes. Must be an integer between `1` and `10080`              | false    |

###### EXAMPLE REQUEST

```bash
curl https://scoreboard.uscyberpatriot.org/api/team/scores.php \
  -d "team[]"=17-1141 \
  -G
```

###### THE TEAM SCORES OBJECT

```json
{
  "data": [
    {
      "team_id": 21,
      "team_number": "17-1141",
      "images": 3,
      "play_time": "03:52:50",
      "score_time": "03:51:55",
      "ccs_score": "251",
      "location": "CA",
      "division": "Open",
      "tier": "Platinum",
      "code": "",
      "adjustment": "0.00",
      "score_1": "80.00",
      "score_2": "215.40",
      "score_3": "71.00",
      "total": "617.40"
    }
  ]
}
```

###### ATTRIBUTES

| Field            | Type                  | Description                                                                                                        |
|------------------|-----------------------|--------------------------------------------------------------------------------------------------------------------|
| data             | array of dictionaries |                                                                                                                    |
| data.team_id     | integer               | Internal team ID                                                                                                   |
| data.team_number | string                | [Team number](https://github.com/afacyberpatriot/cyberpatriot-api-docs/blob/main/docs/Reference.md#team-number)    |
| data.images      | integer               | Number of scored images                                                                                            |
| data.play_time   | string                | Team [play time](https://github.com/afacyberpatriot/cyberpatriot-api-docs/blob/main/docs/Reference.md#play-time)   |
| data.score_time  | string                | Team [score time](https://github.com/afacyberpatriot/cyberpatriot-api-docs/blob/main/docs/Reference.md#score-time) |
| data.ccs_score   | string                | CCS score                                                                                                          |
| data.team_name   | optional string       | Team or school name                                                                                                |
| data.location    | optional string       | [Location](https://github.com/afacyberpatriot/cyberpatriot-api-docs/blob/main/docs/Reference.md#location)          |
| data.division    | optional string       | [Division](https://github.com/afacyberpatriot/cyberpatriot-api-docs/blob/main/docs/Reference.md#division)          |
| data.tier        | optional string       | [Tier](https://github.com/afacyberpatriot/cyberpatriot-api-docs/blob/main/docs/Reference.md#division)              |
| data.code        | optional string       | Letter [codes](https://github.com/afacyberpatriot/cyberpatriot-api-docs/blob/main/docs/Reference.md#code)          |
| data.adjustment  | optional string       | Administrative adjustment                                                                                          |
| data.score_1     | optional string       | Additional score column 1                                                                                          |
| data.score_2     | optional string       | Additional score column 2                                                                                          |
| data.score_3     | optional string       | Additional score column 3                                                                                          |
| data.total       | optional string       | Cumulative score                                                                                                   |
