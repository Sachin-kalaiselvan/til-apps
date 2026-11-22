# til-apps

public pages for the apps the ingredient list ships. landing page, privacy, terms, support. one folder per app.

live: **https://apps.theingredientlist.co**

plain html, no build. vercel deploys every push to `main`.

## layout

```
/                       all apps, one card each
/<app>                  landing          <app>/index.html
/<app>/privacy          privacy policy   <app>/privacy/index.html   <- play console wants this url
/<app>/terms            terms            <app>/terms/index.html
/<app>/support          support          <app>/support/index.html
```

## apps

| app | folder | privacy | play package | ads |
| --- | --- | --- | --- | --- |
| core blocks | `coreblocks/` | `/coreblocks/privacy` | `co.theingredientlist.coreblocks` | admob |
| bandit scan | `bandit-scan/` | `/bandit-scan/privacy` | `co.theingredientlist.bandit` | none |
| intervals | `intervals/` | `/intervals/privacy` | `co.theingredientlist.intervals` | none |
| arrow out | `arrow-out/` | `/arrow-out/privacy` | `co.theingredientlist.arrowout` | admob |
| bolt up | `bolt-up/` | `/bolt-up/privacy` | `co.theingredientlist.boltup` | admob |
| pour nine | `pour-nine/` | `/pour-nine/privacy` | `co.theingredientlist.pournine` | admob |
| gymguild | `gymguild/` | `/gymguild/privacy` | `co.theingredientlist.gymguild` | none |

link without `.html` and without a trailing slash (`/bandit-scan/privacy`). `vercel.json` has `cleanUrls` + `trailingSlash: false` so anything else redirects.

every landing page has a commented-out "get it on google play" button with the real package id. uncomment once the app's live.

## new app

copy `coreblocks/`, rename, edit the 4 pages, add a card to the root `index.html`, push. that's it, no dns, no new project.

## play console

privacy policy `https://apps.theingredientlist.co/<folder>/privacy`, website `https://apps.theingredientlist.co/<folder>`, support email theingredientlist.co@gmail.com.
