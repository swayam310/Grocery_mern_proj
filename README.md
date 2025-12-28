# 🛒 Grocery MERN App

A full-stack e-commerce grocery application built with the MERN stack (MongoDB, Express, React, Node.js). This application provides a complete solution for online grocery shopping with separate interfaces for customers and sellers.

## ✨ Features

### Customer Features
- 🔐 User authentication (Sign up, Login, Logout)
- 🏠 Homepage with featured products and categories
- 🔍 Product browsing and search functionality
- 📦 Product categories (Vegetables, Fruits, etc.)
- 🛍️ Shopping cart management
- 📍 Address management for delivery
- 💳 Order placement and management
- 📋 Order history tracking
- 🎨 Modern, responsive UI with Tailwind CSS

### Seller Features
- 🔐 Seller authentication
- ➕ Add new products with images
- 📝 Product management (View, Edit, Delete)
- 📊 Order management dashboard
- 🖼️ Image upload via Cloudinary
- 📦 Stock management

## 🛠️ Tech Stack

### Frontend
- **React 19** - UI library
- **React Router DOM** - Routing
- **Vite** - Build tool and dev server
- **Tailwind CSS** - Styling
- **Axios** - HTTP client
- **React Hot Toast** - Notifications

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM for MongoDB
- **JWT** - Authentication
- **Bcryptjs** - Password hashing
- **Multer** - File upload handling
- **Cloudinary** - Image storage and CDN
- **Stripe** - Payment processing
- **Cookie Parser** - Cookie handling
- **CORS** - Cross-origin resource sharing

## 📋 Prerequisites

Before running this project, make sure you have the following installed:

