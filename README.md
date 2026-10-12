# Gerry's Brain

An internal alpha for **Byrne Building Services**, a family electrical and plumbing contractor in Naas.

## The problem

Commercial jobs wait about 25 days in the founder Gerry's tray before he prices them, so invoices go out about 40 days after the job. Gerry insists that pricing stays with him.

## What it does

Three views in one page:

1. **Office**: log a finished job in under a minute (customer, job type, date done, hours, materials, a note). A timer shows how long logging took.
2. **Gerry**: a queue of jobs waiting for a price, oldest first. Each job has a suggested price drawn from Gerry's past prices for similar jobs. Swipe right or tap to approve; swipe left or tap Edit to change it, with quick ±5% and ±10% buttons.
3. **Sandra**: what is waiting, for how many days, and the total cash tied up, with an aged breakdown (0–3, 4–7, 8–14, 15+ days).

Anything waiting more than 3 days turns red. A **Play demo** button runs the whole story automatically for presenting.

## How the suggested price works

For the same job type, the app works out the hourly rate Gerry effectively charged on each past job, after allowing a 15% markup on materials. It takes the median of those rates, applies it to the new job's hours, adds materials +15%, and rounds to the nearest €5. Every price Gerry approves is added to the history, so suggestions follow what he actually charges.

## Tech

A single `index.html` file: HTML, CSS and JavaScript together, with no external libraries. Works on a phone. Changes are saved in the browser with `localStorage`, so each device keeps its own copy.

All customers, jobs and prices are made-up sample data. Use **Reset sample data** at the bottom of the page to start again.

## Run it

Open `index.html` in any browser, or view it on GitHub Pages.
