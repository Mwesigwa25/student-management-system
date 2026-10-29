# Student Management System

A Laravel web application for managing students, courses, lecturers and course registrations at Makerere University Business School.

**Course:** BUC3131 Advanced Web Application Development, Coursework Two (2026/2027)

**Repository:** [GitHub repository URL]

## Features

- Authentication with three roles: Administrator, Lecturer and Student
- Role and permission management with spatie/laravel-permission
- Student and course CRUD with form validation
- Course registration that blocks duplicate registrations and full courses
- Role-based records: lecturers see only their own courses, students see only their own registrations
- Reusable Blade layout with sidebar navigation that changes with the user's permissions
- Success and error messages after every action

## Requirements

- PHP 8.2 or newer
- Composer 2
- MySQL (for example through XAMPP)
- Git

## Installation

```bash
git clone [repository URL]
cd student-management-system
composer install
cp .env.example .env
php artisan key:generate
```

On Windows PowerShell, use `copy .env.example .env` instead of `cp`.

## Database setup

1. Start MySQL (XAMPP Control Panel, then Start next to MySQL).
2. Open http://localhost/phpmyadmin and create an empty database named `student_management`.
3. Open `.env` and set:

```properties
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=student_ms
DB_USERNAME=root
DB_PASSWORD=
```

4. Create the tables and load the sample data:

```bash
php artisan migrate:fresh --seed
```

5. Start the application:

```bash
php artisan serve
```

Open http://127.0.0.1:8000 in your browser.

The seeders use `firstOrCreate`, so running `php artisan db:seed` again does not create duplicate records.

## User roles

| Role | What they can do |
|---|---|
| Administrator | Manage students, courses and registrations, and manage user access |
| Lecturer | View assigned courses and the students registered for them |
| Student | View available courses, register for courses, and view or drop their own registrations |

### Permissions

| Role | Permissions |
|---|---|
| admin | view, create, edit and delete students; view, create, edit and delete courses; manage registrations; manage users |
| lecturer | view assigned courses |
| student | view available courses; register courses; view own registrations |

## Sample login credentials

The password for every account is `password`.

| Role | Email |
|---|---|
| Administrator | admin@mubs.ac.ug |
| Lecturer | lecturer1@mubs.ac.ug |
| Lecturer | lecturer2@mubs.ac.ug |
| Student | student1@mubs.ac.ug to student6@mubs.ac.ug |


## Screenshots

Login page
<img width="894" height="407" alt="image" src="https://github.com/user-attachments/assets/8cfe1e83-20f6-49c0-9dc2-80b0a65f3a1c" />

Admin dashboard
<img width="724" height="443" alt="image" src="https://github.com/user-attachments/assets/2fd32288-0e16-4719-b288-cc806eb281b3" />

Students list
<img width="736" height="361" alt="image" src="https://github.com/user-attachments/assets/df2c7491-0f7c-4410-a9e2-c36624de0228" />

Courses
<img width="734" height="282" alt="image" src="https://github.com/user-attachments/assets/c47b0789-dd42-44cd-b865-4f1873d78064" />

Registrations
<img width="716" height="425" alt="image" src="https://github.com/user-attachments/assets/ea34a14e-e608-47dc-bf2f-58fffe446f9e" />


## Team and contributions

| Member | Responsibility | Branch |
|---|---|---|
| [name] | Database design and relationships | feature/relationships |
| [name] | Seeders, roles and permissions | feature/seeders-roles |
| [name] | Student management | feature/student-management |
| [name] | Course and registration management | feature/course-registration |
| [name] | Layout, validation and documentation | feature/layout-docs |



## Technologies

Laravel, PHP, MySQL, Blade, Bootstrap 5, spatie/laravel-permission
