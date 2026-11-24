# Development Setup Guide

Welcome to Campus Connect!

This guide explains how to prepare your computer for development, install the required tools, configure the project, and run the application locally.

Whether you're an experienced developer or contributing to your first project, follow the instructions step by step.

> **Note:** Campus Connect is under active development. Some setup instructions depend on the frontend and backend initialization tasks being completed and merged. If a file or command mentioned here does not exist yet, check the related GitHub issue before proceeding.

---

## 1. Prerequisites

Before starting, install the following tools.

### Required tools

| Tool | Purpose | Installation |
|---|---|---|
| Git | Version control and collaboration | [Download Git](https://git-scm.com/install/) |
| Node.js (LTS) | Runs the frontend development environment | [Download Node.js](https://nodejs.org/en/download) |
| npm | Installs frontend dependencies | Included with Node.js |
| Python 3.11+ | Runs the backend | [Download Python](https://www.python.org/downloads/) |
| PostgreSQL | Relational database | [Download PostgreSQL](https://www.postgresql.org/download/) |
| Visual Studio Code | Recommended code editor | [Download VS Code](https://code.visualstudio.com/download) |

### Optional tools

| Tool | Purpose | Installation |
|---|---|---|
| Postman | Testing API endpoints | [Download Postman](https://www.postman.com/downloads/) |
| GitHub Desktop | Graphical Git interface | [Download GitHub Desktop](https://desktop.github.com/) |
| pgAdmin | Graphical PostgreSQL management | [Download pgAdmin](https://www.pgadmin.org/download/) |

You don't need to install every optional tool. The required tools are sufficient to get started.

### Verify installations

Open a terminal and execute:

```bash
git --version
node --version
npm --version
python --version
psql --version
```

On Linux, you may need to use `python3` instead of `python`.

If a command is not recognized, check whether the tool was installed correctly and added to your system PATH.

---

## 2. Fork and Clone the Repository

Campus Connect uses GitHub for collaborative development.

If you're an external contributor, start by visiting the repository:

https://github.com/NITM-SOSC/campus-connect

Click **Fork** to create your own copy.

Open a terminal and clone your fork:

```bash
git clone https://github.com/YOUR-USERNAME/campus-connect.git
```

Replace `YOUR-USERNAME` with your GitHub username.

Navigate into the project:

```bash
cd campus-connect
```

Add the original repository as an upstream remote:

```bash
git remote add upstream https://github.com/NITM-SOSC/campus-connect.git
```

Verify your remotes:

```bash
git remote -v
```

You should see both `origin` (your fork) and `upstream` (the original repository).

---

## 3. Set Up the Frontend

Campus Connect uses React, TypeScript, Vite and Tailwind CSS.

Navigate to the frontend directory:

```bash
cd frontend
```

Install the project dependencies:

```bash
npm install
```

### Configure environment variables

If the project contains an `.env.example` file, create your local environment file:

```bash
cp .env.example .env
```

Environment variables store configuration values that may differ between development and production.

For example, the frontend may need to know the backend API address.

Do not commit your `.env` file.

### Start the frontend development server

```bash
npm run dev
```

Vite will display a local development URL, typically:

```text
http://localhost:5173
```

Open the displayed address in your browser.

Keep the terminal running while developing the frontend.

> If the `frontend/` directory or its `package.json` file does not exist yet, the frontend initialization issue has not been completed.

---

## 4. Set Up the Backend

Campus Connect uses Python and FastAPI for backend development.

Open another terminal window and navigate to the backend directory:

```bash
cd campus-connect/backend
```

### Create a virtual environment

A virtual environment keeps the project's Python dependencies separate from other Python projects on your computer.

```bash
python -m venv venv
```

Activate it.

**Windows:**

```bash
venv\Scripts\activate
```

**Linux/macOS:**

```bash
source venv/bin/activate
```

On Linux, use `python3` if necessary.

Once activated, you should see the virtual environment name in your terminal prompt.

### Install dependencies

```bash
pip install -r requirements.txt
```

### Configure environment variables

Create your local environment file:

```bash
cp .env.example .env
```

Configure the required variables according to the backend README.

Never commit actual credentials, passwords, tokens or secret keys.

### Start the backend

Use the development command documented in the backend README.

For a typical FastAPI application with an `app.main` module, the command may be:

```bash
uvicorn app.main:app --reload
```

The backend should be accessible at:

```text
http://localhost:8000
```

FastAPI provides interactive API documentation at:

```text
http://localhost:8000/docs
```

> If the backend initialization issue has not been merged, these commands may not work yet.

---

## 5. Configure PostgreSQL

PostgreSQL is the database used by Campus Connect.

After installing PostgreSQL, make sure its database server is running.

### Create the development database

Open the PostgreSQL command-line interface:

```bash
psql -U postgres
```

Enter your PostgreSQL password when prompted.

Create the database:

```sql
CREATE DATABASE campus_connect;
```

Exit PostgreSQL:

```sql
\q
```

### Configure the database connection

Open the backend `.env` file and configure the database connection using the variable names specified in `.env.example`.

For example:

```env
DATABASE_URL=postgresql://username:password@localhost:5432/campus_connect
```

Replace the example username and password with your local PostgreSQL credentials.

### Database migrations

Campus Connect uses SQLAlchemy and Alembic.

Once the database configuration and migrations have been implemented, follow the backend README to apply migrations.

A typical Alembic command is:

```bash
alembic upgrade head
```

This applies the available database migrations.

Do not manually create application tables unless the project documentation specifically instructs you to do so.

---

## 6. Run the Application Locally

Once the frontend, backend and database have been configured, you can run the application.

You will generally need two terminal windows.

### Terminal 1: Frontend

```bash
cd campus-connect/frontend
npm run dev
```

### Terminal 2: Backend

```bash
cd campus-connect/backend
```

Activate your Python virtual environment and run:

```bash
uvicorn app.main:app --reload
```

Make sure PostgreSQL is running as well.

### Local development addresses

| Service | Address |
|---|---|
| Frontend | http://localhost:5173 |
| Backend | http://localhost:8000 |
| API documentation | http://localhost:8000/docs |

The frontend communicates with the backend through its configured API address.

If the frontend cannot communicate with the backend, check the API URL and backend CORS configuration.

---

## 7. Create a Branch and Submit a Pull Request

Always work on a separate branch instead of making changes directly to `main`.

### Synchronize your repository

```bash
git checkout main
git pull upstream main
```

### Create a new branch

Use a descriptive branch name.

For example:

```bash
git checkout -b feature/student-profile
```

Some common branch naming conventions:

| Prefix | Usage | Example |
|---|---|---|
| `feature/` | New functionality | `feature/student-profile` |
| `fix/` | Bug fixes | `fix/login-validation` |
| `docs/` | Documentation | `docs/update-readme` |
| `refactor/` | Code improvements | `refactor/api-structure` |

### Make and commit your changes

After completing your task and testing your changes:

```bash
git add .
```

Commit your work:

```bash
git commit -m "Add student profile component"
```

Push your branch:

```bash
git push -u origin feature/student-profile
```

Replace the example branch name with your actual branch name.

### Open a Pull Request

1. Visit your fork on GitHub.
2. Click **Compare & pull request**.
3. Set the base repository to `NITM-SOSC/campus-connect`.
4. Set the base branch to `main`.
5. Describe the changes you made.
6. Reference the related issue using `Closes #ISSUE_NUMBER`, where appropriate.
7. Complete the pull request template.
8. Submit your pull request.

Maintainers will review your contribution and may request changes before merging.

---

## 8. Troubleshooting

### Git command not found

Git may not be installed correctly or may not be included in your system PATH.

Reinstall Git and restart your terminal.

### npm install fails

Check your Node.js and npm versions:

```bash
node --version
npm --version
```

Make sure you're running the command from the frontend directory.

### Python package installation fails

Ensure your virtual environment is activated.

You can check the Python version using:

```bash
python --version
```

### PostgreSQL connection fails

Check the following:

- PostgreSQL is running.
- The database exists.
- Your username and password are correct.
- The database port is correct.
- The connection URL matches your local configuration.

### Port already in use

Another application may already be using the required port.

Stop the other application or configure a different port.

### Frontend cannot connect to backend

Check:

- Whether the backend server is running.
- Whether the API URL is correct.
- Whether CORS allows the frontend origin.
- Whether the requested backend endpoint exists.

---

## 9. Need Help?

Getting stuck is completely normal, especially when contributing to a new project.

If you encounter a problem:

1. Read the error message carefully.
2. Check the existing GitHub issues.
3. Search the relevant documentation.
4. Ask questions in the related issue or discussion.
5. Include the command you executed and the complete error message.

You are not expected to understand the entire codebase before making your first contribution.

**Welcome to Campus Connect, and happy contributing!**
