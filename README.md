# THREADLINE — clothing store (Econt + email orders)

Responsive storefront with product browsing, category filters, search, sizes, cart, checkout and a Netlify backend function.

## Checkout and delivery
- Payment: cash on delivery (customer pays the courier).
- Delivery: customer chooses Econt office or Econt address delivery and enters the office/address and city.
- Econt shipments are created manually by the store owner in Econt's system. This project does NOT create Econt waybills automatically and does not calculate the courier fee. Confirm the delivery fee with the customer before dispatch.
- New orders are emailed to `alexandrstefanov1@gmail.com` using Resend.

## Deploy using an Android phone (GitHub + Netlify)
1. Create a GitHub repository named `threadline-store`.
2. Upload the CONTENTS of this project to the repository root, preserving the `netlify/functions/order.js` folder structure.
3. In Netlify, choose **Add new site → Import an existing project → GitHub**, select `threadline-store`, and deploy.
4. In Netlify site settings, open **Environment variables** and add:
   - `RESEND_API_KEY` = your secret API key from Resend
   - `STORE_ORDER_EMAIL` = `alexandrstefanov1@gmail.com`
5. Trigger a redeploy after adding the variables.

## Configure email with Resend
1. Create an account at https://resend.com/
2. Create an API key in the Resend dashboard.
3. Add it to Netlify as `RESEND_API_KEY`. Keep it secret; never put it in browser code or commit it to GitHub.
4. This starter uses Resend's `onboarding@resend.dev` sender. In Resend's test mode, delivery is restricted to the email address associated with your Resend account. To send order emails to other recipients reliably, verify a domain you own in Resend and change the `from` address in `netlify/functions/order.js` to an address on that verified domain.
5. Set `STORE_ORDER_EMAIL` to the inbox where you want to receive orders.

## Important before accepting real orders
- This is a starter storefront, not a complete audited e-commerce platform. It does not save orders in a database. Keep a secure order record and test the full flow.
- Replace sample products, photos, prices, brand copy and contact details with your real information.
- Publish accurate privacy, terms, delivery and returns policies for Bulgaria/EU before taking real customer orders.
- The order form collects personal data. Handle it securely and only for legitimate order fulfilment.
- The checkout total excludes Econt shipping. Confirm shipping cost with the customer before dispatch.
- Test an order after deployment. Never place a real order just to test the form.

## Edit products
Edit `products.js`. Product fields include `id`, `name`, `category`, `price` (EUR), `tag`, `color`, `sizes`, `image`, and `description`.
