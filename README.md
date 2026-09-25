# E-Commerce Website

A multi-page storefront prototype built with HTML, CSS, JavaScript, and Bootstrap as a VCU team coursework project.

**[View live demo](https://vladimir-paraschiv.github.io/E-Commerce-Website/)**

The application demonstrates a browser-based shopping experience: browse and filter products, view product details, compare items, save a wishlist, manage a cart, and complete a simulated checkout. Shopping state is stored locally in the browser, with no backend or database required.

**Status:** Frontend prototype. Checkout does not process payments or create real orders. Use fictional information when trying the checkout form.

## My contributions

**Vladimir Paraschiv — Frontend Developer, Project Manager, and GitHub Administrator**

- Applied typography, colors, iconography, and theme styling to the home page (`index.html`) and product comparison page (`compare.html`).
- Implemented JavaScript to highlight the current navigation section, including treating the comparison page as part of the catalog.
- Implemented active breadcrumb highlighting on the comparison page to clarify the user's location.
- Served as project manager alongside frontend development responsibilities.
- Acted as the team's point of contact with the professor.
- Administered the team's GitHub repository.

My frontend contributions are documented in [my original contributor report](README-Vladimir-Paraschiv.md). The features below describe the team's combined application.

## Features

- **Product catalog:** Dynamically rendered sample products with filters for price, device type, and compatibility.
- **Product details:** Display the selected product and provide controls for adding it to the cart, wishlist, or comparison list.
- **Product comparison:** Compare up to four selected products, remove selections, and access product details and reviews.
- **Wishlist:** Save and remove items using browser storage.
- **Shopping cart:** Change quantities, confirm item removal, clear the cart, and calculate totals.
- **Simulated checkout:** Validate required form fields, display an order summary and confirmation modal, and clear the cart after submission.
- **Product reviews:** Display sample reviews and save new ratings and written reviews locally.
- **Home page:** Display recently viewed and wishlisted products from browser storage.
- **Responsive styling:** Use Bootstrap layouts and a collapsible catalog filter sidebar for different screen sizes.

## Technology

| Area | Technology |
| --- | --- |
| Page structure | HTML5 |
| Styling | CSS, Bootstrap 5, Bootswatch Lux |
| Interactivity | Vanilla JavaScript and DOM events |
| Browser persistence | `localStorage` |
| Visual assets | Bootstrap Icons and Google Fonts |

## Run locally

No npm installation or build step is required. Serve the repository with a static web server so all pages share the same browser storage origin.

With Git and Python 3 installed:

```bash
git clone https://github.com/Vladimir-Paraschiv/E-Commerce-Website.git
cd E-Commerce-Website
python -m http.server 8000
```

If your system uses `python3`, run `python3 -m http.server 8000` instead.

Open **http://localhost:8000/**. Keep the same hostname and port while exploring the site because browser storage is specific to the origin. Internet access is needed for the CDN-hosted styles, scripts, icons, and fonts.

## Project structure

| File | Purpose |
| --- | --- |
| `index.html` | Home page, recently viewed items, and wishlist previews |
| `catalog.html` | Sample product data, product rendering, and filters |
| `description.html` | Selected product details and shopping actions |
| `compare.html` | Product comparison and navigation highlighting |
| `wishlist.html` | Saved products and removal controls |
| `review.html` | Product reviews, ratings, and review submission |
| `Cart.html` / `cart.js` | Cart interface, quantities, persistence, and totals |
| `checkout.html` / `checkout.js` | Checkout form, validation, and simulated confirmation |
| `styles.css` | Shared custom styles used by cart and checkout |
| `README-*.md` | Individual contribution and AI-assistance reports |

Several pages contain their JavaScript and CSS inline. The cart and checkout pages use separate JavaScript files.

## How state is shared

The catalog stores a selected product before navigating to its detail page. Other pages read and update shared `localStorage` entries such as `cart`, `wishlist`, `compareList`, `selectedProduct`, and `recentlyViewed`. Reviews use product-specific storage keys.

This approach demonstrates state persistence across separate HTML pages without a server. Data remains in the same browser and origin; it is not shared between users or devices.

## Testing

No automated test suite is included. Suggested manual checks:

1. Filter the catalog by price, device type, and compatibility, then reset the filters.
2. Open a product, save it to the wishlist, and reload the wishlist page.
3. Add multiple products to comparison and remove one.
4. Add a product to the cart, change its quantity, and check the total after reloading.
5. Try an incomplete checkout form, then complete it using fictional details and confirm that the cart clears.
6. Submit a product review and reload that product's review page.
7. Check navigation and the catalog filter sidebar at desktop and mobile widths.

## Known limitations and future improvements

- Products and imagery are sample data and placeholders; there is no live inventory, account system, payment integration, or order service.
- Search controls are not fully wired to catalog filtering, and some footer and deals links are placeholders or point to missing destinations.
- Some links use `cart.html` although the filename is `Cart.html`, which causes failures on case-sensitive hosts.
- Product detail navigation relies on a shared `selectedProduct` entry; direct links and some alternate navigation paths can show stale or missing product information. Product IDs in URLs would make navigation more reliable.
- Some Buy Now links navigate to checkout without adding the selected product to the cart.
- Future work includes consolidating duplicated styles and storage helpers, improving input rendering and storage validation, and adding automated tests for shopping flows.

## Team and development notes

- [Vladimir Paraschiv](README-Vladimir-Paraschiv.md)
- [Adrian Patterson](README-Adrian-Patterson.md)
- [Katang Phuthongthiam](README-Katang-Phuthongthiam.md)
- [Krishna Patel](README-Krishna-Patel.md)

The original contributor reports document individual responsibilities and disclosed AI assistance during development.
