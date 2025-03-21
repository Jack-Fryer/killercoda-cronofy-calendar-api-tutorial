# Step 2: Read Events from the Calendar

Now that you've obtained an access token, you can use it to read events from the user's calendar. Cronofy provides an API endpoint to fetch calendar events.

## Steps:

1. **Make an API Request to Fetch Events**:
   To read events from the user's calendar, you need to send a `GET` request to the Cronofy `events` endpoint. 

   Here's a sample `curl` command to fetch events. Before you copy this into the terminal, replace <CALENDAR_ID> with the ID of the calendar you want to fetch events from, and <ACCESS_TOKEN> with the access token you obtained earlier.

   ```bash
   curl -X GET "https://api.cronofy.com/v1/calendars/<CALENDAR_ID>/events" \
   -H "Authorization: Bearer <ACCESS_TOKEN>"


**Response**: If the request is successful, you will receive a response with the details of the newly created event:

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
