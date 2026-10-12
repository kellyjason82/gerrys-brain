# Gerry's Brain

An internal alpha for **Byrne Building Services**, a family electrical and plumbing contractor in Naas.

**Try it live**
- Web version: https://kellyjason82.github.io/gerrys-brain/
- Phone app version: https://kellyjason82.github.io/gerrys-brain/app/

## The problem

Commercial jobs wait about 25 days in the founder Gerry's tray before he prices them, so invoices go out about 40 days after the job. Gerry insists that pricing stays with him.

## The idea

Take the waiting out, not the decision. The office logs a finished job in under a minute, the app suggests a price from what Gerry has charged before, and Gerry approves or changes it with one tap. Sandra sees what is waiting, for how long, and how much cash is tied up.

Both versions have the same three roles:

1. **Office** logs a finished job: customer, job type, date done, hours, materials and a note.
2. **Gerry** works through a queue of jobs waiting for a price, oldest first, each with a suggested price.
3. **Sandra** sees what is waiting, for how many days, and the total cash tied up, broken down by age (0–3, 4–7, 8–14 and 15+ days).

Anything waiting more than 3 days turns red.

## Two versions

### Web version (`index.html`)
- Three tabs in one page.
- Gerry swipes right to approve or left to edit, with ±5% and ±10% buttons.
- Each job shows a live clock of how long it has sat in the tray.
- A **Play demo** button runs the whole story automatically for presenting.
- A **Get the app** button opens a card with a QR code that takes your phone straight to the phone app.

### Phone app version (`app/`)
A working **Progressive Web App (PWA)**: it installs on a phone from the link, with no App Store.
- **Installs on the home screen** with its own icon and opens full screen.
- **Works offline**, so it keeps going in the van with no signal.
- **Price dial:** Gerry turns a dial, like a multimeter, to set the price. His past prices for that kind of job are marked around the ring.
- **Tap, don't type:** the office logs a job with chips and steppers, and can **photograph the job sheet** with the phone's camera.
- **Nudge Gerry:** Sandra sends a ready-written reminder through WhatsApp.
- On Android, the app icon shows how many jobs are waiting.
- On a laptop or projector it appears inside a phone frame.

## How the suggested price works

For the same job type, the app works out the hourly rate Gerry effectively charged on each past job, after allowing a 15% markup on materials. It takes the median of those rates, applies it to the new job's hours, adds materials +15%, and rounds to the nearest €5. Every price Gerry approves is added to the history, so suggestions follow what he actually charges.

## Tech

HTML, CSS and JavaScript with no external libraries. Data is saved in the browser with `localStorage`, so each phone or computer keeps its own copy. The phone app adds a web app manifest, app icons and a service worker for installing and offline use.

All customers, jobs and prices are made-up sample data. Use **Reset sample data** to start again.

## Files

```
index.html               Web version
app/index.html           Phone app version
app/manifest.webmanifest App name, icon and colours for installing
app/sw.js                Service worker that makes it work offline
app/*.png                App icons
```
