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
