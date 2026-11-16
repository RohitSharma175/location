# Repository Guidelines

## Project Structure

The repository is a small static page. `index.html` contains the page markup, styles, Google Maps embed, and browser-side JavaScript in one file. There are currently no source, asset, or test subdirectories. Keep additions proportionate to this structure; if the project grows, separate reusable code and assets into clearly named directories.

## Build, Test, and Development

There is no build system or automated test suite configured. To preview the page, open `index.html` in a browser. For a local HTTP preview, run `python3 -m http.server 8000` from the repository root and visit `http://localhost:8000`.

Browser geolocation requires a secure context (HTTPS, with localhost treated as secure) and explicit visitor permission. When checking changes, verify the map loads, the layout fills the viewport on desktop and mobile, and location-denied or unsupported cases fail gracefully. Do not send test location data to a live webhook; use an approved test endpoint if validating network behavior.

## Coding Style

Use two spaces for indentation in HTML, CSS, and JavaScript, matching the existing file. Keep HTML attributes quoted, use lowercase HTML element names, and use `camelCase` for JavaScript variables and functions. Prefer small, readable edits within the existing file unless a clear need justifies splitting it. No formatter or linter is currently configured.

## Testing Guidelines

No test framework or coverage requirement exists. For each change, manually inspect the page in a current browser and check the browser console for errors. Exercise geolocation success, denial, and unsupported-browser behavior when relevant, using mocked or controlled inputs rather than real visitor data.

## Commits and Pull Requests

No project commit history is available to establish a message convention. Use concise, imperative commit subjects that describe the change, such as `Improve mobile map layout`. Pull requests should explain the user-visible change and manual checks performed; include desktop/mobile screenshots for visual changes and link a related issue when one exists.

## Security and Configuration

Treat endpoint URLs and location data as sensitive. Do not add credentials, private coordinates, or real user data to source control, screenshots, or logs. Keep location collection transparent and preserve the browser's permission flow; avoid broadening the data sent without documenting the reason.
