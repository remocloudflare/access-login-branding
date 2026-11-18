# Access login branding

Branding assets for the `ciaoremo` Cloudflare Access team domain.

| File | Purpose |
|---|---|
| `landing-art.png` | Image for the App Launcher landing page (800x800, transparent corners; shown at up to 400x400) |
| `landing-art.svg` | Editable source for the image |
| `access-login-page.liquid.html` | Access custom **Login** page template (HTML and Liquid) |

## Landing page image

The landing page (`/#/NoAuth`) needs a public HTTPS image URL:

```text
https://raw.githubusercontent.com/remocloudflare/access-login-branding/main/landing-art.png
```

Set it in Zero Trust > Reusable components > Custom pages > App Launcher customization.
The landing page background is not customizable; only title, message, image, logo and button colors apply.

Suggested settings: button color `#3c503d`, button text color `#ffffff`.

## Login page template

Create a custom page of type **Login** (Zero Trust > Reusable components > Custom pages > Access custom pages),
paste `access-login-page.liquid.html`, publish, and assign it to an application or set it as the account default.
The template uses no inline SVG (the validator rejects it) and keeps exactly one `<cf-access-authbox>`.

Re-render the PNG from the SVG with headless Chrome:

```sh
chrome --headless --default-background-color=00000000 --window-size=800,800 --screenshot=landing-art.png landing-art.svg
```
