Smart Entry Validation System

Overview

The Smart Entry Validation System is a QR Code–based web application designed to automate and streamline the process of validating students or employees during bus or institutional entry.
It eliminates the need for manual attendance or ID checks by providing a secure, automated, and paperless system where Admins can verify Users (Students) using a QR code scan.

This system plays a major role in school, college, or organizational transport systems — ensuring that only authorized users board the correct bus.

🔗Site Link :https://smartentrysystem.netlify.app/

```
🎯 Project Purpose

Traditional entry verification methods — like manual ID checks, name lists, or attendance sheets — are slow, inefficient, and error-prone.
To address this, the Smart Entry Validation System introduces a modern digital validation method using unique QR codes and a simple admin-user model.

The goal is to:

✅ Ensure security by validating authorized users only.

🚍 Simplify daily bus entry operations.

📱 Make validation contactless and fast.

📊 Keep digital attendance records automatically.

🌐 Reduce paper-based administration.```

```
🧩 System Roles and Structure

The application includes two main roles:

🧍‍♂️ 1. User (Student)

The User represents a student or passenger.
Each User gets a unique QR code after registration. This QR acts as their digital entry ID.

User Actions:

Register with personal details.

Receive a unique QR code.

Show the QR code for scanning when boarding the bus.

👨‍💼 2. Admin

The Admin manages scanning, validation, and organization details.
They have special permissions to scan, view attendance, and edit organization details through the Admin Panel.

Admin Actions:

Register as Admin.

Edit organization information.

Access QR Scanner to validate users.

View attendance and validation results.```

```
⚙️ How the System Works (Step-by-Step Workflow)

Let’s break down the full process 👇

🧾 Step 1: Registration Process

Both Admin and User can register through the registration page.

🧍‍♂️ For User:

The student enters details such as:

Name

ID

Bus Number

Password

Role → User

Once submitted, the system automatically generates a unique QR code that contains the student’s details (ID, Name, Bus No).

This QR code acts as a digital identity card for daily bus entry.

👨‍💼 For Admin:

The admin enters:

Name

ID

Bus Number (assigned bus)

Password

Role → Admin

After registration, the Admin gains access to:

🧭 Admin Panel (for managing organization and attendance).

📷 QR Scanner Access (to validate students).

🏫 Step 2: Organization Management (Admin Panel)

The Admin Panel allows the Admin to manage details like:

Organization Name

Address

Bus Route / Bus Number

Timing Information

All these editable fields are stored in the browser’s Local Storage (Chrome LocalStorage).

💡 Note: No cloud database is used for these organization settings.
They are stored locally for simplicity and faster access.

This makes the system perfect for small-scale institutions that need a lightweight, offline-capable management tool.

📷 Step 3: QR Code Scanning and Validation

When a student boards the bus:

The student opens or shows their QR code on their device.

The Admin uses the Scanner Page (in the Admin Panel) to scan the code.

The system decodes the QR to get the user’s details.

The app compares the student’s Bus Number with the Admin’s Bus Number.

Then:

✅ If both match → Validation Success (Valid User)

❌ If they don’t match → Validation Failed (Invalid User)

After validation, the result is instantly shown with a visual indicator (green for valid, red for invalid).

📅 Step 4: Attendance Recording

Each successful (valid) scan is automatically recorded as “Present” for the day.

The Admin can check daily attendance reports in their Admin Panel.

Attendance is stored securely through backend APIs using MongoDB.

This helps the Admin track which students were validated daily, reducing the need for manual attendance sheets.```

```
| Role    | Action                      | Output                               |
| ------- | --------------------------- | ------------------------------------ |
| Student | Registers and gets QR Code  | QR saved on screen/device            |
| Admin   | Registers with assigned bus | Gets access to Admin Panel + Scanner |
| Student | Boards bus and shows QR     | QR scanned by Admin                  |
| System  | Compares bus numbers        | Shows ✅ Valid / ❌ Invalid         |
| Admin   | Views attendance            | List of all present students         |
```

```
💾 Data Flow Explanation

Frontend (User Interface)

Developed using HTML, CSS, and JavaScript.

Handles registration, QR generation, and scanning.

Uses LocalStorage to temporarily store admin organization details.

Backend (Server)

Built with Node.js and Express.js.

Manages user and admin authentication, QR data generation, and attendance records.

Connects to MongoDB database for persistent storage.

Database (MongoDB)

Stores registered users, admin data, and attendance logs.

Each record includes ID, bus number, role, and timestamps for validation.```

```
| Layer              | Technologies Used                                |
| ------------------ | ------------------------------------------------ |
| **Frontend**       | HTML5, CSS3, JavaScript, QRCode.js               |
| **Backend**        | Node.js, Express.js                              |
| **Database**       | MongoDB + Mongoose                               |
| **Other Packages** | bcryptjs, uuid, dotenv, axios, cors, body-parser |
| **Storage**        | Chrome LocalStorage (for organization data)      |
```

```
🗂 Folder Structure
Smart Entry Validation/
│
├── backend/
│   ├── server.js
│   ├── .env
│   ├── package.json

│
├── frontend/
│   ├── index.html
│   ├── register.html
│   ├── admin.html
│   ├── scanner.html
│   ├── styles/
│   │   └── main.css
│   ├── scripts/
│       └── app.js
│
└── README.md
```

```
🌐 Deployment
| Component | Platform         |
| --------- | ---------------- |
| Frontend  | Netlify          |
| Backend   | Render           |
| Database  | MongoDB Atlas    |
```

```
👨‍💻 Developed by:

Santhosh Kumar. S
Full Stack Developer 
📍 Salem, Tamil Nadu, India.
```

```
🏁 Summary

The Smart Entry Validation System offers a secure, modern, and automated approach to daily entry validation.
By combining QR technology, admin control, and local + cloud storage, this system ensures:
✅ Accuracy
✅ Speed
✅ Security
✅ Digital Record-Keeping

It’s a perfect example of how simple technologies can create real-world impact in transportation and institutional management systems.```








