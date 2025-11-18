# 🍴 MERN College Canteen System

<div align="center">

![Canteen Banner](https://img.shields.io/badge/🍔-Digital_Canteen-success?style=for-the-badge)
[![MERN Stack](https://img.shields.io/badge/Stack-MERN-blue?style=for-the-badge&logo=mongodb)](https://github.com)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

**Revolutionizing campus dining with a seamless digital ordering experience**

[✨ Features](#-features) • [🚀 Quick Start](#-quick-start) • [📡 API Docs](#-api-documentation) • [🛠️ Tech Stack](#️-tech-stack)

</div>

---

## 🌟 Overview

Transform your college canteen into a modern, efficient digital platform! This full-stack MERN application eliminates long queues and streamlines the entire food ordering process with separate interfaces for students and administrators.

### 🎯 What Makes It Special?

- **⚡ Lightning Fast** - Order your meal in under 30 seconds
- **📱 Dual Interface** - Student app + Admin dashboard
- **🔐 Secure & Reliable** - JWT authentication with bcrypt encryption
- **☁️ Cloud-Powered** - Cloudinary integration for optimized image delivery
- **📊 Smart Analytics** - Real-time sales insights and order tracking
- **🎨 Modern UI** - Clean, responsive green-themed design

---

## ✨ Features

### 👨‍🎓 For Students

<table>
<tr>
<td width="50%">

#### 🍕 Smart Menu Browsing
- Browse items by category
- Real-time availability updates
- Search with debouncing optimization
- High-quality food images

</td>
<td width="50%">

#### 🛒 Seamless Cart Experience
- Add/remove items instantly
- Update quantities on-the-fly
- Persistent cart across sessions
- Quick checkout process

</td>
</tr>
<tr>
<td width="50%">

#### 📦 Order Tracking
- Live order status updates
- **Preparing** → **Out for Delivery** → **Done**
- Order history & receipts
- Reorder favorite meals

</td>
<td width="50%">

#### 👤 User Profile
- Manage account details
- View past orders
- Track spending history
- Update preferences

</td>
</tr>
</table>

### 🛠️ For Admins

<table>
<tr>
<td width="50%">

#### 📊 Advanced Analytics Dashboard
- Daily/Monthly revenue tracking
- Most popular items analysis
- Peak hours identification
- Order completion rates

</td>
<td width="50%">

#### 🍔 Inventory Management
- CRUD operations on menu items
- Image upload with Cloudinary
- Stock level monitoring
- Category organization

</td>
</tr>
<tr>
<td width="50%">

#### 📦 Order Management
- Real-time order notifications
- Update order status
- View all pending/completed orders
- Customer details & history

</td>
<td width="50%">

#### 📈 Sales Insights
- Revenue reports
- Order statistics
- Performance metrics
- Exportable data

</td>
</tr>
</table>

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                     MERN CANTEEN SYSTEM                      │
└─────────────────────────────────────────────────────────────┘
           │                                    │
    ┌──────▼──────┐                      ┌─────▼──────┐
    │   STUDENT   │                      │   ADMIN    │
    │   CLIENT    │                      │ DASHBOARD  │
    │   (React)   │                      │  (React)   │
    └──────┬──────┘                      └─────┬──────┘
           │                                    │
           └────────────┬───────────────────────┘
                        │
                 ┌──────▼──────┐
                 │   REST API   │
                 │  Express.js  │
                 │     JWT      │
                 └──────┬───────┘
                        │
           ┌────────────┼────────────┐
           │            │            │
    ┌──────▼──────┐ ┌──▼───┐  ┌────▼──────┐
    │   MongoDB   │ │Multer│  │ Cloudinary│
    │   Database  │ │Upload│  │   Images  │
    └─────────────┘ └──────┘  └───────────┘
```

---

## 📂 Project Structure

```
Mern-college-Canteen/
│
├── 📁 backend/                    # Node.js + Express REST API
│   ├── models/                    # Mongoose schemas
│   │   ├── User.js                # User model (students + admins)
│   │   ├── Items.js               # Menu items model
│   │   ├── Orders.js              # Orders model
│   │   └── Cart.js                # Shopping cart model
│   │
│   ├── routes/                    # API route definitions
│   │   ├── auth.js                # Authentication routes
│   │   ├── items.js               # Menu CRUD routes
│   │   ├── cart.js                # Cart operations
│   │   ├── orders.js              # Order management
│   │   └── sales.js               # Analytics routes
│   │
│   ├── controllers/               # Business logic
│   ├── middlewares/               # Auth, Multer, Error handling
│   ├── utils/                     # Helpers (bcrypt, JWT, Cloudinary)
│   ├── connect.js                 # MongoDB connection
│   └── server.js                  # Entry point
│
├── 📁 admin/                      # React Admin Dashboard
│   ├── src/
│   │   ├── components/            # Reusable UI components
│   │   │   ├── OrderCard.js       # Order display component
│   │   │   ├── Charts.js          # Sales charts
│   │   │   └── ItemTable.js       # Inventory table
│   │   │
│   │   ├── pages/                 # Admin pages
│   │   │   ├── Dashboard.js       # Main analytics view
│   │   │   ├── Orders.js          # Order management
│   │   │   ├── Inventory.js       # Menu management
│   │   │   └── Users.js           # User management
│   │   │
│   │   ├── context/               # Global state management
│   │   └── utils/                 # Helper functions
│
├── 📁 client/                     # React Student App
│   ├── src/
│   │   ├── components/            # UI components
│   │   │   ├── Menu.js            # Menu display
│   │   │   ├── Cart.js            # Shopping cart
│   │   │   └── Checkout.js        # Order placement
│   │   │
│   │   ├── pages/                 # Student pages
│   │   │   ├── Home.js            # Landing page
│   │   │   ├── Orders.js          # Order history
│   │   │   └── Profile.js         # User profile
│   │   │
│   │   ├── context/               # Cart & Auth context
│   │   └── utils/                 # API helpers, debouncing
│
└── 📄 README.md                   # You are here!
```

---

## 🚀 Quick Start

### Prerequisites

- Node.js (v14+)
- MongoDB (local or Atlas)
- npm or yarn
- Cloudinary account (for images)

### ⚡ Installation

**1️⃣ Clone the Repository**
```bash
git clone https://github.com/Dineshjogala7/Mern-college-Canteen.git
cd Mern-college-Canteen
```

**2️⃣ Backend Setup**
```bash
cd backend
npm install
```

Create `.env` file in backend directory:
```env
MONGO_URI=mongodb+srv://your_connection_string
JWT_SECRET=your_super_secret_key_here
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
PORT=5000
```

Start backend server:
```bash
npm start
# Server running on http://localhost:5000
```

**3️⃣ Student Client Setup**
```bash
cd ../client
npm install
npm start
# Client running on http://localhost:3000
```

**4️⃣ Admin Dashboard Setup**
```bash
cd ../admin
npm install
npm start
# Admin running on http://localhost:3001
```

---

## 📡 API Documentation

### 🔐 Authentication

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| `POST` | `/cred/signup` | Register new user | ❌ |
| `POST` | `/cred/login` | Login & get JWT token | ❌ |

**Example Request:**
```json
POST /cred/signup
{
  "name": "John Doe",
  "email": "john@college.edu",
  "password": "secure123",
  "role": "student"
}
```

### 🛒 Cart Operations

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| `POST` | `/user/cart/addcartitem/:userid` | Add item to cart | ✅ |
| `PATCH` | `/user/cart/updatecartitem/:userid` | Update quantity | ✅ |
| `DELETE` | `/user/cart/deletecartitem/:userid` | Remove from cart | ✅ |
| `GET` | `/user/cart/getcartitems/:userid` | Fetch cart items | ✅ |

### 🍔 Menu Items

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| `POST` | `/admin/items/additem` | Add menu item (with image) | 🔑 Admin |
| `GET` | `/user/items/getitems/:category` | Get items by category | ✅ |
| `DELETE` | `/admin/items/deleteitem/:itemid` | Delete item | 🔑 Admin |
| `PATCH` | `/admin/items/update/:itemid` | Update stock | 🔑 Admin |
| `PATCH` | `/admin/items/updateadmin/:itemid` | Update details | 🔑 Admin |

### 📦 Orders

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| `POST` | `/user/orders/placeorder/:userid` | Place new order | ✅ |
| `GET` | `/admin/orders/gettotalorders` | Get all orders | 🔑 Admin |
| `GET` | `/user/orders/getuserorders/:userid` | Get user orders | ✅ |
| `PATCH` | `/admin/orders/updateuserorder/:orderid` | Update status | 🔑 Admin |

### 📊 Sales Analytics

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| `GET` | `/admin/sales` | Get sales statistics | 🔑 Admin |

**Example Response:**
```json
{
  "totalOrdersToday": 120,
  "monthlyRevenue": 45000,
  "mostOrderedItem": {
    "name": "Veg Burger",
    "orders": 320
  },
  "pendingOrders": 12,
  "completionRate": "85%"
}
```

---

## 🛠️ Tech Stack

### Backend
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)

- **Runtime:** Node.js
- **Framework:** Express.js
- **Database:** MongoDB with Mongoose ODM
- **Authentication:** JWT + bcrypt
- **File Upload:** Multer + Cloudinary
- **Security:** helmet, cors, express-validator

### Frontend
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Context API](https://img.shields.io/badge/Context_API-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Axios](https://img.shields.io/badge/Axios-5A29E4?style=for-the-badge&logo=axios&logoColor=white)

- **Library:** React.js (Hooks & Functional Components)
- **State Management:** Context API
- **Routing:** React Router v6
- **HTTP Client:** Axios
- **Styling:** CSS3 with green theme
- **Optimization:** Debouncing for search

---

## 📊 Sample Analytics Dashboard

```
╔═══════════════════════════════════════════════════════╗
║           📊 CANTEEN ANALYTICS DASHBOARD              ║
╠═══════════════════════════════════════════════════════╣
║                                                       ║
║  📦 Total Orders Today: 120                           ║
║  💰 Revenue This Month: ₹45,000                       ║
║  🍔 Most Ordered: Veg Burger (320 orders)             ║
║  ⏳ Pending Orders: 12                                ║
║  ✅ Completed Orders: 85%                             ║
║                                                       ║
║  📈 Peak Hours: 12 PM - 2 PM                          ║
║  ⭐ Top Category: Fast Food                           ║
║                                                       ║
╚═══════════════════════════════════════════════════════╝
```

---

## 🎨 UI Highlights

### Student App
- 🎨 Clean, modern green-themed interface
- 📱 Fully responsive design
- ⚡ Real-time cart updates
- 🔍 Instant search with debouncing
- 📦 Order status tracking animations

### Admin Dashboard
- 📊 Interactive charts & graphs
- 📋 Sortable & filterable tables
- 🔔 Real-time order notifications
- 📈 Revenue trend visualization
- 🖼️ Drag & drop image uploads

---

## 🚧 Roadmap & Future Enhancements

- [ ] 💳 **Payment Gateway** - Razorpay/Stripe integration
- [ ] 🔔 **Push Notifications** - Real-time order updates
- [ ] 🤖 **AI Recommendations** - Personalized menu suggestions
- [ ] 📄 **Report Export** - PDF/CSV sales reports
- [ ] 👥 **Multi-Admin Roles** - Hierarchical access control
- [ ] 🌐 **Multi-Language** - Support for regional languages
- [ ] 📱 **Mobile App** - React Native version
- [ ] 🎯 **Loyalty Program** - Points & rewards system

---

## 🤝 Contributing

Contributions are what make the open-source community amazing! Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📝 License

Distributed under the MIT License. See `LICENSE` for more information.

---

## 👨‍💻 Author

<div align="center">

### **Yaswanth Naidu**

[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Yaswanthnaidu1718)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/yaswanthnaidu)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:yaswanthnaiduakula05@gmail.com)

**MERN Stack Developer | Problem Solver | Open Source Enthusiast**

</div>

---

## 🙏 Acknowledgments

* [MongoDB](https://www.mongodb.com/) - Database
* [Cloudinary](https://cloudinary.com/) - Image hosting
* [React Icons](https://react-icons.github.io/react-icons/) - Icon library
* [JWT.io](https://jwt.io/) - Token authentication
* Open source community for amazing tools

---

<div align="center">

### ⭐ Star this repo if you find it helpful!

**Made with ❤️ and lots of ☕**

[Report Bug](https://github.com/Dineshjogala7/Mern-college-Canteen/issues) • [Request Feature](https://github.com/Dineshjogala7/Mern-college-Canteen/issues)

</div>
