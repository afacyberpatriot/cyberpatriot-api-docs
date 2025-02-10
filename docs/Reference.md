# API Reference

The CyberPatriot API is organized around [REST](https://en.wikipedia.org/wiki/REST). Our API has predictable resource-oriented URLs, accepts [form-encoded](https://en.wikipedia.org/wiki/POST_(HTTP)#Use_for_submitting_web_forms) request bodies, returns [JSON-encoded](http://www.json.org/) responses, and uses standard HTTP response codes and verbs.

###### BASE URL

```
https://scoreboard.uscyberpatriot.org/api
```

All API requests should be made over [HTTPS](http://en.wikipedia.org/wiki/HTTP_Secure).

## User Agent

Please provide a valid [User Agent](https://www.rfc-editor.org/rfc/rfc9110.html#section-10.1.5) which specifies your contact information. (Specifically, the contact info of the person that maintains the code sending the automated requests, *not* the contact info of the person using the script.)

Bonus points if you also include a URL where we can check out your script!

###### USER AGENT EXAMPLE

```
User-Agent: github.com/matthewzring/cyberscores by m@tthewzri.ng
```

## Errors

We use conventional HTTP response codes to indicate the success or failure of an API request. In general: Codes in the `2xx` range indicate success. Codes in the `4xx` range indicate an error that failed.

You are expected to make reasonable attempts to avoid making invalid requests. If a request returns a **404** status you should not attempt to use it again.

## Rate Limits

Rate limits exist across CyberPatriot's APIs to prevent spam, abuse, and service overload. If you create any kind of automated tool that touches the CyberPatriot servers, *you* are responsible for ensuring that it does not hammer the CyberPatriot servers.

Avoid sending more than one request per second.

## Timestamps

The format for Date/Times returned in our models will be as it appears on the scoreboard, usually in `m/d H:i` format.

## Nullable and Optional Data Fields

Data fields that may contain a `null` value will be marked as nullable. Data fields that are returned when available have types that are marked as optional.

⚠ If you do not see some of the parameters in your API response it means that they are not displayed on the public scoreboard.

## Data Formatting

We use the default format expected by [DataTables](https://datatables.net/) to display and return information.

## Chart Data

We utilize the [Google Visualization API](https://developers.google.com/chart/interactive/docs/reference) format for chart data returned in our models.

## Bulk Requests

Most endpoints support multiple parameters per request. You can specify up to **32** teams in one request.

💡 Tip: This also works in the native scoreboard, for example:

```
https://scoreboard.uscyberpatriot.org/?team[]=17-1141&team[]=17-0224&team[]=17-0555
```

## Attributes

### Location

Two or three letter state or country abbreviation.

### Division

| Division      | Explanation                           |
|---------------|---------------------------------------|
| All           | All Divisions                         |
| AFJROTC       | Air Force JROTC and Space Force JROTC |
| AJROTC        | Army JROTC                            |
| CAP           | Civil Air Patrol                      |
| MCJROTC       | Marine Corps JROTC                    |
| Middle School | Middle school students                |
| NJROTC        | Navy JROTC and Coast Guard JROTC      |
| Open          | High school students                  |
| USNSCC        | US Naval Sea Cadet Corps              |

### Tier

| Tier          | Explanation         |
|---------------|---------------------|
| All           | All Tiers           |
| High School   | High school teams   |
| Middle School | Middle school teams |
| Platinum      | Platinum tier       |
| Gold          | Gold tier           |
| Silver        | Silver tier         |

### Image

The image name. This will include the OS, year, round, and tier, if applicable.

### Team Number

Team number, consisting of a competition identifier (`17-`) and team number (`0000`).

### Play Time

The total duration a team or image has been running, in `hh:mm:ss` format.

### Score Time

The fastest time to achieve the team's current score, in `hh:mm:ss` format.

### Code

Warnings a team has received.

| Letter Code | Explanation             |
|-------------|-------------------------|
| M           | Multiple Instances      |
| T           | Time Exceeded           |
| C           | Challenge Time Exceeded |
| W           | Scores Withheld         |
