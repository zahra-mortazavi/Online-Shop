[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-8d59dc4de5201274e310e4c54b9627a8934c3b88527886e3b421487c677d23eb.svg)](https://classroom.github.com/a/_H7Tgm1p)
# 🛒 Online Shop Console Application

A fully console-based **Java Online Shop** that simulates a real e-commerce system with three user roles:

> 👤 **Guest** | 🛍 **Buyer** | 🛠 **Admin**

The application supports product browsing, advanced filtering, shopping cart management, purchasing workflow, commenting & scoring system, and admin approval processes — all implemented using pure Java.

---

# ✨ Features Overview

## 👤 Guest Capabilities

* Browse all available products
* Search products by name
* Apply advanced filters:

  * Category
  * Price range
  * Score
  * Inventory status
* Add items to a temporary cart
* View cart and attempt checkout (signup required to finalize purchase)

---

## 🛍 Buyer Capabilities

* Register (requires admin approval)
* Secure login with validated credentials
* Edit personal information:

  * Password
  * Phone number
  * Email
* Manage shopping cart
* Purchase products (inventory + balance validation included)
* View purchase history
* Rate products (0–5 score, editable)
* Add comments

  * Comments for unpurchased items require admin approval
* Request account balance increase (admin approval required)

---

## 🛠 Admin Capabilities

**Default Credentials:**

```
Username: admin  
Password: admin
```

Admin can:

* Add new products (cars, bikes, stationery, digital goods, etc.)
* Edit product:

  * Name
  * Price
  * Inventory
* Delete products (single or multiple)
* View all products
* Review pending requests:

  * Signup requests
  * Comment approvals
  * Balance increase requests
* Accept or reject requests
* Use `help` command to display full command syntax

---

# 🧰 Technologies & Design Patterns

| Technology            | Purpose                               |
| --------------------- | ------------------------------------- |
| Java 8+               | Core programming language             |
| Console I/O           | User interaction                      |
| Regular Expressions   | Input validation                      |
| MVC-like Architecture | Separation of concerns                |
| Singleton Pattern     | Controller & view instance management |
| Enums                 | Categories, types, request status     |

> ✅ No external libraries used — pure Java implementation.

---

# 📁 Project Structure

```
src/
├── controller/
│   ├── admincontroller/
│   ├── buyercontroller/
│   └── goodscontroller/
├── model/
│   ├── goods/
│   ├── request/
│   └── user/
└── view/
    ├── admin/
    ├── buyer/
    └── goods/

Main.java
```

---

## 🔑 Core Classes

| Class             | Responsibility                                   |
| ----------------- | ------------------------------------------------ |
| `Main`            | Application entry point                          |
| `MainMenu`        | Displays main navigation menu                    |
| `BuyerController` | Authentication, cart, purchase, balance requests |
| `GoodsController` | Product management, filters, scoring, comments   |
| `AdminController` | Admin commands & request approvals               |
| `GoodsModel`      | Abstract base class for all products             |
| `BuyerModel`      | Stores cart, history, balance                    |
| `Request`         | Base class for admin approval workflows          |
| `Shop`            | Console product browsing interface               |
| `BuyerPanel`      | Buyer dashboard                                  |
| `AdminPanel`      | Admin command interface                          |

---

# ▶️ How to Run

### 1️⃣ Install Java 8 or higher

Check version:

```bash
java -version
```

### 2️⃣ Compile Project

From the root directory (where `Main.java` exists):

```bash
javac Main.java
```

### 3️⃣ Run Application

```bash
java Main
```

The console application will launch and display the main menu.

---

# 🧭 Usage Guide

## 🏠 Main Menu Options

| Option | Action              |
| ------ | ------------------- |
| `1`    | Sign up as Buyer    |
| `2`    | Login (Buyer/Admin) |
| `3`    | Continue as Guest   |

---

## 👤 Guest Mode

* Browse products
* Apply filters
* Search by keyword
* View details and comments
* Add to cart
* Attempt checkout (requires signup)

---

## 🛍 Buyer Panel

| Option | Action                       |
| ------ | ---------------------------- |
| `1`    | View / Edit Profile          |
| `2`    | Enter Shop                   |
| `3`    | View Cart & Checkout         |
| `4`    | Request Balance Increase     |
| `5`    | View Purchase History & Rate |
| `6`    | Return to Main Menu          |

---

## 🛠 Admin Commands

| Command                            | Description           |                     |              |
| ---------------------------------- | --------------------- | ------------------- | ------------ |
| `help`                             | Show command syntax   |                     |              |
| `add <type> <parameters>`          | Add new product       |                     |              |
| `showgoods`                        | List all products     |                     |              |
| `edit <goodsID> <NAME              | PRICE                 | INVENTORY> <value>` | Edit product |
| `delete <goodsID1> [goodsID2 ...]` | Delete products       |                     |              |
| `showreq`                          | Show pending requests |                     |              |
| `req accept <IDs>`                 | Accept requests       |                     |              |
| `req reject <IDs>`                 | Reject requests       |                     |              |
| `exit`                             | Return to main menu   |                     |              |

---

# 🔒 Validation Rules

| Field            | Rule                                        |
| ---------------- | ------------------------------------------- |
| Username         | Must be unique                              |
| Password         | ≥8 chars, 1 uppercase, 1 lowercase, 1 digit |
| Phone            | Iranian format: `09[1-3]XXXXXXXX`           |
| Email            | Signup: `@gmail.com` only                   |
| Card Number      | 16 digits                                   |
| CVV2             | 3 digits                                    |
| Account Password | ≥5 digits                                   |
| Score            | 0–5                                         |

---

# 🚀 Future Improvements

* Replace in-memory storage with database (e.g., SQLite)
* Password hashing & encryption
* Pagination for large product lists
* Logging system instead of `System.out`
* Stronger MVC separation
* Unit testing
* Product images & detailed descriptions
* REST API version
* GUI or Web version

---

# 📚 Educational Purpose

This project was developed as a learning-oriented console application demonstrating:

* OOP principles
* Design patterns
* Input validation
* Role-based architecture
* Approval workflow systems

---

## 👨‍💻 Author

Sample educational Java project for practicing software design and console-based application development.

---

