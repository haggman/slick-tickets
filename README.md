Slick Tickets is the primary app of a fictitious company of the same name. It is designed to allow Slick Ticket admins to post events, and customers to purchase and print tickets for those events.

This is designed to support the labs for an internal Google training for Google Cloud UX Designers.

If you have any questions email jordanmhart@gmail.com.

To run the app in Cloud Shell:

0. Enable Firestore in native mode in your project if you haven't alread by visiting its page in the hamburger menu
1. Run `npm install` inside the subdirectories of the app folder
2. If not running in Cloud Run, create a .env file in each of the directories with the contents shown below
3. Run npm start in each subdirectory of the app folder (run both services before running the web app)

Important Notes:
1. If running locally, change the service account files below to match yours
2. Or if you are running in Google Cloud (Cloud Shell?), instead of including that var just include an env var ON_GOOGLE_CLOUD=true
3. For the session secret you can put whatever you want
4. To make yourself an admin, first register for an account normally. Then go into the Firestore DB and add the property isAdmin=true to your record.

Events Service .env file:

```
EVENTS_PORT=3001
ON_GOOGLE_CLOUD=true
```

Users Service .env file:

```
USERS_PORT=3002
ON_GOOGLE_CLOUD=true
```

Web App .env file:

```
WEB_PORT=8080
EVENTS_SERVICE=http://localhost:3001
USERS_SERVICE=http://localhost:3002
ON_GOOGLE_CLOUD=true
SESSION_SECRET=putwhateveryouwanthere
```
