# Client KM Logbook

An offline-capable static Home Screen web app for iPhone. It has no server-side code, account, or external database. Trip and client records are stored in the browser storage belonging to the installed app on the iPhone.

## Files

- `index.html` — logbook, trip entry, dashboard, automatic local saving, JSON backup/restore, and Excel workbook export/import.
- `manifest.webmanifest` — Home Screen app name, display mode, and icons.
- `service-worker.js` — caches the app shell for offline use.
- `icons/` — Home Screen and browser icons.
- `guide.pdf` — installation and usage instructions.

## Safari installation requirement

Safari adds a Home Screen web app from an HTTPS page. Serve these static files from an HTTPS URL, then follow `guide.pdf`. There is no backend or database, and the app does not upload trip data. If you do not want the app files hosted at all, Safari Home Screen installation is unavailable; a native iOS app would need to be built and signed with Apple tooling.

Upload the contents of this folder as-is. `index.html`, `manifest.webmanifest`, and `service-worker.js` must stay together, and the `icons` directory must stay in place. Do not upload a personal JSON backup or an Excel export.

## Local data and backups

The app saves records to IndexedDB and local storage for its web app origin, then reloads them when reopened. The app also requests persistent storage from Safari. Export all trips to `.xlsx` for a spreadsheet backup; choose that workbook under **Import trips from an Excel backup** to restore. Imports merge with existing records and skip duplicate rows. JSON backup/restore remains available as an optional alternative.

Keep an exported workbook in the iPhone Files app or iCloud Drive for recovery. Safari website data can still be cleared by the user or removed by iOS, so a separate file is the durable backup. Excel export/import uses the logbook's `.xlsx` format; legacy `.xls` files are not supported.
