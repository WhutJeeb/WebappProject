# WebappProject
Group4
1- Esma Dennis Bin Mohd Adam 2316821
2- Muhammad Najib Bin Mohd Aziz 2317097

Project Title: UniThrift – Role-Based Thrift Marketplace for IIUM Students
📄 Project Description
UniThrift is a Laravel-based web application that allows IIUM students to buy and sell pre-loved items in a secure and organized platform. The system supports role-based access where different users (Admin, Seller, Customer) see different dashboard interfaces upon login. This project demonstrates Laravel authentication, session handling, role-based routing, and CRUD functionality for marketplace items.

🔐 User Roles and Features
Role	Redirect After Login	Dashboard View	Key Features
Admin	/admin/dashboard	dashboard.admin.blade.php	View all purchases, manage listings, future user management
Customer	/customer/dashboard	dashboard.customer.blade.php	Wishlist, messaging, purchases, browse listings

🔧 Project Setup Instructions
1. Clone the project into your XAMPP htdocs folder:
bash
Copy
Edit
cd C:\xampp\htdocs
git clone <repo-url> UniThrift
cd UniThrift
2. Install dependencies:
bash
Copy
Edit
composer install
npm install
3. Set up the environment:
Copy .env.example to .env and update your database config.

bash
Copy
Edit
cp .env.example .env
php artisan key:generate
4. Run migrations:
bash
Copy
Edit
php artisan migrate
This will create all necessary tables including users, products, and add a role column to users.

5. Start the local server:
bash
Copy
Edit
php artisan serve
Then visit:
http://127.0.0.1:8000

🧪 Testing Roles
Use phpMyAdmin to manually edit the users table and set roles:

Email	Role
admin@gmail.com	admin
anyuser@gmail.com	customer

The app will detect roles during login and redirect users accordingly.

🔁 Login Redirection Logic
Login is handled in AuthenticatedSessionController.php:

Authenticates the user

Regenerates the session

Detects the user's role

Redirects to their respective dashboard

php
Copy
Edit
if ($user->role === 'admin') {
    return redirect()->route('admin.dashboard');
}
🖼️ UI Overview
Admin sees a dashboard with access to product management and purchases

Customers have access to wishlist, purchases, messaging, and product browsing

Tailwind CSS is used for styling throughout

🚧 Future Improvements
Implement full seller dashboard

Add role selection during registration

Add role-based middleware to protect dashboard routes

Admin user management panel

👨‍💻 Developer Notes
Laravel version: 10+

Auth: Laravel Breeze (customized)

Frontend: Tailwind CSS

DB: MySQL via XAMPP

Here's the link since the file size exceed 25kb: 
https://drive.google.com/drive/folders/1RHSiswibotfTeeSWc51yyrCOPkCE8TJh?usp=sharing
