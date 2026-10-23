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

- **Landing page:** Introduces G.L.T. Garments and guides visitors to products and bulk ordering.
- **Dashboard:** Clients use **My Orders** to track jobs; the admin account uses the **Admin Dashboard** to manage production and pickups. Sign in to access either workspace.
- **About page:** Explains who G.L.T. Garments serves, its mission, and the custom apparel it offers.
- **Contact page:** Provides phone, email, social links, and a message form that opens a prefilled email.

## Authentication

- Use **Login / Register** to open the dedicated sign-in and account-creation frame. Client accounts land in **My Orders**; the admin account lands in the **Admin Dashboard**.
- Active sign-in sessions are kept in this browser's local storage until logout. **Remember Me** stores only the username/email for convenience. The static demo does not provide server-side authentication or password recovery; its sample accounts are for demonstration only.
- Do not use real customer credentials with this static demo. A production release should replace the browser-only demo authentication with a secure server-side identity provider.
