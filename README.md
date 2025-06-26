# 💳 Banking Management System

A modern **Banking Management System** built using **Java Servlets**, **JSP**, **HTML/CSS**, and **MySQL**, allowing users to securely register, log in, create accounts, deposit, withdraw, and transfer money.

---

## 📁 Project Structure

```
BankingManagementSystem/
├── README.md
├── .gitignore
├── screenshots/
│   ├── create.png
│   ├── transfer.png
│   └── deposit.png
├── src/
│   └── main/
│       ├── java/
│       │   ├── CreateAccountServlet.java
│       │   ├── DBUtil.java
│       │   ├── DepositServlet.java
│       │   ├── DisplayAccountServlet.java
│       │   ├── Login.java
│       │   ├── Registration.java
│       │   ├── TransactionHistory.java
│       │   ├── TransferServlet.java
│       │   └── WithdrawServlet.java
│       └── webapp/
│           ├── Create.html
│           ├── Dashboard.html
│           ├── Diposite.html
│           ├── Display.html
│           ├── Home.html
│           ├── Login.html
│           ├── Registration.html
│           ├── TransactionHistory.html
│           ├── Transfer.html
│           ├── Withdraw.html
│           └── WEB-INF/
│               ├── web.xml
│               └── lib/
│                   └── mysql-connector-j-8.2.0.jar
```

---

## 🚀 Features

* 🗃️ User registration and login
* 📅 Create user bank accounts
* 💵 Deposit and withdraw funds
* 💸 Transfer funds with validation
* 🔄 Transaction history tracking
* 🔒 Secure JDBC-based access

---

## 🧰 Technologies Used

| Layer       | Technology                  |
| ----------- | --------------------------- |
| Frontend    | HTML, CSS                   |
| Backend     | Java Servlets (JSP)         |
| Database    | MySQL                       |
| Server      | Apache Tomcat 10.1.15       |
| JDBC Driver | mysql-connector-j-8.2.0.jar |
| IDE         | Eclipse                     |

---

## 🧪 How It Works

1. Users register and log in using credentials stored in MySQL.
2. Once logged in, they can access operations like create, deposit, withdraw, transfer, and view transactions.
3. Java Servlets handle form submission and connect to the database using JDBC.
4. Transaction safety is ensured with proper validation and rollback.

---

## ⚙️ Setup Instructions

### Step 1: Clone the Repository

```bash
git clone https://github.com/Mrinaldas18/BankingManagementSystem.git
cd BankingManagementSystem
```

### Step 2: MySQL Database Setup

```sql
CREATE DATABASE IF NOT EXISTS user_auth;
USE user_auth;

CREATE TABLE IF NOT EXISTS users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    password VARCHAR(100) NOT NULL
);

CREATE TABLE IF NOT EXISTS accounts (
    account_number INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    account_type VARCHAR(50),
    balance INT NOT NULL
);

CREATE TABLE IF NOT EXISTS transactions (
    id INT AUTO_INCREMENT PRIMARY KEY,
    account_number INT NOT NULL,
    type VARCHAR(50),
    amount INT,
    transaction_date DATETIME DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (account_number) REFERENCES accounts(account_number)
);
```

### Step 3: Configure Database Credentials

Update `DBUtil.java` with your local MySQL credentials:

```java
import java.sql.Connection;
import java.sql.DriverManager;

public class DBConnection {
    public static Connection getConnection() throws Exception {
        Class.forName("com.mysql.cj.jdbc.Driver");
        return DriverManager.getConnection(
            "jdbc:mysql://localhost:3306/user_auth",
            "root",
            "2341"
        );
    }
}
```

### Step 4: Deploy on Apache Tomcat

* Import project in Eclipse
* Run on Apache Tomcat Server
* Navigate to: `http://localhost:8082/Banking_Management_System/Login.html`

---

## 🖼️ Screenshots

| Login Page                                                                                | Register Page                                                                                |
| ----------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| ![Login](https://github.com/user-attachments/assets/7e586f1c-5b19-4a26-acad-f9751bff160a) | ![Register](https://github.com/user-attachments/assets/5bf118e7-6142-44a7-8eb9-a2baee3c1ac6) |

| Dashboard Page                                                                                | Account Creation                                                                           |
| --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| ![Dashboard](https://github.com/user-attachments/assets/487c3e42-9d9a-4ceb-b0d3-9b335e9cab7f) | ![Create](https://github.com/user-attachments/assets/25353e56-dbac-478a-88b6-c308caaa2396) |

| Fund Transfer                                                                                | Transaction History                                                                            |
| -------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| ![Transfer](https://github.com/user-attachments/assets/f122f6f3-74bd-4c39-91ae-0f98fd75ae6d) | ![Transation](https://github.com/user-attachments/assets/d74f93c2-13d8-422d-8f38-ca7aa130849b) |

---

## 🙋 Author

**Mrinal Das**
📧 [mrinaldas2341@gmail.com](mailto:mrinaldas2341@gmail.com)
🔗 [GitHub](https://github.com/Mrinaldas18)

---

## 📃 License

This project is licensed under the [MIT License](LICENSE).
