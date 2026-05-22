# Spendo — Personal Expense Tracker
 
## 1. Project Description
 
Spendo is a personal expense tracking web application designed to help users organise and manage their daily spending in a more structured way. The platform provides a centralised system for recording and reviewing financial information, helping users gain better awareness of their spending habits and make more informed financial decisions.

Registration/Login: User authentication using password hashing and JWT to provide secure account access and ensure users can only access their own expense records.
Logout: Allows users to securely end their session and protect account privacy.
Expense Management: Users can create, view, update, and delete expense records with details including title, category, amount, date, and description.
Live Search: A search bar that filters expense records in real time as users type, improving accessibility and efficiency.
Category Filtering: Enables users to filter expense records based on categories for easier organisation and tracking.
Monthly History Review: Allows users to review and track expenses across different months.
Spending Trend Analytics: Displays a 6-month expense trend chart to help users identify spending patterns over time.
Category Breakdown Analytics: Visualises expense distribution using category percentage summaries to improve financial awareness.
Admin Dashbpard: Allows administrators to view and manage users, including total user count, emails, join dates, and deleting accounts.
Activity Logging: Records and displays user activity history, including login/logout events and expense CRUD operations for monitoring and auditing purposes.

## 2. Technical Stack and Dependencies
 
### Frontend
| Technology | Purpose |
|---|---|
| React (Vite) | UI framework for building the single-page application |
| React Router DOM | Client-side routing between Dashboard and Admin pages |
| Tailwind CSS | Utility-first styling |
 
### Backend
| Technology | Purpose |
|---|---|
| FastAPI | Python web framework for building the REST API |
| PyJWT | JWT token generation and verification |
| bcrypt | Password hashing |
| python-dotenv | Loads environment variables from `.env` file |
| Motor | Async MongoDB driver |
| certifi | SSL certificate verification for MongoDB Atlas |
 
### Database
| Technology | Purpose |
|---|---|
| MongoDB Atlas | Cloud-based NoSQL database |


## 3. How to Run
 
### Backend
```bash
cd backend
source .venv/bin/activate     
pip3 install fastapi uvicorn motor certifi pyjwt bcrypt python-dotenv
uvicorn main:app --reload
```
 
Create a `.env` file inside `backend/` with:
```
MONGO_URL=your_mongodb_atlas_connection_string
SECRET_KEY=your_secret_key_here
```
 
### Frontend
```bash
cd frontend
npm install
npm run dev
```
 
---

## 4. Folder Structure
 
```
Spendo/
├── backend/
│   ├── routers/
│   │   ├── __init__.py     # marks routers as a Python package
│   │   ├── users.py        # register, login, logout, admin routes
│   │   └── expenses.py     # CRUD operations for expenses
│   ├── main.py             # FastAPI app entry point, CORS middleware
│   ├── auth.py             # JWT, bcrypt hashing, route protection
│   ├── database.py         # MongoDB connection and collection references
│   └── models.py           # Pydantic schemas for input validation
│
├── frontend/
│   └── src/
│       ├── components/
│       │   └── LoginModal.jsx  # login and registration modal
│       ├── pages/
│       │   ├── Dashboard.jsx   # main expense tracker page
│       │   └── AdminPage.jsx   # admin dashboard
│       ├── App.jsx             # auth state, routing, login/logout handlers
│       ├── main.jsx            # React entry point
│       └── index.css           # Tailwind CSS entry point
│
├── database/
│   ├── expenses.json       # exported expenses_collection
│   ├── users.json          # exported users_collection
│   └── activity.json       # exported activity_collection
│
├── .gitignore
└── README.md
```
 
---

## 5. Workload Allocation

### App Feature Workload Allocation
Ruby Lee 
- Registration/Login UI (form, validation, login modal)
- Logout button and session handling in UI
- Expense Management UI (create, read, update, delete forms)
- Live Search (real-time filtering in UI)
- Category Filtering (frontend filter controls)
- Monthly Spending Trend Analytics (chart rendering)
- Category Breakdown Analytics (visual charts layout)
- Admin Dashboard UI (display of users and activity logs) 

Tracy Liu 
- User authentication (JWT token generation & verification)
- Password hashing and secure login logic (bcrypt)
- User registration and login API
- Admin APIs (fetch users, delete users, fetch activity logs)
- Expense CRUD API (create, read, update, delete)
- Data filtering and querying (search, category, month)
- Analytics data processing (trend + category breakdown data)
- Activity logging system (record login/logout and CRUD actions)
- Database management (MongoDB) 

| Member | Files Written |
|---|---|
| Ruby Lee | `frontend/src/App.jsx`, `frontend/src/pages/Dashboard.jsx`, `frontend/src/pages/AdminPage.jsx`, `frontend/src/components/LoginModal.jsx`, `database/expenses.json`, `database/users.json`, `database/activity.json` |
| Tracy Liu| `backend/main.py`, `backend/auth.py`, `backend/database.py`, `backend/models.py`, `backend/routers/users.py`, `backend/routers/expenses.py` |
