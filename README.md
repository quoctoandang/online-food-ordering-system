# 🍕 Food Delivery Platform

> A comprehensive food delivery web application built with Django, connecting customers, merchants, and delivery riders

## 📋 Overview

**Food Delivery Platform** is a full-stack web application that enables users to order food from restaurants, merchants to manage their products and orders, and riders to deliver orders efficiently. The system features three distinct user roles with dedicated dashboards and functionalities.

## ✨ Key Features

### 👥 Multi-Role System
- **Customer** - Browse, order, and track food deliveries
- **Merchant** - Manage restaurant, products, and incoming orders
- **Rider** - Accept and deliver orders to customers

### 🛒 Customer Features
- User registration and authentication
- Browse food products from multiple merchants
- Add items to cart with quantity management
- Secure checkout process
- Real-time order tracking with status updates:
  - Pending → Accepted → Packed → On the way → Delivered
- Order history and management
- Cancel orders
- Multiple delivery addresses
- Search functionality

### 🏪 Merchant Features
- Merchant profile management
- Add/edit/delete products
- Update product prices
- View and manage incoming orders
- Update order status
- Dashboard with business insights
- Product image uploads
- Search and filter orders

### 🏍️ Rider Features
- Rider profile with vehicle information (Car/Motorbike)
- View available orders for delivery
- Accept and save orders
- Update delivery status
- Delivery address management
- Dashboard for tracking deliveries
- Profile image upload

### 🔐 Authentication & Security
- Secure user registration with role selection
- Login/Logout functionality
- Password change
- Password reset via email
- Role-based access control

## 🛠️ Technology Stack

| Component | Technology |
|-----------|------------|
| **Backend Framework** | Django 5.x |
| **Database** | SQLite (Development) |
| **Frontend** | HTML, CSS, Bootstrap |
| **Authentication** | Django Auth System |
| **File Storage** | Django Media Files |
| **Forms** | Django Forms with Validation |

## 📁 Project Structure

```
food-delivery-platform/
├── weB/                          # Main project directory
│   ├── manage.py                 # Django management script
│   ├── db.sqlite3                # SQLite database
│   ├── requirements.txt          # Python dependencies
│   ├── weB/                      # Project settings
│   │   ├── settings.py
│   │   ├── urls.py
│   │   └── wsgi.py
│   ├── app/                      # Main application
│   │   ├── models.py             # Database models
│   │   ├── views.py              # View controllers
│   │   ├── urls.py               # URL routing
│   │   ├── forms.py              # Form definitions
│   │   ├── admin.py              # Admin configuration
│   │   ├── templates/            # HTML templates
│   │   │   ├── base.html
│   │   │   ├── home.html
│   │   │   ├── login.html
│   │   │   ├── signup.html
│   │   │   ├── customer.html
│   │   │   ├── merchants.html
│   │   │   ├── rider.html
│   │   │   ├── checkout.html
│   │   │   ├── order.html
│   │   │   └── ...
│   │   ├── static/               # Static files (CSS, JS, images)
│   │   └── migrations/           # Database migrations
│   └── static/                   # Global static files
│       ├── admin/
│       ├── admin-lte/
│       ├── app/
│       └── images/
└── README.md
```

## 🗃️ Database Models

### User & Authentication
- **Account** - Extended user model with role (Customer/Merchant/Rider)
- **Customer** - Customer profile with address and contact info
- **Merchant** - Merchant profile and restaurant details
- **Rider** - Delivery rider profile with vehicle information

### Products & Orders
- **Product** - Food items with price, image, and merchant reference
- **Cart** - Shopping cart items for customers
- **OrderPlaced** - Confirmed orders with status tracking
- **RiderSavedOrders** - Orders assigned to riders

### Order Status Flow
```
Pending → Accepted → Packed → On the way → Delivered
                              ↓
                           Cancel
```

## 🚀 Installation & Setup

### Prerequisites
- Python 3.8+
- pip (Python package manager)

### Installation Steps

1. **Clone the repository**
```bash
git clone <repository-url>
cd Build_Food_Delivery_Web/weB
```

