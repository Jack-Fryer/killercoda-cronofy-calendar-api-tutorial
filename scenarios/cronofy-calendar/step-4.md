# ❌ Step 4: Delete an Event from the Calendar

You’ve created and viewed events — now let’s clean up by deleting one.

Cronofy makes it simple to delete calendar events using their unique `event_id`. 

Let's test your knowledge and see if you can run a query to see what events you have and find the event ID of the event we just created (ADD something here) 

---

## 🧼 1. Send a DELETE Request to the API

To delete an event, send a `DELETE` request to Cronofy’s `/events` endpoint.

Replace the placeholders before running this command:

```bash
curl -X DELETE "https://api.cronofy.com/v1/calendars/<CALENDAR_ID>/events" \
  -H "Authorization: Bearer <ACCESS_TOKEN>" \
  -H "Content-Type: application/json" \
  -d '{
    "event_id": "<EVENT_ID>"
  }'
```

---

## 📎 What You Need

| Parameter        | Description                                       |
|------------------|---------------------------------------------------|
| `<CALENDAR_ID>`  | The ID of the calendar where the event exists     |
| `<ACCESS_TOKEN>` | The token you received during authorization       |
| `<EVENT_ID>`     | The exact ID of the event you want to delete      |

---

✅ If the request is successful, you’ll get a `202 Accepted` response and the event will be removed.

💡 Pro Tip: Run the **read events** command from Step 2 again to confirm that the event is gone! Verify by checking your calendar too.

---

🎉 That’s it — you’ve now created, read, and deleted events using the Calendar API - congrats!
