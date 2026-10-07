# Jersey United Cricket Club — FREE Render Static Site

All website source and assets are included. This version uses React + Vite and Render's free Static Site hosting. The shared form sends enquiries directly to `njerseyunited@gmail.com` through FormSubmit. There is no paid server, disk, or separate submissions database.

## 1. Upload to GitHub

1. Extract the ZIP.
2. Create a GitHub repository, for example `jersey-united-cricket-club`.
3. Upload the **contents** of `jersey-united-render` to the repository root. You should see `package.json`, `package-lock.json`, `index.html`, `render.yaml`, `src/`, and `public/` directly in the repository.
4. Do not upload the ZIP itself, `node_modules`, or any personal secrets.

## 2. Deploy on Render for free

1. Sign in to Render and connect GitHub.
2. Choose **New → Static Site** (not Web Service).
3. Select the repository.
4. Use these settings:

| Setting | Value |
|---|---|
| Name | `jersey-united-cricket-club` |
| Branch | `main` (or your repository's branch) |
| Root directory | Leave blank |
| Build command | `npm ci && npm run build` |
| Publish directory | `dist` |
| Environment variable | `NODE_VERSION=24.19.0` |

5. Create the Static Site. Open its `https://...onrender.com` URL once deployment succeeds.

Alternatively, choose **New → Blueprint** and select the repository. The included `render.yaml` declares a Static Site; it does not provision a paid web service or disk.

## 3. Activate email notifications

1. Submit an enquiry from your deployed website.
2. Open `njerseyunited@gmail.com` and check Inbox and Spam for FormSubmit's activation email.
3. Click the activation link.
4. Submit a second test enquiry and confirm its notification arrives.

A new website URL may require activation even if the earlier ChatGPT-hosted website was activated. Email delivery has not yet been verified. The form keeps input visible if the provider rejects a submission or the network fails. Successful provider acceptance does not itself prove inbox delivery.

The form uses FormSubmit's AJAX endpoint and sends name, email, enquiry type, message, and recruitment details when selected. Reply-To is the submitter's address. No Gmail password or API key is required. The consent and privacy note identify this processing.

## Important storage difference

This free static version has **no separate submissions database**. Keep your notification emails as your records. Previously saved submissions remain on the original ChatGPT-hosted website; they are not included in this ZIP. FormSubmit's documented submission archive is retained for 30 days, so do not treat that as a permanent backup.

## Editing and local preview

Install Node 24, then run:

```sh
npm ci
npm run dev
```

For a production preview:

```sh
npm run build
npm run preview
```

- `src/App.tsx`: all page sections and the shared form.
- `src/styles.css`: colours, typography, responsive styles.
- `public/cricket-hero.png`: generated cricket hero photograph.
- `public/favicon.svg`: favicon.
- `index.html`: page title and description.
- `render.yaml`: free static deployment settings.

The email recipient appears in the FormSubmit URL in `src/App.tsx`. To change it, change that address and activate the new inbox. The club email is visible in the browser's source/network requests; it is not a secret.

Changes committed to the connected GitHub branch can redeploy automatically on Render. Your existing ChatGPT-hosted site is not changed or redirected by this package.

## Documentation

- https://render.com/docs/static-sites
- https://render.com/docs/blueprint-spec
- https://formsubmit.co/ajax-documentation
- https://formsubmit.co/documentation