2. **Create virtual environment**
```bash
python -m venv venv
# Windows
venv\Scripts\activate
# Linux/Mac
source venv/bin/activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Run migrations**
```bash
python manage.py migrate
```

5. **Create superuser (admin)**
```bash
python manage.py createsuperuser
```

6. **Collect static files**
```bash
python manage.py collectstatic
```

7. **Run development server**
```bash
python manage.py runserver
```

8. **Access the application**
- Website: http://127.0.0.1:8000
- Admin Panel: http://127.0.0.1:8000/admin

## 📱 Main Routes

### Authentication
| Route | Description |
|-------|-------------|
| `/` | Home page |
| `/signup/` | User registration with role selection |
| `/login` | User login |
| `/logout/` | User logout |
| `/passwordchange/` | Change password |
| `/password-reset/` | Password reset flow |

### Customer Routes
| Route | Description |
|-------|-------------|
| `/customer/` | Browse products |
| `/profile/` | Create customer profile |
| `/address/` | Manage delivery addresses |
| `/add-to-cart` | Add product to cart |
| `/cart/` | View shopping cart |
| `/checkout` | Checkout and place order |
| `/orders/` | View order history |
| `/dashboardcus/` | Customer dashboard |
| `/search/` | Search products |

### Merchant Routes
| Route | Description |
|-------|-------------|
| `/merchants` | Merchant home |
| `/profilemerchants/` | Create merchant profile |
| `/merchantsaddress/` | Manage merchant address |
| `/addproduct` | Add new product |
| `/ordersmc/` | View merchant orders |
| `/dashboardmer/` | Merchant dashboard |
| `/update_price/<id>/` | Update product price |
| `/delete_product/<id>/` | Delete product |
| `/update_order_status/<id>/` | Update order status |
| `/searchmer/` | Search merchant orders |

### Rider Routes
| Route | Description |
|-------|-------------|
| `/rider` | View available orders |
| `/profilerider/` | Create rider profile |
| `/rideraddress/` | Manage rider address |
| `/ridersave/<id>/` | Accept and save order |
| `/saveorder/` | View saved orders |
| `/update_rider_status/<id>/` | Update delivery status |
| `/dashboardrider/` | Rider dashboard |

## 🎯 User Workflows

### Customer Journey
1. Register account and select "Customer" role
2. Create customer profile with delivery address
3. Browse products from various merchants
4. Add items to cart
5. Proceed to checkout
6. Place order with selected address
7. Track order status in real-time
8. Receive delivered order

### Merchant Journey
1. Register account and select "Merchant" role
2. Create merchant profile with restaurant details
3. Add products with images and prices
4. Receive customer orders
5. Update order status (Accept → Pack)
6. Manage product catalog
7. View business metrics on dashboard

### Rider Journey
1. Register account and select "Rider" role
2. Create rider profile with vehicle info
3. View available orders for delivery
4. Accept orders
5. Update status (On the way → Delivered)
6. Track delivery history

## 🎨 Features In Detail

### Shopping Cart Management
- Add/Remove products
- Update quantities with +/- buttons
- Real-time price calculation
- Persistent cart data

### Order Management
- Customer: Track orders, cancel pending orders
- Merchant: Accept/reject orders, update status
- Rider: Accept orders, update delivery status

### Search Functionality
- Customers can search products by name
- Merchants can search their orders

### Dashboard Analytics
- Customer: Order history, total spending
- Merchant: Total orders, revenue insights
- Rider: Delivery statistics

## 🔧 Configuration

### Email Settings (for password reset)
Update in `weB/settings.py`:
```python
EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
EMAIL_HOST = 'smtp.gmail.com'
EMAIL_PORT = 587
EMAIL_USE_TLS = True
EMAIL_HOST_USER = 'your-email@gmail.com'
EMAIL_HOST_PASSWORD = 'your-app-password'
```

### Media Files
- Product images stored in `/media/images/`
- Rider images stored in `/media/`

## 📝 License

This project is developed for educational purposes.

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests
- Improve documentation

## 📧 Contact & Support

For support and inquiries, please use the contact form on the website.

---
⭐ If you find this project useful, please give it a star!

