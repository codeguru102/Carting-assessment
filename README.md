# Carting Assessment

A full-stack e-commerce shopping cart application built with React and Node.js, featuring Stripe payment integration.

## Tech Stack

**Frontend:** React 18, Redux Toolkit, React Router, Tailwind CSS, Vite  
**Backend:** Node.js, Express.js, MongoDB, Mongoose  
**Auth:** JWT (HttpOnly cookies), bcrypt  
**Payments:** Stripe Checkout

## Features

- User registration and authentication
- Product browsing and details view
- Shopping cart with quantity management
- Stripe payment integration
- Dark/Light mode toggle
- Responsive design

## My Implementation: Buy All Feature

As part of this assessment, I implemented the **"Buy All"** feature on the cart page:

### Buy All Button
- Professional blue-purple gradient button in the Order Summary section
- Displays total price inline on the button
- Disabled state when cart is empty
- Smooth hover animations

### Confirmation Modal
- Opens when "Buy All" is clicked
- Displays order summary (items count, total quantity, total price)
- Two action buttons:
  - **Yes, Buy All** - Proceeds with purchase via Stripe
  - **No, Cancel** - Closes modal without changes
- Loading state with spinner during API call
- Backdrop blur with click-to-close functionality
- Smooth slide-in animation

## Getting Started

### Prerequisites
- Node.js 18+
- MongoDB
- Stripe account

### Installation

1. Clone the repository
```bash
git clone https://github.com/yourusername/Carting-assessment.git
cd Carting-assessment
```

2. Install dependencies
```bash
npm install
cd server && npm install
```

3. Set up environment variables

**Root `.env`:**
```
VITE_SERVER_URL=http://localhost:3000
```

**`server/.env`:**
```
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
STRIPE_KEY=your_stripe_secret_key
ORIGIN=http://localhost:5173
```

4. Run the application
```bash
npm run dev
```

This starts both the frontend (port 5173) and backend (port 3000) concurrently.

## Project Structure

```
├── src/                    # Frontend React app
│   ├── app/               # Redux store and slices
│   ├── components/        # Reusable components
│   ├── pages/             # Page components
│   └── helpers/           # Utility functions
├── server/                 # Backend Express app
│   ├── controllers/       # Route handlers
│   ├── middlewares/       # Auth middleware
│   ├── models/            # Mongoose schemas
│   └── routes/            # API routes
└── public/                 # Static assets
```

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | Create account |
| POST | `/api/auth/login` | Login |
| GET | `/api/auth/user` | Get current user |
| GET | `/api/auth/logout` | Logout |
| POST | `/api/cart/add` | Add item to cart |
| DELETE | `/api/cart/remove/:id` | Remove item |
| POST | `/api/cart/increment/:id` | Increase quantity |
| POST | `/api/cart/decrement/:id` | Decrease quantity |
| POST | `/api/cart/checkout` | Create Stripe session |
| GET | `/api/cart/clear` | Clear cart |