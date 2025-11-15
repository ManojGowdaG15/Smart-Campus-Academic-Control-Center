# 🎓 Smart Campus Academic Control Center

*A Scalable Django-Based Academic & Administrative Management System*

---

## 📌 **Project Overview**

The **Smart Campus Academic Control Center** is a full-fledged, web-based academic management system developed using the **Django framework**. It digitalizes the core academic and administrative operations of an educational institution — covering **students, faculty, administrators, courses, attendance, grades, notifications, and academic workflows**.

This system brings transparency, reduces paperwork, supports data-driven decisions, and enhances communication across the campus.
It is **scalable**, making it suitable for schools, colleges, and large universities.

---

## 🎯 **Objectives of the Project**

* Provide a secure **role-based login** system (Admin, Teacher, Student)
* Centralize all academic data in a unified platform
* Manage students, faculty, courses, sessions, attendance, and grades
* Offer dedicated dashboards for each user type
* Enable real-time access to academic information
* Replace manual workflows with automated modules
* Build a scalable architecture for future expansion

---

## 🧩 **Problem Statement**

Traditional academic systems cause:

* High paperwork
* Inefficient tracking of student performance
* Lack of centralized communication
* Data redundancy & loss
* Time-consuming administrative tasks

This system solves these challenges using a smart, interactive Django web platform.

---

## 🔍 **Scope of the Project**

Includes:

* Authentication & role-based access
* Student & faculty management
* Course & subject management
* Attendance & grade entry
* Academic dashboards
* Session & timetable management
* Notifications
* Scalable architecture for future modules

---

# 🛠 **Technologies Used**

### **Backend:**

* Python
* Django Framework (3.2.5)

### **Frontend:**

* HTML5, CSS3
* Bootstrap
* JavaScript

### **Database:**

* SQLite (development)

### **Server Technologies:**

* Gunicorn
* Whitenoise
* dj-database-url
* psycopg2-binary

### **Tools:**

* VS Code
* Git
---
# 💻 Hardware & Software Requirements

### **Hardware**

| Component | Minimum  | Recommended |
| --------- | -------- | ----------- |
| Processor | Intel i3 | Intel i5+   |
| RAM       | 4 GB     | 8 GB+       |
| Storage   | 50 GB    | 100 GB SSD  |
| Display   | 1024×768 | Full HD     |

### **Software**

* Windows 10/11, Linux, or macOS
* Python 3.8+
* Django 3.2.5
* SQLite / PostgreSQL
* XAMPP (optional)
* Git
* Postman
---
# 🏛 **System Architecture**

The project follows Django’s **MVT architecture**:

### **Model**

Defines database schema (Student, Faculty, Course, etc.)

### **View**

Handles logic, processing, validation, and data flow.

### **Template**

Renders the UI using HTML + Django template tags.

---
## 🧱 **System Layers**

### **1. Client Layer**

* Web browser interface
* HTML, CSS, Bootstrap-based UI

### **2. Application Layer**

* Django views, business logic, form processing
* Implements module-specific workflows

### **3. Data Layer**

* Django ORM for database communication
* Supports SQLite (dev) & PostgreSQL (prod)

---

# 🔧 **Core Modules**

## ✔ 1. User Authentication

* Role-based access control
* Email-based login
* Secure password validation
* Admin / Faculty / Student redirection

## ✔ 2. Student Management

* Add/edit/delete students
* Assign students to courses & sessions

## ✔ 3. Faculty Management

* Manage faculty profiles
* Assign subjects
* Approve faculty accounts

## ✔ 4. Course & Subject Management

* Create & manage courses
* Add subjects to courses

## ✔ 5. Attendance Module

* Faculty marks attendance
* Students view attendance reports

## ✔ 6. Grades & Examination

* Faculty uploads marks
* Students view internal results

## ✔ 7. Class Scheduling

* Session/timetable creation
* Students access schedules

## ✔ 8. Dashboards

