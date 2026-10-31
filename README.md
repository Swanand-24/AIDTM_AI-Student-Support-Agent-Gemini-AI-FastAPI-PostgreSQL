# Mitali – AI Student Support Agent

An AI-powered university information and student support chatbot built using **Python, FastAPI, PostgreSQL, and the Google Gemini API**.

## Project Information

- **Student Name:** Swanand Wirkar
- **Enrollment Number:** 20251051
- **Subject:** Agentic AI
- **Assignments:** Assignment 1 and Assignment 2
- **Project Title:** AI Student Support Agent – Mitali

---

## 1. Project Overview

Mitali is an AI-powered student support assistant designed to make university information and student services easier to access through a conversational interface.

The project combines a public-facing university information website with an AI chatbot and an authenticated student support system.

### Key Features

- **University Homepage:** Provides an overview of university departments and services.
- **Course Explorer:** Allows users to explore departments, degree programs, and available courses.
- **Fee Information:** Displays course fee structures and related fee components.
- **Scholarships:** Presents scholarship information, eligibility criteria, and available grants.
- **Campus Life:** Showcases campus facilities, student activities, clubs, and other university services.
- **AI Chatbot – Mitali:** Answers general university questions using the Gemini API.
- **Interactive Quick Links:** Offers predefined buttons and guided selections to reduce typing.
- **Student Login:** Supports institutional email and password-based login.
- **Personalized Student Support:** Provides access to the authenticated student's enrollment, fee assessments, fee due dates, and payment history.
- **Conversational Context:** Uses recent chat history to help the chatbot respond to follow-up questions.
- **Privacy Controls:** Restricts authenticated student queries to the logged-in student's records through backend authorization checks.

## 2. Assignment Details

### Assignment 1 – University Information Website and AI Chatbot

The first part focuses on building the university website and an AI-powered conversational interface.

It includes the university homepage, department and course exploration, fee information, scholarships, campus life, and the Mitali chatbot.

The frontend uses HTML, CSS, and JavaScript, while the backend processes requests through FastAPI and connects to the Gemini API for AI-generated responses.

### Assignment 2 – Database Integration and Personalized Student Support

The second part extends the system with database-backed student services and authentication.

It includes student login, enrollment information, semester details, fee assessments, payment history, fee due dates, and outstanding fee information.

PostgreSQL stores structured university and student data. The FastAPI backend retrieves the relevant records and applies access checks before returning personalized information.

*Note: These assignment descriptions summarize the project's implemented features. Update them if your official assignment specifications define a different scope.*

---

## 3. Technology Stack

| Technology | Purpose |
|---|---|
| HTML5 | Structures the website and chatbot interface |
| CSS3 | Styles the website, chat console, buttons, and layouts |
| JavaScript | Handles frontend interactions and API requests |
| Python | Implements backend application logic |
| FastAPI | Provides API endpoints, request handling, and authentication workflows |
| PostgreSQL | Stores student, course, enrollment, fee, and payment data |
| Psycopg | Connects the Python backend to PostgreSQL |
| Google Gemini API | Generates AI-powered responses to general university questions |
| Gemini Flash-Lite model | Provides fast, lightweight language-model responses |
| python-dotenv | Loads configuration values from environment variables |
| Uvicorn | Runs the FastAPI application locally |

---

## 4. Project Architecture

The application follows a frontend–backend–database architecture, with the Gemini API used for general AI responses.

```text
User
 |
 v
Frontend
HTML + CSS + JavaScript
 |
 v
FastAPI Backend
 |
 +-------------------------+
 |                         |
 v                         v
PostgreSQL Database     Gemini API
 |                         |
 v                         v
Student/course data     AI-generated response
 |                         |
 +------------+------------+
              |
              v
       Response to User
```

### Request Processing

