# 📝 Step 3: Create a New Event in the Calendar

Now that you know how to read events, let’s move on to creating them. Cronofy’s API makes it easy to add events to a user’s calendar.

---

## ✍️ 1. Make an API Request to Create an Event

To create a new event, send a `POST` request to the `/events` endpoint.

Before running the command below, replace:

- `<CALENDAR_ID>`: The calendar you want to add the event to  
- `<ACCESS_TOKEN>`: Your access token from the previous step  
- Other fields like `event_id`, `summary`, `start`, and `end` as needed

```bash
curl -X POST "https://api.cronofy.com/v1/calendars/<CALENDAR_ID>/events" \
  -H "Authorization: Bearer <ACCESS_TOKEN>" \
  -H "Content-Type: application/json" \
  -d '{
    "event_id": "event-123",
    "summary": "Team Sync",
    "description": "Meeting to discuss project updates",
    "start": "2025-03-25T09:00:00Z",
    "end": "2025-03-25T10:00:00Z",
    "location": "Zoom",
    "timezone": "UTC"
  }'
```

📝 **Field Descriptions:**

| Field         | Description                                            |
|---------------|--------------------------------------------------------|
| `event_id`    | A unique ID for the event (any string you choose)      |
| `summary`     | A short title for the event                            |
| `description` | A longer description (optional)                        |
| `start`, `end`| Start and end times in ISO 8601 format (UTC)           |
| `location`    | Location of the event (optional)                       |
| `timezone`    | Timezone (optional, default is UTC)                    |

---

## 📬 2. Example Response

If successful, the API will return a JSON array of upcoming events. Here’s a sample response:

```json
{
  "events": [
    {
      "event_id": "12345",
      "summary": "Meeting with team",
      "start": "2025-03-22T10:00:00Z",
      "end": "2025-03-22T11:00:00Z"
    },
    {
      "event_id": "67890",
      "summary": "Doctor's Appointment",
      "start": "2025-03-22T14:00:00Z",
      "end": "2025-03-22T15:00:00Z"
    }
  ]
}
```

---

✅ You’ve now created a real event on a real calendar using Cronofy’s API!
