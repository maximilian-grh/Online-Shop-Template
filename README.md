### Tech Stack

- JavaScript
- Next.js
- Tailwindcss
- Herocions
- Stripe [Customer, Product, Payments]
- Auth0 [User Login / Registraion]

---

### Workflow Auth

Auth0 is used for user login and registration. This user data is synced with Stripe via a custom trigger, which adds the Stripe customer ID to the access token, links the user to Stripe, and fully integrates Stripe.

#### Client Page

If the client needs to update his client information (name, email, shipping and so on) he can do it with the "edit-icon". This function allows updating all client data in real time, which is very efficient because the webshop owner doesn't need to edit data manually.

**The Client sees all data & ready to update:**

- Name
  - Full Name
- E-Mail
- Phone Number
- Customer ID
- Shipping Adress
- Payment Method
  - Type
  - Last 4 Numbers
  - Residue

**This is not included to edit as a client:**

- Last 4 Orders
  - Amount
  - Date
  - Status
  - Invoice .pdf

---

### Testing

To check if all dependencies match the latest package version run:

    ncu
    ncu -u (for upgrade)

---

### AUTH0 Custom Actions for Stripe Sync

- Stripe Full Integration
  (see file: custom_actions/stripe_auth.txt)

- Link User to Stripe
  (see file: custom_actions/stripe_auth_linking.txt)

- Add Stripe Customer ID to Access Token
  (see file: custom_actions/stripe_auth_token.txt)

---

### Getting started

1. git clone
2. npm install
3. Configure the Auth0 SDK for env.
4. For AUTH_SECRET - run: openmssl rand -hex 32
5. Add the Auth0 Keys, IDs & Domain

###### Snippet:

    AUTH0_SECRET='use [openssl rand -hex 32] to generate a 32 bytes value'
    AUTH0_BASE_URL='http://localhost:3000'
    AUTH0_ISSUER_BASE_URL='https://{yourDomain}'
    AUTH0_CLIENT_ID='{yourClientId}'
    AUTH0_CLIENT_SECRET='{yourClientSecret}'

---

### Git Commits Legend

- **Add** | Description
  - Packages, Functions, File Structure, Description
- **Fix** | Description
  - Bugs
- **Frontend** | Description
  - Styles, Components
- **Backend** | Description
  - APIs
- **Test** | Description
  - Unit Test, Component Test, Integration Test, E2E Test
