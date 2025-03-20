# Chart

###### ENDPOINTS

```http
GET /api/image/chart.php
```

###### PARAMETERS

| Field | Type   | Description                                                                                                     | Required |
|-------|--------|-----------------------------------------------------------------------------------------------------------------|----------|
| team  | string | [Team number](https://github.com/afacyberpatriot/cyberpatriot-api-docs/blob/main/docs/Reference.md#team-number) | true     |

###### EXAMPLE REQUEST

```bash
curl https://scoreboard.uscyberpatriot.org/api/image/chart.php \
  -d "team[]"=17-1141 \
  -G
```

###### THE CHART OBJECT

```json
{
  "cols": [
    {
      "type": "string",
      "label": "Time"
    },
    {
      "type": "number",
      "label": "Windows11_cp17_sf_pg"
    },
    // ...
  ],
  "rows": [
    {
      "c": [
        {
          "v": "01/26 00:30"
        },
        {
          "v": 0
        },
        // ...
      ]
    },
    // ...
  ]
}
```

###### ATTRIBUTES

| Field      | Type                  | Description                         |
|------------|-----------------------|-------------------------------------|
| cols       | array of dictionaries |                                     |
| cols.type  | string                | Data type of the data in the column |
| cols.label | string                | Label of the data in the column     |
| rows       | array of dictionaries |                                     |
| rows.c     | array of dictionaries | Array of cells in the row           |
| rows.c.v   | varies                | The cell value                      |
