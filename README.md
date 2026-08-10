# UniFind - University Lost & Found Management System

UniFind is a PHP/MySQL web application for managing lost and found items in a university. Students can report items, search active reports, view possible matches, submit ownership claims and receive claim-status notifications. Administrators verify claims and manage users/items.

## Main Features

- Student registration and login
- Administrator role and separate admin dashboard
- Report lost items with category, location, date, description and optional image
- Report found items
- Search and filter active lost/found reports
- Possible match scoring for lost items
- Ownership claim requests
- Admin claim approval/rejection
- Automatic item status update to `returned` after approval
- Student claim tracking and notifications
- Edit/delete own active reports
- Admin views for users, items and claims
- Responsive dark/cyan user interface with interactive hover effects

## Screenshots

### Landing Page
![Landing Page](docs/screenshots/home.png)

### Student Dashboard
![Student Dashboard](docs/screenshots/dashboard.png)

### Search Items
![Search Items](docs/screenshots/search.png)

### Possible Matches
![Possible Matches](docs/screenshots/matches.png)

### Admin Dashboard
![Admin Dashboard](docs/screenshots/admin-dashboard.png)

### Claim Verification
![Claim Verification](docs/screenshots/admin-claims.png)

## SAD Diagrams

- [Use Case Diagram](docs/diagrams/use_case.png)
- [Activity Diagram](docs/diagrams/activity.png)
- [ER Diagram](docs/diagrams/er.png)
- [System Flow](docs/diagrams/system_flow.png)
- [Dashboard Wireframe](docs/diagrams/wireframe.png)

## Technology Stack

- Frontend: HTML5, CSS3, JavaScript
- Backend: PHP 8.x
- Database: MySQL / MariaDB
- Local server: Apache through XAMPP
- Development: Visual Studio Code
- Version control: Git and GitHub

## Database Tables

- `users`
- `items`
- `claims`
- `notifications`

## Local Setup

1. Copy the project folder to:

   ```text
   C:\xampp\htdocs\UniFind
   ```

2. Start **Apache** and **MySQL** in XAMPP.

3. Open phpMyAdmin:

   ```text
   http://localhost/phpmyadmin
   ```

4. Run `install.sql` from the SQL tab.

5. Check `config/database.php`. The default XAMPP configuration is:

   ```text
   host: localhost
   username: root
   password: (empty)
   database: unifind_db
   ```

6. Open the application:

   ```text
   http://localhost/UniFind/
   ```

7. Register a student account.

8. If no administrator exists, create the first administrator at:

   ```text
   http://localhost/UniFind/create-admin.php
   ```

   The page disables itself after an admin account exists.

## Possible Match Scoring

The current rule-based matching feature uses:

- Same category: base score of 40
- Exact location: +25
- Partial location similarity: +15
- Date within 3 days: +20
- Date within 7 days: +10
- Item-name similarity: up to +15
- Maximum score: 100%

## Suggested Demo Flow

1. Student A reports a lost wallet.
2. Student B reports a similar found wallet.
3. Student A opens **Possible Matches**.
4. Student A submits a claim for the found wallet.
5. Administrator reviews the ownership information.
6. Administrator approves the claim.
7. The item becomes `returned` and the student receives a notification.

## Project Documentation

- [Project Report - PDF](docs/UniFind_Project_Report.pdf)
- [Project Report - Word](docs/UniFind_Project_Report.docx)

## Project Structure

```text
UniFind/
├── admin/
├── config/
├── css/
├── js/
├── uploads/
├── docs/
│   ├── diagrams/
│   └── screenshots/
├── dashboard.php
├── index.php
├── login.php
├── register.php
├── report-lost.php
├── report-found.php
├── search-items.php
├── possible-matches.php
├── my-reports.php
├── my-claims.php
├── notifications.php
└── install.sql
```

## Notes

This project is configured for local academic/demo use. Before production deployment, use environment variables for database credentials, enable HTTPS, apply stronger account/authorization policies, and use managed storage for uploaded images.
