# 🎓 College Management System

A role-based college management web application built with **Django**. It brings the daily work of a college into one place: managing staff, students, courses and subjects, taking attendance, publishing results, and handling leave requests and feedback.

## ✨ Features

### 👨‍💼 Admin / HOD
- Dashboard with summary charts for student and staff performance
- Add, edit and delete staff, students, courses, subjects and session years
- View student attendance by subject and date
- Approve or reject leave requests from staff and students
- Read and reply to feedback from staff and students
- Update profile

### 👩‍🏫 Staff / Teacher
- Dashboard with summaries for their subjects, students and leave status
- Take and update student attendance
- Add and update student results
- Apply for leave and send feedback to the HOD
- Update profile

### 🎒 Student
- Dashboard with attendance, subject and leave summaries
- View attendance and results
- Apply for leave and send feedback to the HOD
- Update profile

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python, Django |
| Frontend | HTML, CSS, JavaScript, jQuery, Ajax, Bootstrap, AdminLTE |
| Database | SQLite (default), MySQL supported via `settings.py` |

## 🚀 Getting Started

### Prerequisites
- Python 3.10 or newer
- pip

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/College_Management_System.git
cd College_Management_System

# 2. Create and activate a virtual environment
python -m venv env
source env/bin/activate        # Windows: env\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Apply database migrations
python manage.py migrate

# 5. Create an admin (HOD) account
python manage.py createsuperuser

# 6. Start the server
python manage.py runserver
```

Open **http://127.0.0.1:8000/** in your browser.

## 📁 Project Structure

```
College_Management_System/
├── manage.py
├── student_management_project/   # Project settings and root URLs
├── student_management_app/
│   ├── models.py                 # Database models
│   ├── views.py                  # Login, registration, public pages
│   ├── HodViews.py               # Admin / HOD features
│   ├── StaffViews.py             # Staff features
│   ├── StudentViews.py           # Student features
│   ├── urls.py
│   └── templates/                # HTML templates per role
├── media/                        # Uploaded profile pictures
└── static/                       # CSS, JS and AdminLTE assets
```

## 🔐 Roles

| Role | `user_type` | Landing page |
|---|---|---|
| HOD / Admin | 1 | `/admin_home/` |
| Staff | 2 | `/staff_home/` |
| Student | 3 | `/student_home/` |

## ⚠️ Notes for Production

This project was built for learning. Before deploying it publicly, you should:
- Set `DEBUG = False` and load `SECRET_KEY` from an environment variable
- Set `ALLOWED_HOSTS`
- Store passwords hashed (use Django's `authenticate()` and `check_password`)
- Use `POST` instead of `GET` for login

## 🤝 Contributing

Contributions are welcome. Fork the repo, create a feature branch and open a pull request.

## 📄 License

Add a license of your choice (for example MIT) before publishing.
