# 🏥 DocAppoint

A comprehensive web-based appointment management system built with PHP and MySQL that streamlines the process of booking, managing, and tracking medical appointments between patients and healthcare providers.

[![PHP](https://img.shields.io/badge/PHP-7.4%2B-blue.svg)](https://php.net)
[![MySQL](https://img.shields.io/badge/MySQL-5.7%2B-orange.svg)](https://mysql.com)
[![Bootstrap](https://img.shields.io/badge/Bootstrap-5.0-purple.svg)](https://getbootstrap.com)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 📋 Table of Contents
  
- [Features](#-features)
- [Demo](#-demo)
- [Installation](#-installation)
- [Database Setup](#-database-setup)
- [Configuration](#-configuration)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [Database Schema](#-database-schema)
- [Technologies Used](#-technologies-used)
- [Support](#-support)

## ✨ Features

### 👨‍⚕️ For Doctors

- **Secure Login System** - Password protected doctor authentication
- **Dashboard Overview** - View appointment statistics and quick insights
- **Appointment Management** - View, approve, cancel, and reschedule appointments
- **Patient Communication** - Add remarks and update appointment status
- **Profile Management** - Update personal and professional information
- **Specialization Management** - Associate with medical specializations
- **Date Range Reports** - Generate appointment reports between specific dates
- **Search Functionality** - Quick search through appointments

### 👥 For Patients

- **Easy Appointment Booking** - Simple form-based appointment scheduling
- **Doctor Selection** - Choose from available doctors by specialization
- **Appointment Tracking** - Check appointment status and details
- **Flexible Scheduling** - Select preferred date and time slots
- **Medical History** - View past appointments and remarks
- **Contact Information** - Easy access to clinic contact details

### 🔧 Administrative Features

- **Specialization Management** - Add/manage medical specializations
- **Doctor Registration** - Register new doctors with credentials
- **Content Management** - Update About Us and Contact information
- **Status Tracking** - Track appointment lifecycle (Pending/Approved/Cancelled)
- **Responsive Design** - Works on desktop, tablet, and mobile devices

## 🌐 Demo

**Live Demo**: [https://docappoint.kesug.com/](https://docappoint.kesug.com/)

## 🚀 Installation

### Prerequisites

- **Web Server** (Apache/Nginx)
- **PHP 7.4 or higher**
- **MySQL 5.7 or higher**
- **Web browser** (Chrome, Firefox, Safari, Edge)

## 🗄️ Database Setup

1. **Create Database**

   ```sql
   CREATE DATABASE damsmsdb;
   ```

2. **Import Database Schema**

   - Open phpMyAdmin (`http://localhost/phpmyadmin`)
   - Select the `damsmsdb` database
   - Import the `SQL File/damsmsdb.sql` file

3. **Verify Installation**
   - Check that all tables are created:
     - `tblappointment`
     - `tbldoctor`
     - `tblpage`
     - `tblspecialization`

## ⚙️ Configuration

### Database Configuration

Update the database credentials in the following files:

**File**: `dams/includes/dbconnection.php`

```php
define('DB_HOST','localhost');
define('DB_USER','your_username');
define('DB_PASS','your_password');
define('DB_NAME','damsmsdb');
```

**File**: `dams/doctor/includes/dbconnection.php`

```php
define('DB_HOST','localhost');
define('DB_USER','your_username');
define('DB_PASS','your_password');
define('DB_NAME','damsmsdb');
```

### For Production Deployment

For hosting on platforms like InfinityFree, 000webhost, etc.:

1. **Update database credentials** with your hosting provider's details
2. **Upload files** to your hosting directory
3. **Import database** using hosting control panel
4. **Test the application**

## 📖 Usage

### For Patients

1. **Visit the website** homepage
2. **Book Appointment**:
   - Fill in personal details
   - Select medical specialization
   - Choose preferred doctor
   - Pick appointment date and time
   - Add any special message
3. **Track Appointment**: Note down your appointment number for future reference

### For Doctors

1. **Login** using your credentials
2. **Dashboard**: View appointment overview and statistics
3. **Manage Appointments**:
   - View all appointments
   - Approve/Cancel appointments
   - Add remarks for patients
   - Update appointment status
4. **Profile Management**: Update your professional information

## 📁 Project Structure

```
doctor-appointment-system/
├── dams/                          # Main application directory
│   ├── css/                       # Stylesheets
│   │   ├── bootstrap.min.css
│   │   ├── templatemo-medic-care.css
│   │   └── ...
│   ├── js/                        # JavaScript files
│   │   ├── jquery.min.js
│   │   ├── bootstrap.bundle.min.js
│   │   └── ...
│   ├── images/                    # Image assets
│   ├── includes/                  # PHP includes
│   │   ├── dbconnection.php       # Database connection
│   │   ├── header.php             # Common header
│   │   └── footer.php             # Common footer
│   ├── doctor/                    # Doctor panel
│   │   ├── login.php              # Doctor login
│   │   ├── dashboard.php          # Doctor dashboard
│   │   ├── all-appointment.php    # Appointment management
│   │   ├── profile.php            # Doctor profile
│   │   └── ...
│   ├── index.php                  # Homepage
│   ├── check-appointment.php      # Appointment booking
│   └── get_doctors.php            # AJAX doctor fetching
├── SQL File/
│   └── damsmsdb.sql              # Database schema
├── Database_ER_Diagram.md        # Database documentation
└── README.md                     # This file
```

## 🗃️ Database Schema

The system uses 4 main tables:

### Tables Overview

| Table               | Purpose                 | Key Relationships                               |
| ------------------- | ----------------------- | ----------------------------------------------- |
| `tblspecialization` | Medical specializations | Referenced by doctors and appointments          |
| `tbldoctor`         | Doctor profiles         | Links to specializations, has many appointments |
| `tblappointment`    | Appointment records     | Links to doctors and specializations            |
| `tblpage`           | Static content          | Stores About Us, Contact Us pages               |

### Key Relationships

- **Specialization → Doctor** (One-to-Many)
- **Doctor → Appointment** (One-to-Many)
- **Specialization → Appointment** (One-to-Many)

## 🛠️ Technologies Used

### Backend

- **PHP 7.4+** - Server-side scripting
- **MySQL** - Database management

### Frontend

- **HTML5** - Markup language
- **CSS3** - Styling
- **Bootstrap 5** - CSS framework
- **JavaScript** - Client-side scripting
- **jQuery** - JavaScript library

### Additional Libraries

- **Owl Carousel** - Image/content slider
- **Bootstrap Icons** - Icon library

## 🆘 Support

If you encounter any issues or have questions:

1. **Check the documentation** first
2. **Search existing issues** on GitHub
3. **Create a new issue** if your problem isn't already reported
4. **Provide detailed information** including:
   - PHP version
   - MySQL version
   - Error messages
   - Steps to reproduce

## 🚀 Deployment

### Free Hosting Options

- **InfinityFree** - Recommended for beginners
- **000webhost** - Good alternative
- **Netlify** - For static parts (requires modifications)

### Production Hosting

- **Shared Hosting** - Most affordable option
- **VPS** - More control and resources
- **Cloud Hosting** - Scalable solutions

## 🔮 Future Enhancements

- [ ] Email notifications for appointments
- [ ] SMS notifications
- [ ] Online payment integration
- [ ] Video consultation feature
- [ ] Mobile app development
- [ ] Advanced reporting and analytics
- [ ] Multi-language support
- [ ] Calendar integration

---

⭐ **Star this repository** if you found it helpful!
