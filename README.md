# BAKEY - Cake Business Management App

BAKEY is a mobile application designed to help manage a cake-making business. It brings customer-facing ordering flows and business-management tools together in one app, including cake browsing, cart and checkout, order tracking, inventory, and an admin dashboard.

This repository contains the **frontend** of the project, built with React Native and Expo. The app communicates with a separate backend API.

## Features

### Customer experience
- **Account access:** sign-up, login, email verification, and password recovery flows.
- **Cake catalog:** browse cakes and view product details, images, ingredients, descriptions, and prices.
- **Cart and checkout:** manage cart items, review totals, choose a payment method, and submit an order.
- **Orders:** view order information and access order-related flows.
- **Delivery scheduling:** select a delivery date and check its availability through the API.
- **Profile management:** update profile details and profile picture.
- **Account security:** change password and manage recovery-email settings.
- **Cake customization UI:** select cake decorations.

### Administration
- Admin dashboard and panel.
- Inventory management screen.
- Statistics screen.

> Feature availability depends on the corresponding backend endpoints and configuration. A screen in the frontend does not necessarily mean that a related external service (such as payment processing) is fully integrated.

## Tech stack

- **React Native** - cross-platform mobile UI.
- **Expo** - app development and runtime tooling.
- **Expo Router** - file-based navigation and route organization.
- **TypeScript / JavaScript** - application code.
- **React Navigation** - navigation components.
- **Axios and Fetch API** - HTTP requests to the backend.
- **AsyncStorage** - local storage for session-related values.
- **Jest and jest-expo** - testing setup.

## Project structure

```text
app/
├── (tabs)/                 # Main customer tab navigation
├── (admintabs)/            # Admin tab navigation
├── product/[id].jsx        # Dynamic product route
├── index.tsx               # Login / entry screen
├── SignUpScreen.tsx        # Registration
├── ProductDetailsScreen.tsx
├── CartScreen.tsx
├── OrdersScreen.tsx
├── CheckoutScreen.tsx
├── InventoryScreen.tsx     # Located in (admintabs)
├── StatisticsScreen.tsx    # Located in (admintabs)
├── styles/                 # Screen-specific styles
└── utils/                  # Shared screen utilities
components/                 # Reusable UI components
constants/                  # Shared constants, including colors
hooks/                      # Theme-related hooks
config.js                   # Backend API base URL
```

The repository also includes additional screens for delivery dates, profile editing, account security, saving draft orders, and duplicating orders.

## Getting started

### Prerequisites

Install the following before running the project:

- [Node.js](https://nodejs.org/) (an LTS release is recommended)
- npm
- [Expo Go](https://expo.dev/go) for compatible device testing, or an Android/iOS development environment

### 1. Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd avielesperansa-finalproject-frontend
```

Replace `<YOUR_GITHUB_REPOSITORY_URL>` with the repository's actual Git URL.

### 2. Install dependencies

```bash
npm install
```

### 3. Configure the backend API

Open `config.js` and set `BASE_URL` to the address where your backend API is running:

```js
const config = {
  BASE_URL: "http://YOUR_COMPUTER_LAN_IP:3000",
};

export default config;
```

Use the actual host and port for your backend. When testing on a physical phone, `localhost` usually refers to the phone itself, not your development computer; use the computer's reachable local network IP address instead. Make sure the phone and computer can reach each other and that the backend accepts connections.

The backend is maintained separately and must be running for API-backed functionality such as login, cake data, cart operations, and order submission to work.

### 4. Start the app

```bash
npx expo start
```

Then follow the Expo CLI instructions to open the app in Expo Go, an emulator, or a simulator.

Useful scripts:

```bash
npm start       # Start Expo
npm run android # Start on Android
npm run ios     # Start on iOS
npm run web     # Start for web
npm test        # Run Jest in watch mode
npm run lint    # Run Expo lint
```

## API configuration notes

The frontend uses the `BASE_URL` value exported from `config.js` to build backend request URLs. Before testing, confirm that:

- The backend is running at the configured address.
- The backend routes and response formats match the frontend requests.
- Authentication tokens are returned and handled as expected.
- Any required email, database, or payment services are configured on the backend.

Do not commit private API keys, passwords, production credentials, or other secrets to the repository. For a production release, use an appropriate environment-specific configuration and secure credential handling.

## Testing

Run the configured Jest test suite with:

```bash
npm test
```

The repository includes a Jest/Expo test setup and a sample component test.

## Future improvements

Potential areas for continued development include:

- A richer visual cake builder with draggable decoration elements.
- More comprehensive order and business-expense reporting.
- Production-ready payment-provider integration.
- Automated end-to-end tests and improved environment configuration.

These are possible next steps, not a claim that they are already implemented.

## Project status

BAKEY is a software engineering project focused on simplifying cake-business workflows through a mobile-first interface. The frontend is organized into customer and administrator areas and integrates with a separately hosted backend API.

## License

No license is specified yet. Add a `LICENSE` file before distributing the project under an open-source license.
