# Google Calendar Event Multiselect Mode

## Objective:
This is meant for people who use Google Calendar for time boxing.

I usually have my whole schedule for the day planned out, but when some delay happens (whoops), I'd need to shift all the rest of the day's events backwards. Clicking, dragging and dropping each event to adjust its timing is very tedious to do if there are many events to move.

I also have recurring events in my daily schedule, but if I want to break from the schedule for a day, I'd need to delete all the scheduled events one by one.

This extension saves a lot of time because you can select multiple events and move/delete them all at once!

## How to set up and use this:
NOTE: Please tell me if you want to test this and I'll add your email to the test users :-D
1. Download the gcal-multiselect folder and its contents on your computer.
2. Go to chrome://extensions/ in Google Chrome and turn on Developer Mode at the top right. Click Load Unpacked and select the gcal-multiselect folder.
3. Go to calendar.google.com and click the extension icon to open the popup.
4. _Set your calendar ID:_ The calendar ID for your primary calendar (the one titled your name) is just your gmail address. If you are using a different calendar, you can find its calendar ID in the calendar settings.
5. _Select the events to move or delete:_ CTRL/⌘ + CLICK to select individual (non "All day") events. If you have a block of back-to-back events you'd like to move, select the first event in the block, then SHIFT + CLICK the last event to select all the events in between as well.
6.  
    * _Move the events:_ Move one of the selected events, then press **CTRL/⌘ + ENTER** to move the rest.
    * _Delete the events:_ Just press **DEL** to delete all the selected events.

(Please be patient, it takes a while for the selection borders and event changes to appear.)

### If you want to make your own version of this:
1. Go to console.cloud.google.com > Create a new project
2. "APIs & Services" > "Enabled APIs & Services" > Enable Google Calendar API
3. "OAuth Consent Screen" > "External" > "Create" > Fill in the required information > Add the scope .../auth/calendar.events > Add your test users
4. "Credientials" > "Create Credentials" > "OAuth client ID" > Application type: Chrome Extension; Item ID: (copy the extension's ID from chrome://extensions/ in developer mode) > Copy the client ID
5. Replace "client_id" in manifest.json with your own client ID.

## Future improvements (maybe):
* Autofill the calendar ID
* It would be really nice if all the selected events would just shift together once one is shifted, without having to press Ctrl+Enter, but unfortunately, it seems like Google Calendar does something when events are dragged & dropped which prevents the dropping of events from registering as mouseups. I'd like to try and find an alternative solution if possible.
* Everything is kind of very slow... 🐌... Gotta try and fix that, though I'm not sure how I might approach this problem, since Google Calendar itself sometimes lags when editing events.
