# 💳 Banking Management System

A web-based **Banking Management System** built using **Java Servlets**, **JSP**, **HTML**, and **MySQL**. This system supports creating accounts, depositing, withdrawing, and transferring money between users.

---

## 📁 Project Structure

```
BankingManagementSystem/
├── src/
│   └── main/
│       ├── java/
│       │   ├── Create.java
│       │   ├── Transfer.java
│       │   ├── Withdraw.java
│       │   ├── Diposite.java
│       │   └── Login.java
│       └── webapp/
│           ├── Create.html
│           ├── Transfer.html
│           ├── Withdraw.html
│           ├── Display.html
│           └── WEB-INF/
│               ├── web.xml
│               └── lib/
│                   └── mysql-connector-j-8.2.0.jar
```

---

## 🚀 Features

- 🧾 Create new user bank accounts
- 💵 Deposit money into an account
- 💸 Withdraw money with balance checks
- 🔁 Transfer money between accounts
- 🔐 Validation for account existence and balance sufficiency
- 🔄 Transaction rollback if transfer fails

---

## 🧰 Technologies Used

| Layer        | Technology                  |
|--------------|-----------------------------|
| Frontend     | HTML, CSS                   |
| Backend      | Java Servlets (JSP)         |
| Database     | MySQL                       |
| Server       | Apache Tomcat 10.1.15       |
| JDBC Driver  | mysql-connector-j-8.2.0.jar |
| IDE          | Eclipse                     |

---

## 🧪 How It Works

1. HTML form takes user input (sender/receiver account, amount).
2. Servlet receives the form data through `doPost()`.
3. JDBC connects to MySQL to:
   - Validate accounts
   - Check balance
   - Perform transaction with rollback support
4. Outputs result via `PrintWriter` (success/failure message).

---

## ⚙️ Setup Instructions

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/BankingManagementSystem.git
cd BankingManagementSystem
```

### Step 2: MySQL Database Setup

```sql
CREATE DATABASE userdetails;
USE userdetails;

CREATE TABLE createservlet (
    num INT PRIMARY KEY,
    name VARCHAR(100),
    balance INT
);
```

### Step 3: Configure Database Credentials

Update your `.java` files (`Create.java`, `Transfer.java`, etc.):

```java
Connection con = DriverManager.getConnection(
    "jdbc:mysql://localhost:3306/userdetails", "root", "2341");
```

### Step 4: Deploy on Apache Tomcat

- Open project in Eclipse
- Run on Server → Apache Tomcat
- Visit: `http://localhost:8080/YourProjectName/`

---

## 🖼️ Screenshots

> Below are some example screenshots of the system working in Eclipse IDE.

| Account Creation | Fund Transfer | Deposit Page |
|------------------|---------------|--------------|
| ![Create](screenshots/create.png) | ![Transfer](screenshots/transfer.png) | ![Deposit](screenshots/deposit.png) |

*You can place screenshots in a `/screenshots` folder and reference them here.*

---

## 🙋 Author

**Mrinal Das**  
📧 [mrinalldas2341@gmail.com](mailto:mrinaldas2341@gmail.com)  
🔗 [GitHub](https://github.com/Mrinaldas18)

---

## 📃 License

This project is open-source and available under the [MIT License](LICENSE).
