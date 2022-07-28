<h1 align="center">Mi Smart Band 5</h1>

Tinkering with my smartwatch.

## <b>Server Based pairing</b>
Mi Band 5 and devices released after them do require this process of pairing. This means that for devices that require server base pairing you absolutely
must at least once use the original MiFit, Amazfit, Zepp or other official app to make the very first, initial pairing.

### <b>Obtaining the auth/pairing key</b>
The key is available either from Mifit/Zepp internal data storage or from their online servers. You **must not unpair** the watch from their original app as this would erase the key.

There are several methods to do this you can find them [here](https://codeberg.org/Freeyourgadget/Gadgetbridge/wiki/Huami-Server-Pairing) for both rooted and non-rooted phones.My phone isnt rooted and thus the handy python script by the wonderful guys at [Gadgetbridge](https://codeberg.org/argrento/huami-token) will do.

Run the script with your credentials in my case thats my Amazfit/zepp account:
```bash
$ python huami_token.py --method amazfit --email dannduati2@gmail.com --p xxxxxxxx --bt_keys
Getting access token with 'amazfit' login method...
Token: ['UQVBQDZOQmJaR0YyajYmWnJoBAgAAAAAAYT1Vb0JyMU9heWw0ZWczZ0lpaXh5TkhfUUFBQVlKRXZjMkwmcj05JnQ9aHVhbWkmdGk9ZGFubmR1YXRpMkBnbWFpbC5jb20maD0xNjU5MDEzMjM4NTI0Jmk9ODY0MDAwJnVzZXJuYW1lPWRhbm5kdWF0aTJq19qB6015dlOaCWAWAnw5']
Logging in...
Logged in! User id: 3085xxxxx
Getting linked wearables...

╓───Device 0
║  MAC: C9:4B:C7:03:F8:15, active: Yes
║  Key: 0x09fc02af210596d54xxxxxxxxxxxxx
╙────────────

Logged out.
```

> ***Warning:***
> Every time you hard reset the band/watch, the Bluetooth MAC Address will be changed and you must grab a new key! Also, anytime you unpair your band/watch from MiFit, the pairing key will be invalidated and you must make new pairing in MiFit app.

### Features that work without authkey
- Sending Calls
- Sending alerts
- Sending Missed call notifications
- Retrieving device info
- Sending music title and music state(Playing/Paused)
- Recieve music control events (Play/Pause/Forward/Backward/Volume Up/Volume Down/Enter Music app/ Exit Music app) through callbacks

## Features that needs authkey
- Retrieving heart rate (Realtime and Single time)
- Firmware update/restore (This feature has the potential to brick your Mi Band 4. Do it at your own risk)
- Retrieving steps count, calories count and fat burnt
- Setting date and time
- Fetching fitness data within certain past intervals.

