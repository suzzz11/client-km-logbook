# Client KM Logbook

An offline-capable static Home Screen web app for iPhone. It has no server-side code, account, or external database. Trip and client records are stored in the browser storage belonging to the installed app on the iPhone.

## Files

- `index.html` — logbook, trip entry, dashboard, JSON backup/restore, and Excel workbook export.
- `manifest.webmanifest` — Home Screen app name, display mode, and icons.
- `service-worker.js` — caches the app shell for offline use.
- `icons/` — Home Screen and browser icons.
- `guide.pdf` — installation and usage instructions.

## Safari installation requirement

Safari adds a Home Screen web app from an HTTPS page. Serve these static files from an HTTPS URL, then follow `guide.pdf`. There is no backend or database, and the app does not upload trip data. If you do not want the app files hosted at all, Safari Home Screen installation is unavailable; a native iOS app would need to be built and signed with Apple tooling.

Upload the contents of this folder as-is. `index.html`, `manifest.webmanifest`, and `service-worker.js` must stay together, and the `icons` directory must stay in place. Do not upload a personal JSON backup or an Excel export.

## Local data and backups

The app saves records to IndexedDB and local storage for its web app origin. Keep regular JSON backups in the iPhone Files app. Restoring a backup merges it with records already stored in the app. Safari storage can be cleared by the user or removed by iOS under storage pressure, so a backup is the durable copy.