* **Admin Dashboard:** Full control panel
* **Faculty Dashboard:** Attendance & grade management
* **Student Dashboard:** Courses, marks, attendance

## ✔ 9. Notification System

* Admin → Students
* Admin → Faculty

---

# 🗂 **Database Structure (ER Model)**

### **Major Entities**

* `CustomUser`
* `Student`
* `Staff`
* `Course`
* `Subject`
* `Session`
* `Attendance`
* `Marks`

### **Relationships**

* One-to-many (Course → Student)
* Many-to-many (Student ↔ Subject)
* One-to-many (Faculty → Subjects)

*(Your ER diagram will sit here if uploaded)*

---

# 🔄 **Data Flow Diagram (DFD) Overview**

### **Main Processes**

1. Login Module
2. Admin Operation Flow
3. Data Entry (Attendance, Grades)
4. Dashboard Output

*(You may add screenshots of DFD here)*

---

# 🧪 **Software Testing**

### **Testing Performed**

* **Unit Testing** (forms, models)
* **Integration Testing**
* **System Testing**
* **White-box Testing**
* **Black-box Testing**
* **Performance Testing**

### **Admin Login — Test Case Example**

| Test Case | Input                     | Expected Output       | Status |
| --------- | ------------------------- | --------------------- | ------ |
| TC01      | Correct admin credentials | Redirect to dashboard | Pass   |
| TC02      | Wrong password            | Show error message    | Pass   |
| TC03      | Empty fields              | Validation error      | Pass   |
| TC04      | Faculty credentials       | Access denied         | Pass   |

---

# 🧩 Sample Code Snippet

### **Custom Authentication (Email Login)**

```python
class EmailBackend(ModelBackend):
    def authenticate(self, username=None, password=None, **kwargs):
        UserModel = get_user_model()
        try:
            user = UserModel.objects.get(email=username)
        except UserModel.DoesNotExist:
            return None
        else:
            if user.check_password(password):
                return user
        return None
```

### **Admin Model Registration**

```python
admin.site.register(CustomUser, UserModel)
admin.site.register(Staff)
admin.site.register(Student)
admin.site.register(Course)
admin.site.register(Subject)
admin.site.register(Session)
```

### **URL Routing Example**

```python
path("admin/home/", hod_views.admin_home, name='admin_home'),
path("staff/home/", staff_views.staff_home, name='staff_home'),
path("student/home/", student_views.student_home, name='student_home'),
```

---

# 🚀 **How to Run This Project Locally**

### **1. Clone the Repository**

```
https://github.com/ManojGowdaG15/Smart-Campus-Academic-Control-Center
```

### **2. Create a Virtual Environment**

```
python -m venv venv
venv\Scripts\activate  (Windows)
source venv/bin/activate  (Linux/macOS)
```

### **3. Install Dependencies**

```
pip install -r requirements.txt
```

### **4. Apply Migrations**

```
python manage.py migrate
```

### **5. Create Superuser**

```
python manage.py createsuperuser
```

### **6. Run the Server**

```
python manage.py runserver
```

### **7. Access in Browser**

```
http://127.0.0.1:8000/
```

---

# 🔮 Future Enhancements

* Detailed analytics dashboard
* REST API integration (mobile app support)
* Push notifications
* Granular role-based permissions
* Student performance analytics
* Cloud deployment (AWS, GCP, Heroku)

---

# 📝 Conclusion

The **Smart Campus Academic Control Center** demonstrates how Django can be used to develop a powerful academic management system.
It eliminates the complexities of manual processes, enhances academic transparency, supports scalability, and provides separate, user-friendly dashboards for Admins, Teachers, and Students.

This project is a strong foundation for future expansion into a complete digital campus ecosystem.

---

# 👨‍💻 Author
**Manoj Gowda G**
MCA Student | Django Developer | Backend Developer
Dr. Ambedkar Institute of Technology
Bengaluru, India
