# 📅 Step 2: Read Events from the Calendar

Now that you've obtained an access token, you can use it to read events from the user's calendar. For the case of this tutorial, we will be reading events from your own calendar that you have already connected. 

Cronofy provides a simple API endpoint to do this.

---

## 🔁 a. Make an API Request to Fetch Events

To read events, you’ll send a `GET` request to Cronofy’s `/events` endpoint.

Before running the command below, replace:
 
- `<ACCESS_TOKEN>` with the token you got in Step 3


The Cronofy API allows you to read all events across all calendars for all providers with one call. The only mandatory parameter is the tzid, ie. time zone identifier, for which you want to read. The example below is for UTC, but you can also use Europe/Paris, America/Chicago or any identifier in the IANA Time Zone Database.

> By default the events returned are from 42 days in the past to 201 days in the future. You can specify `<from>` and `<to>` parameters to refine that search - you can see the query below is searching for events set between March 21st 2025 and March 22nd 2025.



```bash
curl -v -G --header "Authorization: Bearer {YOUR_ACCESS_TOKEN_HERE}" \
  -d 'tzid=Etc/UTC&from=2025-03-21&to=2025-03-22' https://api.cronofy.com/v1/events
```

This will return a list of events from that calendar.

---


## 📬 b. Example Response

If the request is successful, you'll receive a list of events in JSON format. Here's a sample of one event object:

```json
{
  "event_id": "event-123",
  "summary": "Team Sync",
  "description": "Meeting to discuss project updates",
  "start": "2025-03-25T09:00:00Z",
  "end": "2025-03-25T10:00:00Z",
  "location": "Zoom",
  "timezone": "UTC"
}
```

---

✅ You’ve now successfully fetched real calendar data using the Cronofy Calendar API!


> Next, you’ll learn how to create an event in your calendar by calling the Calendar API.

