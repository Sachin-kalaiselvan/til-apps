# til-apps

Public pages for apps published by The Ingredient List — landing pages, privacy
policies, terms and support, one folder per app.

Live at **https://apps.theingredientlist.co**

Static HTML, no build step. Vercel deploys on every push to `main`.

## Layout

```
/                       index of all apps (one card per app)
/<app>                  landing page        <app>/index.html
/<app>/privacy          privacy policy      <app>/privacy/index.html   <- Play Console needs this URL
/<app>/terms            terms of use        <app>/terms/index.html
/<app>/support          support page        <app>/support/index.html
```

## Apps

| App | Folder | Website | Privacy policy | Play package | Ads |
| --- | --- | --- | --- | --- | --- |
| Core Blocks | `coreblocks/` | `/coreblocks` | `/coreblocks/privacy` | `co.theingredientlist.coreblocks` | AdMob |
| Bandit Scan | `bandit-scan/` | `/bandit-scan` | `/bandit-scan/privacy` | `co.theingredientlist.bandit` | none |
| Intervals | `intervals/` | `/intervals` | `/intervals/privacy` | `co.theingredientlist.intervals` | none |
| Arrow Out | `arrow-out/` | `/arrow-out` | `/arrow-out/privacy` | `co.theingredientlist.arrowout` | AdMob |
| Bolt Up | `bolt-up/` | `/bolt-up` | `/bolt-up/privacy` | `co.theingredientlist.boltup` | AdMob |
| Pour Nine | `pour-nine/` | `/pour-nine` | `/pour-nine/privacy` | `co.theingredientlist.pournine` | AdMob |
| GymGuild | `gymguild/` | `/gymguild` | `/gymguild/privacy` | `co.theingredientlist.gymguild` | none |

Each page is `<folder>/index.html`. Link to pages without `.html` and without a
trailing slash (e.g. `/bandit-scan/privacy`) — `vercel.json` sets `cleanUrls` and
`trailingSlash: false`, so other forms get redirected.

Every landing page has a commented-out "Get it on Google Play" button with the real
package id. Uncomment it once that app is live.

## Adding an app

Copy the `coreblocks/` folder, rename it, edit the four pages, add a card to the
root `index.html`. Push. That's the whole process — no DNS change, no new project.

## Play Console fields

| Field | Value |
| --- | --- |
| Privacy policy | https://apps.theingredientlist.co/coreblocks/privacy |
| Website | https://apps.theingredientlist.co/coreblocks |
| Support email | theingredientlist.co@gmail.com |

Every app uses the same pattern: `https://apps.theingredientlist.co/<folder>/privacy`
and `https://apps.theingredientlist.co/<folder>`.
