# Deep Link Hosting Setup

This folder contains the Apple App Site Association (AASA) file needed for Universal Links.

## Setup Instructions

### Option 1: GitHub Pages

1. Create a new GitHub repository (e.g., `superapp-links`)
2. Copy the `.well-known` folder to the repository root
3. Enable GitHub Pages in repository Settings > Pages
4. Your AASA file will be available at: `https://YOUR-USERNAME.github.io/superapp-links/.well-known/apple-app-site-association`

### Option 2: Netlify

1. Create a new site on Netlify
2. Drag and drop this `DeepLinkHosting` folder
3. Your AASA file will be available at: `https://YOUR-SITE.netlify.app/.well-known/apple-app-site-association`

## Important Notes

- The file must be served with `Content-Type: application/json`
- Must be accessible via HTTPS without redirects
- No `.json` extension on the filename

## Verification

After hosting, verify the file is accessible:
```bash
curl -I https://YOUR-DOMAIN/.well-known/apple-app-site-association
```

The response should include:
- HTTP 200 status
- `Content-Type: application/json`

## QR Code URL Examples

Once hosted, generate QR codes with these URLs:

```
https://YOUR-DOMAIN/sendmoney?amount=500&recipient=09171234567
https://YOUR-DOMAIN/pay?merchantId=ABC123&amount=100
https://YOUR-DOMAIN/receive?amount=1000
https://YOUR-DOMAIN/profile?userId=12345
https://YOUR-DOMAIN/web?url=https://example.com&title=Example
https://YOUR-DOMAIN/dynamic?code=PROMO2024&ref=abc123
```