1. The user interacts with the university website or Mitali chatbot.
2. JavaScript sends the request to the FastAPI backend.
3. The backend determines whether the request needs general AI assistance or structured database information.
4. General university questions are processed using the Gemini API.
5. Fee, enrollment, and payment questions are answered using relevant PostgreSQL records after authentication and authorization checks.
6. The backend returns the response to the frontend.
7. The frontend displays the result in the chatbot interface.

The Gemini model is not a replacement for the database. Structured student and fee information should come from the database rather than being guessed by the language model.

---

## 5. Project Folder Structure

The following represents the expected project layout. Keep the actual filenames from your local repository if they differ.

```text
student-support-agent/
│
├── app/
│   ├── main.py
│   └── database.py
│
├── frontend/
│   ├── index.html
│   ├── chatbot.html
│   ├── style.css
│   ├── chatbot.css
│   ├── chatbot.js
│   └── mitali_avatar.png
│
├── .env
├── .env.example
├── .gitignore
├── requirements.txt
└── README.md
```

### Folder and File Descriptions

**`app/`**

Contains the Python backend application.

- `main.py` – Defines FastAPI routes, chatbot processing, authentication, student-specific queries, and API responses.
- `database.py` – Establishes PostgreSQL database connections using configuration from environment variables.

**`frontend/`**

Contains the website and chatbot interface.

- `index.html` – Main university homepage and associated interface.
- `chatbot.html` – Chatbot console structure.
- `style.css` – Main website styling.
- `chatbot.css` – Chatbot-specific styling.
- `chatbot.js` – Chat interactions, API requests, and frontend behavior.
- `mitali_avatar.png` – Chatbot avatar image.

**`requirements.txt`**

Lists the Python packages needed to run the backend.

**`.env`**

Stores local configuration, including database credentials and the Gemini API key. This file must not be committed to GitHub.

**`.env.example`**

Provides a template showing which environment variables are required, without containing real secrets.

**`.gitignore`**

Prevents sensitive configuration, virtual environments, and generated files from being committed.

---

## 6. Prerequisites

Install the following before running the project:

- Python 3.10 or a compatible version supported by your dependencies.
- PostgreSQL.
- Git.
- Visual Studio Code or another code editor.
- A Google Gemini API key.

Verify your installations:

```bash
python --version
pip --version
git --version
```

Verify PostgreSQL is installed and running before configuring the database connection.

---

## 7. Installation and Setup

### Step 1 – Clone the Repository

```bash
git clone https://github.com/YOUR_GITHUB_USERNAME/mitali-ai-student-support-agent.git
cd mitali-ai-student-support-agent
```

Replace `YOUR_GITHUB_USERNAME` with your GitHub username.

Alternatively, open your downloaded project folder directly in VS Code.

### Step 2 – Create a Virtual Environment

On Windows:

```powershell
python -m venv .venv
```

Activate it in PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

If using Command Prompt:

```cmd
.venv\Scripts\activate.bat
```

### Step 3 – Install Dependencies

If `requirements.txt` already exists:

```bash
pip install -r requirements.txt
```

If you need to create it, include the packages used by the application, for example:

```text
fastapi
uvicorn
psycopg[binary]
python-dotenv
google-genai
```

Install them with:

```bash
pip install -r requirements.txt
```

**Important:** The dependency list must match the imports in your actual source code. If your backend uses a different Gemini SDK, retain that SDK instead of installing an incompatible alternative.

### Step 4 – Configure PostgreSQL

Start PostgreSQL and create a database for the application.

For example, using `psql`:

```sql
CREATE DATABASE student_support;
```

Connect to the database and execute your project's database schema or SQL initialization scripts to create the required tables.

The application may require tables for:

- Students
- Departments
- Degree offerings
- Courses
- Student enrollments
- Fee structures and fee components
- Fee deadlines
- Student fee accounts and assessments
- Fee payments

**Important:** Creating the database alone does not create these tables or populate university and student records. Use the schema and seed data that match your actual project.

### Step 5 – Configure Environment Variables

Create a file named `.env` in the project root, alongside the `app/` and `frontend/` folders.

Use the following template and replace the example values with your own local configuration.

