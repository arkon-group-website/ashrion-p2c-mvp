# Safe Deployment Checklist

## Current Status

- Demo type: static HTML/CSS/JavaScript MVP.
- Required environment variables: none.
- Secret scan result: no API calls or obvious key/token patterns found in `index.html`.
- Recommended deployment: Vercel project connected to a GitHub repository.

## GitHub

1. Create a new GitHub repository, for example `ashrion-p2c-mvp`.
2. Keep it private if the MVP is still confidential.
3. Add the repository remote locally:

```bash
git remote add origin https://github.com/YOUR_ORG_OR_USERNAME/ashrion-p2c-mvp.git
```

4. Push the initial branch:

```bash
git push -u origin main
```

## Vercel

1. In Vercel, import the GitHub repository.
2. Use framework preset `Other`.
3. Set build command to `npm run build`.
4. Set output directory to `dist`.
5. Deploy the project.
6. Add the custom domain `p2c.ashridigital.com` in Vercel project settings.

## DNS

In Hostinger DNS for `ashridigital.com`, create the exact DNS record Vercel asks for after you add `p2c.ashridigital.com` to the Vercel project.

Typical subdomain shape:

```text
Type: CNAME
Name: p2c
Value: copy the exact Vercel-provided CNAME target
```

Vercel currently provides project-specific CNAME targets for subdomains, so do not guess the value.

## Secrets

The current static demo needs no secrets.

For a future full ASHRION P2C app, likely variables may include:

```text
OPENAI_API_KEY
NVIDIA_NIM_API_KEY
SUPABASE_URL
SUPABASE_ANON_KEY
SUPABASE_SERVICE_ROLE_KEY
DATABASE_URL
```

Keep server-side keys such as `OPENAI_API_KEY`, `NVIDIA_NIM_API_KEY`, `SUPABASE_SERVICE_ROLE_KEY`, and `DATABASE_URL` out of client-side code. Add them only in Vercel environment variables or backend hosting secrets.

## Final Checks Before Public Demo

1. Run `npm run build`.
2. Open the `dist/` preview and click through all demo screens.
3. Confirm all outbound links point to the intended ASHRI Digital pages.
4. Confirm no `.env` files are tracked by Git.
5. Confirm Vercel production deployment is using HTTPS.
6. Add a button on `ashridigital.com` linking to `https://p2c.ashridigital.com`.
