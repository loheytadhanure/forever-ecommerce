# 🛍️ FOREVER

### Full-Stack E-Commerce Platform with Razorpay Payment Integration

FOREVER is a full-stack e-commerce platform built to provide a complete online shopping experience — from product discovery and cart management to **secure online payment and order processing**.

The application integrates **Razorpay Payment Gateway** with a Node.js/Express backend to handle payment creation, verification, and order processing.

---

## ✨ Key Features

### 🛒 E-Commerce

- Product browsing and search
- Category-based product discovery
- Product details and variants
- Shopping cart management
- Quantity updates
- Order management
- Responsive user interface

### 💳 Payment Integration

- Razorpay payment gateway integration
- Backend-generated payment orders
- Secure payment workflow
- Payment verification
- Order creation after successful payment
- Payment status handling
- Transaction-aware order processing

### 👤 User Management

- User registration and authentication
- Secure login
- User-specific cart
- Order history

---

# 🏗️ System Architecture

```text
                         USER
                           │
                           ▼
                ┌─────────────────────┐
                │ React + TypeScript  │
                │      Frontend       │
                └──────────┬──────────┘
                           │
                           │ REST API
                           ▼
                ┌─────────────────────┐
                │ Node.js + Express   │
                │      Backend        │
                └──────────┬──────────┘
                           │
              ┌────────────┼────────────┐
              │            │            │
              ▼            ▼            ▼
        ┌──────────┐ ┌───────────┐ ┌────────────┐
        │PostgreSQL│ │   Order   │ │  Razorpay  │
        │ Database │ │ Management│ │   Gateway  │
        └──────────┘ └───────────┘ └──────┬─────┘
                                           │
                                           ▼
                                      Payment
                                      Verification
💳 Payment Workflow

One of the core components of FOREVER is its Razorpay payment integration.

        User
         │
         ▼
    Add Products
         │
         ▼
    Shopping Cart
         │
         ▼
    Checkout
         │
         ▼
 ┌──────────────────┐
 │ Backend creates  │
 │ Razorpay Order   │
 └────────┬─────────┘
          │
          ▼
 ┌──────────────────┐
 │ Razorpay Checkout│
 └────────┬─────────┘
          │
          ▼
      Payment
          │
          ▼
 ┌──────────────────┐
 │ Payment Details  │
 │ returned to      │
 │ backend          │
 └────────┬─────────┘
          │
          ▼
 ┌──────────────────┐
 │ Verify Payment   │
 │ Signature        │
 └────────┬─────────┘
          │
          ▼
 ┌──────────────────┐
 │ Create / Update  │
 │ Order            │
 └────────┬─────────┘
          │
          ▼
    Order Confirmed
🔐 Payment Security

The payment workflow is designed so that sensitive payment operations are handled by the backend rather than trusting the frontend.

The backend is responsible for:

Creating Razorpay payment orders
Managing the Razorpay secret credentials
Receiving payment information
Verifying payment signatures
Confirming successful transactions
Updating the corresponding order

Sensitive credentials are stored using environment variables and are not committed to the repository.

RAZORPAY_KEY_ID=your_key_id
RAZORPAY_KEY_SECRET=your_key_secret

Never expose RAZORPAY_KEY_SECRET in frontend code or commit it to GitHub.

📦 Order Lifecycle
Product Selection
       │
       ▼
Shopping Cart
       │
       ▼
Checkout
       │
       ▼
Payment Order Created
       │
       ▼
Razorpay Payment
       │
       ▼
Payment Verification
       │
       ▼
Order Created
       │
       ▼
Order History

This separates the payment process from the application's order management, allowing the backend to verify the transaction before finalizing the order.

🛠️ Tech Stack
Frontend
React.js
TypeScript
Tailwind CSS
JavaScript
Backend
Node.js
Express.js
REST APIs
Database
PostgreSQL
Payment
Razorpay Payment Gateway
Development
Git
GitHub
npm
VS Code
📸 Application
🏠 Home Page

🛍️ Product Listing

🛒 Shopping Cart

💳 Razorpay Checkout

📦 Order Confirmation

👨‍💻 Key Technical Contributions
Developed the full-stack e-commerce workflow.
Built REST APIs using Node.js and Express.
Integrated PostgreSQL for persistent application data.
Implemented shopping cart and order management.
Integrated Razorpay for online payment processing.
Implemented backend payment-order creation.
Added payment verification before completing orders.
Connected the payment lifecycle with the application's order lifecycle.
Implemented environment-based configuration for payment credentials.

🚀 Getting Started
1. Clone the repository
git clone https://github.com/loheytadhanure/Internship.git

cd Internship
2. Install dependencies
Frontend
cd frontend
npm install
Backend
cd ../backend
npm install
3. Configure environment variables

Create a .env file in the backend:

PORT=5000
DATABASE_URL=your_postgresql_url

RAZORPAY_KEY_ID=your_razorpay_key
RAZORPAY_KEY_SECRET=your_razorpay_secret
4. Start the backend
npm run dev
5. Start the frontend
cd ../frontend
npm run dev

🔌 Payment API Flow

A simplified payment flow:

Frontend
   │
   │ Request payment
   ▼
Backend
   │
   │ Create Razorpay order
   ▼
Razorpay
   │
   │ Return order details
   ▼
Frontend
   │
   │ Open Checkout
   ▼
Razorpay
   │
   │ Payment completed
   ▼
Backend
   │
   │ Verify signature
   ▼
Database
   │
   ▼
Order confirmed
🎯 What I Learned
Through this project, I gained hands-on experience with:

Full-stack application development
REST API design
PostgreSQL database integration
Authentication and authorization
E-commerce architecture
Payment gateway integration
Razorpay payment workflows
Payment verification
Order lifecycle management
Frontend-backend communication
Environment-based secret management

🔮 Future Improvements
Webhook-based payment status synchronization
Payment failure and retry handling
Refund management
Multiple payment gateway support
Admin payment analytics
Inventory synchronization
Automated payment reconciliation
Dockerized deployment
CI/CD pipeline

👨‍💻 Author
Loheyta Dhanure

B.E. Electronics & Telecommunication Engineering
AIML Honors — PICT

GitHub

📄 License

This project was developed for educational and portfolio purposes.
