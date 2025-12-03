# DICT Attendance System - Deployment Guide

## 🚀 Quick Installation Steps

### 1. Prerequisites
- **XAMPP** installed with Apache and MySQL running
- **Web browser** (Chrome/Firefox recommended for camera access)
- **NFC reader device** for card scanning

### 2. Installation Process

#### Step 1: Copy Files
1. Copy all files to `C:\xampp\htdocs\DICT\`
2. Ensure the following directory structure exists:
   ```
   C:\xampp\htdocs\DICT\
   ├── install_database.sql    ← Single database installation file
   ├── index.php              ← Main attendance landing page
   ├── config/
   │   └── database.php       ← Database configuration
   ├── css/                   ← Stylesheets
   ├── js/                    ← JavaScript files  
   ├── img/                   ← Images and logos
   ├── images/                ← For attendance photos
   └── [other system files]
   ```

#### Step 2: Database Setup
1. Open **phpMyAdmin** (http://localhost/phpmyadmin)
2. Create new database or import:
   ```sql
   -- Option 1: Auto-create (recommended)
   -- Just run: install_database.sql
   
   -- Option 2: Manual
   CREATE DATABASE attendance_system;
   ```
3. Import `install_database.sql` file
4. **Done!** All tables, indexes, and default admin are automatically created

#### Step 3: Configuration
1. Check `config/database.php` settings:
   ```php
   define('DB_HOST', 'localhost');     // ✅ Keep as localhost
   define('DB_USER', 'root');          // ✅ Default XAMPP user
   define('DB_PASS', '');              // ✅ Default XAMPP (no password)
   define('DB_NAME', 'attendance_system'); // ✅ Database name
   ```

#### Step 4: Permissions
1. Create directory for attendance photos:
   ```
   mkdir C:\xampp\htdocs\DICT\images\attendance
   ```
2. Ensure write permissions for photo storage

## 🎯 Access Points

### Main Attendance Station (with Camera)
- **URL:** `http://localhost/DICT`
- **Features:** NFC scanning + automatic photo capture
- **Users:** For daily attendance recording

### Remote Dashboard Access  
- **URL:** `http://192.168.x.x/DICT` (your computer's IP)
- **Features:** Login to dashboards (no camera needed)
- **Users:** Interns and admins accessing from other devices

## 👥 Default Login Credentials

### System Administrator
- **Card UID:** 123456789   
- **PIN:** 000000
- **Access:** Full system administration

## 📋 System Features

### ✅ Completed & Working
- **Always-on camera** with live preview
- **Automatic photo capture** on NFC card tap
- **Real-time attendance table** updates
- **Admin dashboard** with full management
- **Intern dashboard** with attendance history
- **Employee management** system
- **Completion tracking** and graduation notifications
- **Image storage** with organized file structure
- **Responsive design** for mobile and desktop

### 🛠️ Technical Specifications
- **Database:** MySQL with optimized indexes
- **Image Storage:** Date-organized folders (`YYYY-MM-DD`)
- **Camera:** 640x480 resolution, JPEG format
- **Security:** SQL injection protection, XSS prevention
- **Performance:** Optimized queries with proper indexing

## 🔧 Troubleshooting

### Camera Issues
- **Problem:** Camera not working on IP access
- **Solution:** This is normal! Use `localhost` for attendance station
- **Explanation:** Browser security requires localhost for camera access

### Database Connection
- **Problem:** Can't connect to database
- **Solution:** 
  1. Ensure XAMPP MySQL is running
  2. Check `config/database.php` settings
  3. Verify database exists in phpMyAdmin

### Attendance Not Recording
- **Problem:** NFC tap not working
- **Solution:**
  1. Check if input field is focused
  2. Verify card UID is registered in system
  3. Ensure user status is 'active'

## 📁 File Structure Overview

### Core System Files
- `index.php` - Main attendance landing page
- `login.php` - System login page
- `admin-dashboard.php` - Administrative interface
- `intern-dashboard.php` - Intern interface
- `process.php` - Attendance processing logic

### Management Files
- `interns.php` - Intern management
- `employee-management.php` - Employee management
- `attendance-history.php` - Attendance records

### API Endpoints
- `get_recent_attendance.php` - Real-time attendance data
- `get_dtr_data.php` - DTR generation
- `save_tasks.php` - Task saving
- And other specific endpoints...

## 🎊 Installation Complete!

After following these steps, your DICT Attendance System will be ready for production use with:
- ✅ Clean, optimized codebase
- ✅ Single database installation file
- ✅ Complete feature set
- ✅ Professional UI/UX
- ✅ Real-time updates
- ✅ Photo capture functionality

**Happy deployment! 🚀** 

-Reginado, 2025
