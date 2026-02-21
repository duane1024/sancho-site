# Ask Sancho Website

First draft static site for `asksancho.ai`.

## Local preview

```bash
cd /home/ubuntu/projects/sancho-site
python3 -m http.server 8080
```

Then open: http://localhost:8080

## Deploy target

Cloudflare Pages (production branch: `master`).

## Optional: Cloudflare Web Analytics

In Cloudflare dashboard for this site, enable Web Analytics and add the provided token/script in `index.html` before `</body>` if you want visitor metrics.

## Contact form via Cloudflare Worker

Form posts to `/api/contact` and should be backed by the worker in `cloudflare-worker/`.

### Deploy worker

```bash
cd /home/ubuntu/projects/sancho-site/cloudflare-worker
npm i -g wrangler
wrangler login
wrangler secret put RESEND_API_KEY
wrangler deploy
```

Then in Cloudflare dashboard for worker `asksancho-contact`, add route:

- `asksancho.ai/api/contact`

This keeps contact form handling on your own Cloudflare stack (no third-party form relay).
