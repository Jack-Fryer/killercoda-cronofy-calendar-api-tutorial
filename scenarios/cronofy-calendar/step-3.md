# 📝 Step 3: Create a New Event in the Calendar

Now that you know how to read events, let’s move on to creating them. Cronofy’s API makes it easy to add events to a user’s calendar.

---

## ✍️ 1. Make an API Request to Create an Event

To create a new event, send a `POST` request to the `/events` endpoint.

> Before running the command below, replace:

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

✅ You’ve now created a real event on a real calendar using Cronofy’s API! Head to your calendar to verify the event was created.

> We're going to delete it in the next step.
