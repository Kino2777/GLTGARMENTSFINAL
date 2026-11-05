# G.L.T. Garments Demo

## How to Open in VS Code

1. Extract this ZIP file into a folder on your computer.
2. Open **Visual Studio Code**.
3. Go to **File > Open Folder...** and select the extracted folder.
4. To view the website live:
   - Make sure you have the **Live Server** extension installed in VS Code.
   - Right-click on `GLT GARMENTS DEMO.html` and select **Open with Live Server**.

## Order, Deposit, and Pickup Workflow

- Checkout offers **Face-to-Face / In-Shop Payment** and calculates the grand total, 50% deposit, and balance due at pickup. Enter approved custom add-ons in the add-ons field.
- A submitted order waits for in-person deposit verification. Admin test login: **admin123 / 123**; client test login: **user123 / 123**.
- In the Admin Dashboard, confirm the deposit to start production, then mark the finished order ready for pickup. The client sees the updated tracker and can schedule or reschedule pickup.
- Pickup appointments are available Monday-Saturday, from 9:00 AM through 5:00 PM, on the next business day through 14 days after completion. A maximum of five appointments can be scheduled per calendar day; Sundays are closed.
- The Admin Dashboard's **Pickup Appointments** tab shows the daily schedule, remaining capacity, and balance due.

This is a browser-only demo: job orders are stored in the current browser's local storage, and dashboard alerts are in-app only. It does not send real email/SMS or synchronize data between different browsers/devices. A production deployment needs an authenticated backend and shared database for those capabilities.

## Website Sections

- **Landing page:** Starts with the About Us and five-step ordering timeline, followed by the interactive **Pick Your Style** apparel hero, the **Customer Reviews & Proof of Orders** gallery, and the **Contact Us** section with contact details and a shop map. Proof photos go in `GLTGARMENTSFINAL-main/images/`; the current files are `images/PROOF1.jpeg`, `images/PROOF2.jpeg`, and `images/PROOF3.jpeg`. Edit the `PROOF_ORDERS` array near the top of the main script in `index.html` to change captions or add orders; paths with spaces and `.jpg`, `.jpeg`, `.png`, or `.webp` extensions are supported. Reviews can be edited in the adjacent `CUSTOMER_REVIEWS` array. Review identities, ratings, and trust counters are sample placeholders; replace them with verified customer information before publishing. Contact information and weekday opening hours are in the `CONTACT_CONFIG` object near the top of the script in `index.html`. The current contact email is `gltgarments27@gmail.com`, the Facebook page is **G.L.T. GARMENTS**, and the shop is **Gold St. Sanrafael Village Davao City, beside Floretnine Building**. Its map pin uses `7.083921, 125.596962`; update `mapUrl` or `mapCoordinates` there if needed. The About collage currently uses the transparent garment cutouts; its `data-image-placeholder` attributes list suggested photo paths to swap later. The product catalog and bulk-order portal require a signed-in account; guests are prompted to log in or register before either page opens.
- **Featured products:** The signed-in **Made for your people** grid is generated from `CATALOG_ITEMS` in `index.html`. Edit a product's `images` array to add alternate views; `badge` controls the card badge. The category filters, search, sort, quick-view estimates, and wishlist use that same product data. Wishlist choices are stored in this browser only. The existing base prices, minimum orders, and **Order Now** actions still use the existing order portal and product IDs; the catalog's **T-Shirts & PE** filter includes both T-shirts and PE Uniforms.
- **Category slideshow:** The signed-in **Made for your people** section has three editable slides in `CATEGORY_SLIDES` in `index.html` (Jerseys, T-Shirts & Polos, and PE Uniforms). Slide images are `images/SPORTS_JERSEYS-removebg-preview.png`, `images/TSHIRT_POLO_SHIRT-removebg-preview.png` plus `images/COMPANY_POLO_SHIRTS-removebg-preview.png`, and `images/PE_UNIFORMS-removebg-preview.png`, respectively. Starting prices and minimum quantities are pulled from the matching `CATALOG_ITEMS` records; change those records' images to update the slides. While signed in, the Home dashboard shows **Made for your people**, the customer trust bar, final call-to-action, and footer; the other landing-page sections return after logout.
- **Dashboard:** Clients use **My Orders** to track jobs; the admin account uses the **Admin Dashboard** to manage production and pickups. Sign in to access either workspace.
- **Admin catalog and dashboard storage:** Admin **Products & Pricing** edits use the same `CATALOG_ITEMS` data that feeds the public product cards, catalog filters, slideshow pricing/images, and order-product dropdown. Changes are persisted in the browser's `localStorage` under `glt-garments-catalog-v1`; category order/names, change history, business settings, and dark-mode preference use separate browser-local keys. Uploaded catalog images are resized and stored as WebP data in that browser's local storage; for production, store images on a server and keep only their URLs in the product records. This does not synchronize between browsers or devices.
- **Admin security limitation:** The dashboard checks the current browser session's `admin` role, but this standalone demo has no trusted server and its role check can be bypassed by a user who controls the browser. Do not use it to protect real customer data or pricing. A production deployment must enforce admin authorization and validate changes on the server, with shared database access rules. The admin settings form updates the public contact information and optional announcement in this browser; it does not change authentication passwords or server-side settings.
- **About page:** Explains who G.L.T. Garments serves, its mission, and the custom apparel it offers.
- **Contact page:** Provides phone, email, social links, and a message form that opens a prefilled email.

## Authentication

- Use **Login / Register** to open the dedicated sign-in and account-creation frame. Client accounts land in **My Orders**; the admin account lands in the **Admin Dashboard**.
- Sign in or create an account to unlock **Catalog & Pricing**, **Bulk Order Portal**, and the landing page's featured product cards.
- Active sign-in sessions are kept in this browser's local storage until logout. **Remember Me** stores only the username/email for convenience. The static demo does not provide server-side authentication or password recovery; its sample accounts are for demonstration only.
- Do not use real customer credentials with this static demo. A production release should replace the browser-only demo authentication with a secure server-side identity provider.
