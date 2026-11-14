# HCI-AL-AHLY
Learnbridge ALAHLY
## Run locally

Install [Node.js](https://nodejs.org/) version 18 or newer.

1. Download this repository and extract it.
2. Open a terminal in the project folder.
3. Start the application:

```bash
npm start
```

4. Open **http://localhost:4173** in your browser.

No additional packages, API keys, or accounts are required. Press **Ctrl+C** in the terminal to stop the server.

## Deploy online

The application is a static website. Deploy it using a static hosting service with these settings:

- **Build command:** Leave empty.
- **Publish/output directory:** `dist`

The `dist` folder contains the complete website. Share the URL provided by your hosting service after deployment.

## Test

Run the workflow tests:

```bash
npm test
```

Check JavaScript syntax:

```bash
npm run check
```

## Demonstration

Choose the student role to upload a sample exam, then switch to the teacher role to verify answers, review marks, and publish feedback.

OCR, AI grading, and learning-gap suggestions are simulated. Demo data is saved in the current browser; different browsers and devices do not share progress.