1. **Node.js** (v16 or higher) - [Download here](https://nodejs.org/)
2. **MongoDB** - Either install locally or use MongoDB Atlas (cloud database)
3. **npm** or **yarn** (comes with Node.js)
4. **Git** (if not already installed)

## 🚀 Installation & Setup

### Step 1: Clone the Repository

```bash
git clone <your-repo-url>
cd grocery-mern-app
```

### Step 2: Install Backend Dependencies

```bash
cd backend
npm install
```

### Step 3: Install Frontend Dependencies

```bash
cd ../client
npm install
```

### Step 4: Set Up MongoDB Database

You have two options:

#### Option A: MongoDB Atlas (Cloud - Recommended)
1. Go to [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a free account
3. Create a new cluster
4. Create a database user
5. Get your connection string (it will look like: `mongodb+srv://username:password@cluster0.xxxxx.mongodb.net/databaseName?retryWrites=true&w=majority`)

#### Option B: Local MongoDB
1. Install MongoDB locally from [mongodb.com](https://www.mongodb.com/try/download/community)
2. Start MongoDB service
3. Your connection string will be: `mongodb://localhost:27017/grocery-app`

### Step 5: Set Up Cloudinary (For Image Uploads)

1. Go to [Cloudinary](https://cloudinary.com/)
2. Sign up for a free account
3. Go to Dashboard
4. Copy your:
   - Cloud Name
   - API Key
   - API Secret

### Step 6: Configure Environment Variables

#### Backend Environment Variables

1. Navigate to the `backend` folder
2. Create a file named `.env`
3. Add the following variables:

```env
# MongoDB Connection
MONGO_URI=your_mongodb_connection_string_here

# JWT Secret (use any random string, e.g., use a password generator)
JWT_SECRET=your_jwt_secret_key_here

# Cloudinary Configuration
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret

# Seller Email (the email that will be used for seller login)
SELLER_EMAIL=your_seller_email@example.com

# Server Port (optional, defaults to 5000)
PORT=5000

# Node Environment (optional, use 'production' for production)
NODE_ENV=development
```

**Example `.env` file:**
```env
MONGO_URI=mongodb+srv://user:password@cluster0.xxxxx.mongodb.net/grocery-app?retryWrites=true&w=majority
JWT_SECRET=mySuperSecretJWTKey123456789
CLOUDINARY_CLOUD_NAME=demo
CLOUDINARY_API_KEY=123456789012345
CLOUDINARY_API_SECRET=abcdefghijklmnopqrstuvwxyz
SELLER_EMAIL=seller@example.com
PORT=5000
NODE_ENV=development
```

#### Frontend Environment Variables

1. Navigate to the `client` folder
2. Create a file named `.env`
3. Add the following variable:

```env
# Backend API URL (default is http://localhost:5000)
VITE_BACKEND_URL=http://localhost:5000
```

## 🏃 Running the Application

### Start the Backend Server

1. Navigate to the `backend` folder:
   ```bash
   cd backend
   ```

2. Start the server:
   ```bash
   npm run dev
   ```
   Or if nodemon is not installed:
   ```bash
   node index.js
   ```

You should see:
- "MongoDB connected"
- "Server is running on port 5000" (or your specified port)

**Keep this terminal window open!**

### Start the Frontend Development Server

1. Open a **new terminal window**
2. Navigate to the `client` folder:
   ```bash
   cd client
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

You should see:
- The server running on `http://localhost:5173` (Vite default port)

### Access the Application

1. Open your web browser
2. Go to: `http://localhost:5173`
3. You should see the grocery app homepage!

## 📁 Project Structure

```
grocery-mern-app/
├── backend/                    # Express.js backend server
│   ├── config/                 # Database and Cloudinary configuration
│   │   ├── cloudinary.js       # Cloudinary setup
│   │   ├── connectDB.js        # MongoDB connection
│   │   └── multer.js           # File upload configuration
│   ├── controller/             # Route controllers
│   │   ├── address.controller.js
│   │   ├── cart.controller.js
│   │   ├── order.controller.js
│   │   ├── product.controller.js
│   │   ├── seller.controller.js
│   │   └── user.controller.js
│   ├── middlewares/            # Authentication middlewares
│   │   ├── authSeller.js       # Seller authentication
│   │   └── authUser.js         # User authentication
│   ├── models/                 # MongoDB models
│   │   ├── address.model.js
│   │   ├── order.model.js
│   │   ├── product.model.js
│   │   └── user.model.js
│   ├── routes/                 # API routes
│   │   ├── address.routes.js
│   │   ├── cart.routes.js
│   │   ├── order.routes.js
│   │   ├── product.routes.js
│   │   ├── seller.routes.js
│   │   └── user.routes.js
│   ├── uploads/                # Uploaded images (temporary)
│   ├── index.js                # Server entry point
│   └── package.json
│
└── client/                     # React frontend (Vite)
    ├── src/
    │   ├── components/         # Reusable React components
    │   │   ├── Banner.jsx
    │   │   ├── BestSeller.jsx
    │   │   ├── Category.jsx
    │   │   ├── Footer.jsx
    │   │   ├── Navbar.jsx
    │   │   ├── NewsLetter.jsx
    │   │   ├── ProductCard.jsx
    │   │   └── seller/
    │   │       └── SellerLogin.jsx
    │   ├── pages/              # Page components
    │   │   ├── Address.jsx
    │   │   ├── Cart.jsx
    │   │   ├── Home.jsx
    │   │   ├── MyOrders.jsx
    │   │   ├── ProductCategory.jsx
    │   │   ├── Products.jsx
    │   │   ├── SingleProduct.jsx
    │   │   └── seller/
    │   │       ├── AddProduct.jsx
    │   │       ├── Orders.jsx
    │   │       ├── ProductList.jsx
    │   │       └── SellerLayout.jsx
    │   ├── context/            # React context (state management)
    │   │   └── AppContext.jsx
    │   ├── modals/             # Modal components
    │   │   └── Auth.jsx
    │   ├── assets/             # Images and assets
    │   ├── App.jsx             # Main App component
    │   ├── main.jsx           # React entry point
    │   └── index.css          # Global styles
    ├── public/                # Static files
    ├── index.html
    ├── vite.config.js
    └── package.json
```

## 🔌 API Endpoints

The backend API runs on `http://localhost:5000` with the following routes:

### User Routes (`/api/user`)
- `POST /register` - User registration
- `POST /login` - User login
- `GET /logout` - User logout
- `GET /profile` - Get user profile

### Seller Routes (`/api/seller`)
- `POST /login` - Seller login
- `GET /logout` - Seller logout

### Product Routes (`/api/product`)
- `GET /` - Get all products
- `GET /:id` - Get single product
- `GET /category/:category` - Get products by category
- `POST /` - Create new product (Seller only)
- `PUT /:id` - Update product (Seller only)
- `DELETE /:id` - Delete product (Seller only)

### Cart Routes (`/api/cart`)
- `GET /` - Get user cart
- `POST /add` - Add item to cart
- `POST /remove` - Remove item from cart
- `POST /update` - Update cart item quantity

### Address Routes (`/api/address`)
- `GET /` - Get user addresses
- `POST /` - Add new address
- `PUT /:id` - Update address
- `DELETE /:id` - Delete address

### Order Routes (`/api/order`)
- `GET /` - Get user orders
- `POST /` - Create new order
- `GET /seller` - Get seller orders (Seller only)
- `PUT /:id` - Update order status (Seller only)

## 🐛 Troubleshooting

### Backend Issues

1. **MongoDB Connection Error**
   - Check if your MongoDB connection string is correct
   - Ensure MongoDB is running (if using local MongoDB)
   - Check if your IP is whitelisted in MongoDB Atlas
   - Verify network access in MongoDB Atlas settings

2. **Port Already in Use**
   - Change the PORT in `.env` file
   - Or stop the process using port 5000
   - On Windows: `netstat -ano | findstr :5000` then `taskkill /PID <pid> /F`

3. **Module Not Found**
   - Delete `node_modules` folder and `package-lock.json`
   - Run `npm install` again

4. **Cloudinary Upload Error**
   - Verify your Cloudinary credentials in `.env`
   - Check if your Cloudinary account is active
   - Ensure the API key and secret are correct

### Frontend Issues

1. **Cannot Connect to Backend**
   - Ensure backend is running on the correct port
   - Check `VITE_BACKEND_URL` in client `.env` file
   - Verify CORS settings in backend
   - Check browser console for CORS errors

2. **Build Errors**
   - Clear node_modules and reinstall: `rm -rf node_modules && npm install`
   - On Windows: `rmdir /s node_modules && npm install`
   - Check for version conflicts in package.json

3. **Images Not Loading**
   - Verify Cloudinary configuration
   - Check if image URLs are correct
   - Ensure CORS is properly configured

## 📝 Additional Notes

- The backend server must be running before the frontend can make API calls
- Both servers need to run simultaneously (in separate terminal windows)
- For production deployment, you'll need to build the frontend: `npm run build` in the client folder
- The `uploads` folder in backend stores temporary files before uploading to Cloudinary
- JWT tokens are stored in HTTP-only cookies for security
- Seller authentication is email-based (configured via `SELLER_EMAIL` in `.env`)

## 🚀 Production Deployment

### Building for Production

1. **Build the frontend:**
   ```bash
   cd client
   npm run build
   ```

2. **Update environment variables:**
   - Set `NODE_ENV=production` in backend `.env`
   - Update `VITE_BACKEND_URL` to your production API URL

3. **Deploy backend:**
   - Deploy to services like Heroku, Railway, or Render
   - Ensure MongoDB Atlas is accessible from your hosting provider

4. **Deploy frontend:**
   - Deploy the `dist` folder to services like Vercel, Netlify, or AWS S3
   - Configure environment variables in your hosting platform

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 👨‍💻 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page.

## 🙏 Acknowledgments

- MongoDB Atlas for database hosting
- Cloudinary for image storage
- Stripe for payment processing
- All the open-source libraries that made this project possible

---

**Happy coding! 🚀**
