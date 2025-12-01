
# Task 1 - Flask Form with MongoDB

## Overview
This is a simple task submission web application built using:

- **Frontend:** HTML, CSS, JavaScript  
- **Backend:** Python Flask  
- **Database:** MongoDB (Local or Atlas)  

Users can submit tasks with details such as name, email, title, description, and due date. The submissions are stored in MongoDB.

---

## Project Structure

```
task1_form/
│
├── app.py             # Flask application
├── db.py              # MongoDB connection
├── requirements.txt   # Python dependencies
├── templates/
│   └── index.html     # HTML form
├── static/
│   └── script.js      # JavaScript for form submission
└── .env               # Environment variables (optional)
```

---

## Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/Task-1-Flask-Form-with-MongoDB.git
cd Task-1-Flask-Form-with-MongoDB
```

2. **Create a virtual environment**
```bash
python -m venv venv
# Activate:
# Windows: venv\Scripts\activate
# macOS/Linux: source venv/bin/activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Set up MongoDB**
- Local: Start `mongod`  
- Atlas: Copy your connection string and add it to `.env` as `MONGO_URI`

5. **Optional:** Create `.env` file in project root
```
MONGO_URI=mongodb://localhost:27017  # or your Atlas URI
```

---

## Running the App

```bash
python app.py
```

Open your browser at [http://127.0.0.1:5000](http://127.0.0.1:5000) to access the form.

---

## Usage

1. Fill in the **Name**, **Email**, **Title**, **Description**, and **Due Date** fields.  
2. Click **Submit**.  
3. Check MongoDB to see the saved tasks in the `task_manager` database and `submitted_tasks` collection.

---

## Optional: View Submissions on Web

You can add a route in `app.py` to view all tasks:

```python
@app.route('/tasks')
def show_tasks():
    tasks = list(collection.find({}, {'_id': 0}))
    return jsonify(tasks)
```

Then visit [http://127.0.0.1:5000/tasks](http://127.0.0.1:5000/tasks) to see all submissions in JSON format.

---

## Dependencies
- Flask  
- PyMongo  

---

## License
This project is open-source and free to use.
