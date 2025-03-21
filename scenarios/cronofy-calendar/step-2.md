# 📅 Step 2: Read Events from the Calendar

Now that you've obtained an access token, you can use it to read events from the user's calendar. For the case of this tutorial, we will be reading events from your own calendar that you have already connected. 

Cronofy provides a simple API endpoint to do this.

---

## 🔁 1. Make an API Request to Fetch Events

To read events, you’ll send a `GET` request to Cronofy’s `/events` endpoint.

Before running the command below, replace:

- `<CALENDAR_ID>` with the ID of the calendar you want to query  
- `<ACCESS_TOKEN>` with the token you got in Step 3

```bash
curl -X GET "https://api.cronofy.com/v1/calendars/<CALENDAR_ID>/events" \
  -H "Authorization: Bearer <ACCESS_TOKEN>" | jq
```

This will return a list of events from that calendar.

---


## 📬 2. Example Response

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

