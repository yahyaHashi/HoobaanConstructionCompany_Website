# Hoobaan Construction Company Website

Static production website for Hoobaan Construction Company, built with HTML, Tailwind CDN, JavaScript, image assets, and video assets.

Live canonical URL:

`https://www.hoobaanconstruction.com/`

## Pages

- `index.html` - home page, company overview, featured services, video preview, and contact section.
- `about.html` - company story, values, team, and call to action.
- `services.html` - construction, design, consultancy, and finishing services.
- `Projects.html` - completed projects, interior work, 3D visualization, gallery, and video lightbox.
- `AdnaDhiso.html` - client project request flow that prepares a WhatsApp message.

## SEO

The site includes production SEO basics:

- Page-specific titles and meta descriptions.
- Canonical URLs using the `www` domain.
- Open Graph and Twitter preview metadata.
- Local business structured data on the home page.
- `robots.txt`.
- `sitemap.xml`.
- Google Search Console verification file.

Google Search Console is verified and the sitemap has been submitted successfully with 5 discovered pages.

## Deployment

The site is deployed through cPanel Git deployment. The deployment task in `.cpanel.yml` copies the HTML pages, SEO files, verification file, `.htaccess`, and image assets into `public_html`.

Important deployment files:

- `.cpanel.yml` - cPanel deployment copy tasks.
- `.htaccess` - redirects all traffic to `https://www.hoobaanconstruction.com/`.
- `robots.txt` - crawler access and sitemap location.
- `sitemap.xml` - pages submitted to Google.
- `googled81049e85dc3ae38.html` - Google Search Console ownership verification file.

## Security Notes

- No passwords, API keys, private keys, database credentials, or tokens are stored in this repository.
- `.cpanel.yml` is public and reveals the server deploy path. It is not a password, but if hosting privacy is a concern, keep the repository private or move deployment to a private workflow.
- The Google verification HTML file is intentionally public and should remain deployed so ownership stays verified.
- Do not commit `.env` files, cPanel login details, FTP credentials, analytics secrets, or private keys.

## Maintenance

- Keep image and video assets optimized for page speed.
- Keep large video assets under GitHub file size limits.
- After major content or URL changes, update `sitemap.xml` and resubmit it in Google Search Console.
- Test mobile responsiveness before publishing new layout changes.
