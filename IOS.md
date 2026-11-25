# Azan Times: iPhone app

The website lives in `www/` and Netlify publishes that folder. The iPhone app wraps the same files and adds real azan alerts at prayer times, even when the phone is locked.

## Build it on your Mac (one time setup)

1. Install **Xcode** from the Mac App Store, and Node.js from nodejs.org.
2. In Terminal: `git clone https://github.com/muratygt/azan-times && cd azan-times && npm install`
3. Run `npx cap sync ios`, then `npx cap open ios`. Xcode opens the project.
4. In Xcode, click **App** in the left list, then **Signing & Capabilities**. Choose your Apple ID under **Team**. If the bundle ID `com.muratygt.azantimes` is taken, change it to something unique.
5. Plug in your iPhone, pick it at the top of Xcode, and press Run. On the phone, trust the developer in Settings > General > VPN & Device Management.

A free Apple ID can run the app on your own phone, but it expires after 7 days. The paid Apple Developer Program ($99 a year) removes that limit and lets you use TestFlight and the App Store.

## The azan sound

`ios/App/App/azan.wav` is a placeholder chime. Replace it with a real azan:

- iPhone notification sounds can be at most **30 seconds**. A longer file falls back to the default sound.
- Trim and convert (for example with ffmpeg): `ffmpeg -i azan_full.mp3 -t 30 -af "afade=t=out:st=27:d=3" -ar 44100 -ac 1 ios/App/App/azan.wav`
- Keep the file name `azan.wav`, then run it again from Xcode.
- Use a recording you have the right to use.

## How the alerts work

The app schedules the next 12 days of alerts on the phone. iPhone allows about 64 at once. Opening the app tops it up, so open it at least every 12 days. Changing the city or settings reschedules everything.

## Updating the app

After changing files in `www/`, run `npx cap sync ios` and press Run in Xcode. Netlify still publishes the website from the same files.

## App Store

In Xcode, choose Product > Archive, then Distribute App > App Store Connect. In App Store Connect add screenshots, a description, a privacy policy page (the app uses location, and nothing leaves the phone), and submit for review. Apple may reject apps that are only a website, so mention the azan notifications, the compass and the widget-free offline use in the review notes.
