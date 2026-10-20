# mobile-app-pages

Public pages that the App Store and Google Play require for our white-label client apps, such as account deletion pages. GitHub Pages serves this repo from the root of `main`.

## Layout

One folder per client, one folder per page:

```text
<client>/<page>/index.html
<client>/<page>/icon.png
```

A page is served at `https://<owner>.github.io/mobile-app-pages/<client>/<page>/`.

| Client | App | Page | Used in |
| --- | --- | --- | --- |
| `kent` | Frank by Kent (`com.kentplc.intranet`) | [`account-deletion`](kent/account-deletion/) | Google Play Data safety form: account deletion link |

## Adding a page for a client

1. Copy an existing page folder, for example `kent/account-deletion`, to `<client>/<page>`.
2. Replace the app name, package name, developer name and form endpoint. The names must match the client's store listing exactly, or Google rejects the link.
3. Take `icon.png` from the client's branding repo (`icon/Android/playstore-icon.png`). The branding repos are listed in `white-label/branding-repos.json` in quark-rn.
4. Fill in every `[CONFIRM: …]` item with the client before you push. Google reviewers read the retention section.
5. Add a row to the table above.

## Google Play account deletion requirements

The page Google checks must:

- Name the app or the developer exactly as they appear on the Play listing.
- Show the steps a user takes to request deletion.
- Say which data is deleted and which is kept, and for how long anything is kept.
- Load without signing in.

See [Understanding Google Play's app account deletion requirements](https://support.google.com/googleplay/android-developer/answer/13327111).
