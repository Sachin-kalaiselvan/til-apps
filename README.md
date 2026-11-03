# til-apps

Public pages for apps published by The Ingredient List — landing pages, privacy
policies, terms and support, one folder per app.

Live at **https://apps.theingredientlist.co**

Static HTML, no build step. Vercel deploys on every push to `main`.

## Layout

```
/                       index of all apps
/coreblocks             app landing page
/coreblocks/privacy     privacy policy   <- Play Console needs this URL
/coreblocks/terms       terms of use
/coreblocks/support     support page
/bandit-scan            app landing page
/bandit-scan/privacy    privacy policy
/bandit-scan/terms      terms of use
/bandit-scan/support    support page
```

Each page is `<folder>/index.html`. Link to pages without `.html` and without a
trailing slash (e.g. `/bandit-scan/privacy`) — `vercel.json` sets `cleanUrls` and
`trailingSlash: false`, so other forms get redirected.

## Adding an app

Copy the `coreblocks/` folder, rename it, edit the four pages, add a card to the
root `index.html`. Push. That's the whole process — no DNS change, no new project.

## Play Console fields

| Field | Value |
| --- | --- |
| Privacy policy | https://apps.theingredientlist.co/coreblocks/privacy |
| Website | https://apps.theingredientlist.co/coreblocks |
| Support email | theingredientlist.co@gmail.com |

Bandit Scan uses the same pattern: `/bandit-scan/privacy` and `/bandit-scan`.
