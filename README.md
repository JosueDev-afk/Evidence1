# Halcon — Order Tracking Web Application

This project is a web application for **Halcon**, a construction material distributor.  
The app allows customers to check the status of their orders and enables employees to manage the lifecycle of orders through a role-based dashboard.

---

## 🚀 Tech Stack
- **Backend:** Laravel 11 (PHP 8.2+)
- **Frontend:** Vue 3 + Vite + Pinia + Vue Router
- **Database:** MySQL / MariaDB
- **Auth:** Laravel Breeze (JWT or Sanctum for API tokens)
- **File Storage:** Local (for development) / S3-compatible bucket (for production)
- **Containerization:** Docker + Sail (optional)

---

## 📂 Project Structure

```
halcon-order-tracker/
├─ backend/ (Laravel API)
│  ├─ app/
│  ├─ routes/
│  ├─ database/
│  └─ ...
├─ frontend/ (Vue 3 + Vite app)
│  ├─ src/
│  ├─ public/
│  └─ ...
├─ docs/ (diagrams, ERD, BPMN, UML)
├─ docker-compose.yml
└─ README.txt
```

---

## ⚙️ Installation

### 1. Clone Repository
```bash
git clone https://github.com/<your-org>/halcon-order-tracker.git
cd halcon-order-tracker
```

### 2. Backend (Laravel)
```bash
cd backend
cp .env.example .env
composer install
php artisan key:generate
```

Configure your `.env` with database credentials:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=halcon
DB_USERNAME=root
DB_PASSWORD=secret
```

Run migrations and seed default Admin user:
```bash
php artisan migrate --seed
```

Start local server:
```bash
php artisan serve
```

### 3. Frontend (Vue 3)
```bash
cd ../frontend
cp .env.example .env
npm install
npm run dev
```

Default frontend runs at: `http://localhost:5173`

---

## 🔑 Default Admin User (seeded)
```text
Email: admin@halcon.com
Password: admin123
```

Use this account to create other users and assign roles.

---

## 👥 Roles
- **Admin:** Create users and assign roles  
- **Sales:** Create orders  
- **Warehouse:** Mark orders as “In process” / “In route”  
- **Purchasing:** Record purchases for missing materials  
- **Route:** Upload photos (loading + delivery), mark as “Delivered”  

---

## 📌 Main Features
- Customer portal to check order status by **Customer Number + Invoice Number**  
- Admin dashboard with role-based access  
- Order lifecycle:
  1. Ordered
  2. In process
  3. In route (upload loading photo)
  4. Delivered (upload delivery photo)
- Search orders by Invoice, Customer, Date, or Status  
- Soft-delete & restore orders  
- Upload & display photos for delivery evidence  

---

## 🧪 Testing
Run Laravel tests:
```bash
php artisan test
```

Run Vue tests (Vitest):
```bash
npm run test
```

---

## 🐳 Using Docker (optional)
You can run everything with **Laravel Sail** or Docker Compose:
```bash
docker-compose up -d
```
This will start:
- MySQL  
- Laravel backend  
- Vue frontend  

---

## 📖 Documentation
- `/docs/` folder contains:
  - BPMN Diagram
  - UML Use Case Diagram
  - Class Diagram
  - Activity Diagram
  - ER Diagram

---

## ✨ Personal Reflection
This project demonstrates applying best programming practices with **Laravel + Vue** to solve a real client need.  
Role-based access, soft deletes, and clear status transitions ensure reliability and traceability of orders.

---

## 📜 License
MIT — feel free to adapt and extend.
