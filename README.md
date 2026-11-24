# Azan Times

A prayer times site for your phone: live countdown with seconds, Qibla compass, monthly timetable, GPS location. It installs to the home screen like an app.

## Put it online (about 2 minutes)

The site must be served over HTTPS for GPS and the compass to work.

**Netlify Drop (easiest, from a computer)**
1. Unzip `azan-site.zip` so you have the `azan-site` folder.
2. Go to https://app.netlify.com/drop and drag the whole folder onto the page.
3. Netlify gives you a link ending in `.netlify.app`. Create a free account when it asks if you want to keep the site.

**GitHub Pages (alternative)**
1. Make a new public repository and upload the files in this folder.
2. In the repository, open Settings > Pages and publish from the main branch.

## On your iPhone

1. Open the link in Safari.
2. Tap Share, then Add to Home Screen.
3. Open it from the home screen. Allow Location when asked, pick "My location (GPS)" from the city name at the top, then open the Compass tab and tap "Use my phone's compass" and allow Motion & Orientation.
4. If the compass stays blank: iPhone Settings > Safari > Motion & Orientation Access must be on.

## Settings worth knowing

- Method defaults to Muslim World League angles (Fajr 18, Isha 17), which matches the app this was modelled on. ISNA (15 and 15) is in the list and gives a later Fajr and earlier Isha.
- Minute adjustments default to 0, -7, 5, 4, 7, 0 (Fajr, Sunrise, Dhuhr, Asr, Maghrib, Isha).
- Compass correction converts your phone's magnetic heading to true north. Dallas is roughly +3 to +4 degrees.
- The chime plays only while the page is open. Background notifications need a native app.
