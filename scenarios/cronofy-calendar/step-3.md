# Step 3: Create a New Event in the Calendar

Now that you know how to read events, let's move on to creating a new event in the calendar. Cronofy provides a simple way to add new events via their API.

## Steps:

1. **Make an API Request to Create an Event**:
   To create a new event, you need to send a `POST` request to the Cronofy `events` endpoint. Here’s a sample `curl` command to create an event:

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

Before you copy the command, make sure you replace the following placeholders:

<CALENDAR_ID>: The calendar ID where you want to create the event.

<ACCESS_TOKEN>: The access token you obtained earlier.

event_id: A unique identifier for the event. You can use any string that’s unique.

summary: A short title or name for the event.

description: A more detailed description of the event (optional).

start and end: The start and end times of the event in ISO 8601 format (UTC time).

location: The location of the event (optional).

timezone: The timezone in which the event will occur (optional).

2. **Handling the Response**:  
   The API will return a list of events in JSON format. Here’s an example of the response:

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

