# Northstar Relay Honeypot Site

A self-contained static decoy website designed to resemble an internal ecommerce and operations environment.

## Pages

- `index.html` - Northstar Supply Co. storefront with product browsing, search, category filters, and a client-side cart.
- `payment.html` - Simulated checkout page with inline QR payment visuals, wallet switching, order summary, and a fake card payment form.
- `admin-login.html` - Fake staff login page. Submissions always show an invalid-credentials message and send nothing.
- `dashboard.html` - Fake internal operations dashboard reachable through the storefront footer and staff links.

## Supporting Files

- `style.css` - Shared responsive styles for the storefront, checkout, login, and dashboard.
- `robots.txt` - Intentionally permissive crawler configuration.
- `decoy-files/` - Harmless synthetic files such as `.env`, `config.php`, and deployment notes.

## Local Preview

From the repository root:

```sh
cd honeypot-site
python3 -m http.server 8765
```

Open `http://localhost:8765/` in a browser.

## Behavior

The site is static and has no backend. Cart contents are stored only in browser `localStorage` while moving from the storefront to checkout. Payment forms, QR choices, and checkout confirmation are simulated and do not process, transmit, or store real payment information.

The site does not connect to or modify any honeypot listener. Serve this directory from the existing HTTP-facing web root as needed.
