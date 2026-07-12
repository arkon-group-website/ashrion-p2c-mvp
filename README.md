# ASHRION P2C MVP Demo

Static clickable ASHRION P2C Play2Career MVP demo for deployment on Vercel.

## Local Build

```bash
npm run build
```

Preview the built static site:

```bash
npm run preview
```

Then open:

```text
http://localhost:4173
```

## Deployment Shape

- Source: this repository
- Framework preset: Other
- Build command: `npm run build`
- Output directory: `dist`
- Production domain: `p2c.ashridigital.com`

## Environment Variables

The current static MVP does not require environment variables.

When real AI/auth/backend features are added, keep secrets out of Git and configure them only in the deployment provider, such as Vercel project environment variables.