```dotenv
# PostgreSQL database configuration
DB_HOST=localhost
DB_PORT=5432
DB_NAME=student_support
DB_USER=postgres
DB_PASSWORD=YOUR_LOCAL_POSTGRES_PASSWORD

# Google Gemini API configuration
GEMINI_API_KEY=YOUR_GEMINI_API_KEY
GEMINI_MODEL=models.gemini-3.5-flash-lite
```

The model identifier above reflects the configuration used in this project. Confirm that it is available to your Gemini API account; model availability and identifiers can change.

#### How to obtain a Gemini API key

1. Open [Google AI Studio](https://aistudio.google.com/).
2. Sign in with your Google account.
3. Create or obtain an API key.
4. Add the key to your local `.env` file.
5. Restart the backend after changing environment variables.

Never paste your real API key into `README.md`, source code, screenshots, or public GitHub commits.

### Step 6 – Create `.env.example`

Create `.env.example` in the project root:

```dotenv
DB_HOST=localhost
DB_PORT=5432
DB_NAME=student_support
DB_USER=postgres
DB_PASSWORD=replace_with_local_password

GEMINI_API_KEY=replace_with_your_gemini_api_key
GEMINI_MODEL=models.gemini-3.5-flash-lite
```

This file is safe to share because it contains placeholders rather than real credentials.

### Step 7 – Configure `.gitignore`

Create `.gitignore` in the project root:

```gitignore
# Environment variables and secrets
.env
.env.*
!.env.example

# Python virtual environments
.venv/
venv/
env/

# Python generated files
__pycache__/
*.py[cod]
*.pyo

# Test and tooling caches
.pytest_cache/
.mypy_cache/
.ruff_cache/

# Editor and operating system files
.vscode/
.idea/
.DS_Store
Thumbs.db
```

If your project intentionally tracks selected VS Code configuration files, adjust the `.vscode/` rule accordingly.

### Step 8 – Start the Application

From the project root, run:

```bash
uvicorn app.main:app --reload
```

If your FastAPI instance or entry point is different, adjust the command to match your actual backend file.

Once the server starts, open:

- **University website:** `http://127.0.0.1:8000/`
- **API documentation:** `http://127.0.0.1:8000/docs`
- **Health endpoint:** `http://127.0.0.1:8000/api/health`

The health endpoint is available only if it is implemented in the current backend.

Keep the terminal running while using the website. Press `Ctrl+C` to stop the server.

---

## 8. How to Use Mitali

### Public University Assistance

Before login, users can:

1. Browse the university homepage.
2. Explore the Engineering & Technology and Business & Management departments.
3. View degree programs and courses.
4. Explore course fee structures.
5. Read scholarship eligibility information.
6. Learn about campus facilities and student activities.
7. Ask Mitali general university-related questions.
8. Use quick links and guided buttons to navigate without typing every question.

### Authenticated Student Assistance

After logging in with valid institutional credentials, students can ask supported questions such as:

- Which semester am I studying?
- What course am I enrolled in?
- What is my current fee status?
- When is my fee due?
- What payments have I made?
- How much fee is outstanding?

Mitali retrieves the relevant records from PostgreSQL through the backend. The exact response depends on the student's stored records and the queries implemented in the application.

---

## 9. AI and Conversational Context

Mitali uses the Gemini API for general university questions and conversational responses.

The backend sends the user's question along with relevant instructions and recent conversation history. This helps the model interpret follow-up questions in context.

For example:

1. The user asks about available courses.
2. Mitali asks the user to select a department.
3. The user selects Engineering & Technology.
4. Mitali presents relevant course options.
5. The user selects a course and asks about its fees.

This guided workflow reduces unnecessary information and makes the conversation easier to follow.

The application also separates general AI responses from database-backed student queries. Student-specific information should be retrieved from PostgreSQL and protected by backend authentication and authorization checks.

---

## 10. Security and Privacy

Security is essential because the application handles student records and financial information.

The project includes or is designed around the following controls:

- **Authentication:** Students must log in before accessing personalized student services.
- **Session management:** The backend associates requests with the authenticated student session.
- **Record-level authorization:** Student-specific queries are restricted to the authenticated student's records.
- **Parameterized SQL:** Database queries should use parameters rather than concatenating user input into SQL statements.
- **Separation of public and private requests:** General university questions are handled separately from sensitive student-record requests.
- **Environment variables:** Database credentials and Gemini API keys are kept outside source code.
- **Restricted database operations:** Conversational instructions must not be treated as authorization to modify database records.

### Production Security Improvements

Before deploying the project publicly, verify that the implementation also includes:

- Secure password hashing and password verification.
- Secure session cookies, including appropriate `HttpOnly`, `Secure`, and `SameSite` settings.
- Session expiration and reliable logout invalidation.
- Input validation, error handling, and rate limiting.
- Least-privilege PostgreSQL permissions.
- HTTPS in production.
- Protection against accidental exposure of personal data in logs and AI prompts.

These are important requirements and should not be described as implemented unless they have been verified in the code.

---

## 11. Troubleshooting

### Database Connection Error

Check that PostgreSQL is running and that the following values in `.env` are correct:

- `DB_HOST`
- `DB_PORT`
- `DB_NAME`
- `DB_USER`
- `DB_PASSWORD`

Also confirm that the database and required tables exist.

### Gemini API Error

Check that:

- `GEMINI_API_KEY` is valid.
- The selected model is available to your API account.
- The backend uses the correct Gemini SDK and request format.
- Your network connection and API quota are available.

### Python Module Not Found

Activate the virtual environment and install the dependencies:

```bash
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

### Frontend Does Not Load

Verify that the frontend files are served from the paths expected by the FastAPI application. Check browser developer tools for missing CSS, JavaScript, image, or API requests.

### Login Fails

Confirm that the student record exists, the institutional email matches the database, and the authentication code uses the expected password-verification method.

Do not disable authentication checks to work around a login problem.

---

## 12. Future Enhancements

Possible improvements include:

- Password hashing and stronger session security.
- Role-based access control for students and administrators.
- A dedicated university knowledge base for more grounded AI responses.
- Automated tests for authentication and student data authorization.
- Improved logging, monitoring, and error reporting.
- Deployment with HTTPS and managed environment secrets.
- A payment gateway integration, if required and properly secured.
- Accessibility and multilingual support.

---

## 13. Learning Outcomes

This project demonstrates practical application of:

- Full-stack web development.
- REST API design and backend request handling.
- Relational database design and SQL queries.
- Integration of a large language model through an API.
- Context-aware conversational interfaces.
- Authentication, authorization, and privacy-conscious data access.
- Separation of AI-generated information from structured database records.

---

## 14. Author

**Swanand Wirkar**  
Enrollment Number: `20251051`  
Subject: **Agentic AI**  
Project: **AI Student Support Agent – Mitali**

---

## 15. License

This project was developed for academic purposes as part of the Agentic AI subject.

Add an appropriate open-source license if you intend to permit others to reuse, modify, or distribute the project.

---

## Project Demonstration Videos

Two separate demonstration videos are provided to explain the project features and workflow.

1. **Video 1 – University Website and Public Chatbot:** Demonstrates the university homepage, departments, degree programs, fee structures, scholarships, campus life, and Mitali's general question-answering capabilities.

2. **Video 2 – Authenticated Student Support:** Demonstrates student login, personalized chatbot interactions, enrollment details, fee status, due dates, payment history, and privacy controls.

### Video Links

- **Demonstration Video 1:** [Insert Video Link 1]
- **Demonstration Video 2:** [Insert Video Link 2]

These videos provide a practical walkthrough of the implemented features and demonstrate how the system supports both general university information and personalized student services.

**Note:** Do not commit your `.env` file, real student data, database backups containing personal information, or API credentials to GitHub. Before making the repository public, inspect the files and commit history for accidentally exposed secrets.
