# Step 1: Get Authorization to Access a Calendar

To start using the Cronofy Calendar API, you'll need to authenticate and get an access token.

## Steps:

1. **Create an App on Cronofy**:
   - Go to the [Cronofy Developer Dashboard](https://www.cronofy.com/developers/).
   - Sign up or log in.
   - Click on **Create New App** and follow the instructions to create a new application.

2. **Obtain your Client ID and Client Secret**:
   - After creating the app, you will receive a **Client ID** and **Client Secret**. Keep these credentials safe.

3. **Get the OAuth Authorization URL**:
   - To get the access token, Cronofy uses OAuth 2.0. Direct your user to the following URL to authenticate:
     ```
     https://api.cronofy.com/oauth/authorize?response_type=code&client_id=<YOUR_CLIENT_ID>&redirect_uri=<YOUR_REDIRECT_URI>
     ```
     Replace `<YOUR_CLIENT_ID>` with your actual Client ID, and `<YOUR_REDIRECT_URI>` with the redirect URI you specified when creating your app.

4. **User Grants Access**:
   - The user will log in and authorize your app to access their calendar. After approval, Cronofy will redirect the user to the redirect URI, appending an authorization code to the URL.

5. **Exchange the Authorization Code for an Access Token**:
   - Once you have the authorization code, you can exchange it for an access token. This is done by making a POST request to the Cronofy API with the following details:
   
   ```bash
   POST https://api.cronofy.com/oauth/token
   Content-Type: application/x-www-form-urlencoded
   Grant_type: authorization_code
   Code: <YOUR_AUTHORIZATION_CODE>
   Client_id: <YOUR_CLIENT_ID>
   Client_secret: <YOUR_CLIENT_SECRET>
   Redirect_uri: <YOUR_REDIRECT_URI>

- This will return an access token that you can use to make requests to the Cronofy API.

After completing this step, you'll have the credentials needed to authenticate your app and access the calendar data.
