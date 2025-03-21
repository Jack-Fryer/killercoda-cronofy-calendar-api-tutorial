# 🔐 Step 1: Connect to the Cronofy API

We first need to connect to the Cronofy API using your client credentials.

---

## 🧠 1. Create a Cronofy Developer App

1. Go to the [Cronofy Developer Console](https://app.cronofy.com/sign_up/developer) and create a free account.  
2. Click **“Create New Application”**  
3. Name it anything you like, like 'Calendar API Test'.  
4. Set the **Redirect URI** to:

```
http://localhost:3000/callback
```

> (We won’t use this for this tutorial, but it’s required)

5. After creating the app, copy your:
- **Client ID**
- **Client Secret**

👉 You’ll also need to **authorize access to your calendar** during this tutorial in order to make API calls that interact with real data.

---

## 🔑 2. Request an Access Token

Paste your credentials into these variables and run this in the terminal:

```sh
CLIENT_ID="your-client-id"
CLIENT_SECRET="your-client-secret"

curl -X POST https://api.cronofy.com/oauth/token \
  -d "grant_type=client_credentials" \
  -d "client_id=$CLIENT_ID" \
  -d "client_secret=$CLIENT_SECRET" | jq
```

You should see a JSON response with your access token:

```json
{
  "access_token": "your-access-token",
  "token_type": "bearer",
  ...
}
```

👉 Copy that access token — you’ll use it in the next step!


