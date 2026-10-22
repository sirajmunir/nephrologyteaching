# Nephrology Teaching Calendar

A one-page teaching calendar for GitHub Pages. It shows each session's topic, presenter, time and venue, highlights today, and lets you (and only you) add, edit and delete sessions from the page.

The site is two files:

| File | What it holds |
|---|---|
| `index.html` | The calendar page. Its settings block sets the title, subtitle, your private editing link, and the session types and colours. |
| `events.js` | The list of sessions. This is the only file that changes week to week. |

## Putting it on GitHub Pages (once)

1. Create a new repository on GitHub, for example `nephrology-teaching`.
2. Choose **Add file → Upload files**, drag in `index.html` and `events.js`, then choose **Commit changes**. (In this repository they live in the `calendar` folder.)
3. Go to **Settings → Pages**. Under **Build and deployment**, set **Source** to *Deploy from a branch*, pick the `main` branch and the `/ (root)` folder, then **Save**.
4. After a minute or two the calendar is live at `https://sirajmunir.github.io/nephrologyteaching/calendar/`.

## Who can change the calendar

Visitors only ever see the calendar. There are no edit buttons on the page, and nothing anyone does in their own browser changes what others see. The calendar only changes when someone uploads a new `events.js` to your GitHub repository, and only people you've given access to the repository can do that.

You edit through a private link: your calendar address with `#renal-admin` on the end, for example

`https://sirajmunir.github.io/nephrologyteaching/calendar/#renal-admin`

Bookmark it. To change the word, edit `editLink` in the settings block near the top of `index.html`.

The link just saves you clutter; it isn't a password. Anyone who opened it could only change their own browser's copy. They still couldn't publish anything without access to your GitHub repository.

## Adding or deleting sessions

1. Open your editing link.
2. Add a session with the **+** on any day (or **Add a session**). Click any session to **Edit** or **Delete** it. Deleting can be undone from the message that appears.
   - For a regular slot, use **Repeat** to add the same session weekly in one go.
3. Choose **Download events.js**. If your browser saves it as `events (1).js`, rename it to `events.js`.
4. In your GitHub repository open the `calendar` folder, choose **Add file → Upload files**, drop in the new `events.js` and **Commit changes**. It replaces the old one.
5. Wait about a minute and reload. Everyone now sees the updated calendar.

Your changes are saved in your own browser until you publish them, so you can close the tab and come back. **Finish editing** shows the calendar exactly as everyone else sees it. **Discard changes** throws away anything you haven't published.

## Editing events.js by hand

You can also open `events.js` on GitHub and click the pencil icon. Each session is one block:

```js
  {
    date:      "2026-10-22",
    start:     "12:30",
    end:       "13:30",
    title:     "Acute kidney injury: recognition and first steps",
    presenter: "Dr Sarah Okafor",
    venue:     "Renal Unit Seminar Room",
    type:      "Teaching",
    notes:     ""
  },
```

- To add one, copy a block and change the details. Order doesn't matter.
- To delete one, remove the whole block from `{` to `},`.
- Dates are year-month-day; times use the 24-hour clock.
- If the page shows "The session list could not be loaded", it names the line with the mistake. It is nearly always a missing comma between blocks or a missing quotation mark.

## Other features

- Today is highlighted in the calendar and shown at the top, with a "Happening now" tag during a session.
- **List** view shows the whole month as an agenda; **Month** view shows the grid.
- **Add to my calendar** on any session downloads an invite for Outlook, Google or Apple Calendar.
- Keyboard: ← and → change month, **T** jumps to today.
- Works on phones, follows the device's dark mode and prints cleanly.

The sample sessions and names in `events.js` are placeholders. Replace them with your own programme.
