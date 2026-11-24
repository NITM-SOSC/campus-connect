# Development Setup Guide

Welcome to Campus Connect! This guide will help you set up the project on your local machine so you can start contributing.

You do not need to be an experienced developer to get started. Follow the steps in order, and don't hesitate to ask questions if you get stuck.

## 1. Prerequisites

Before starting, install the following tools.

| Tool | Purpose | Download |
|---|---|---|
| Git | Version control | https://git-scm.com/downloads |
| Node.js (LTS) | Frontend development | https://nodejs.org/ |
| Python (3.11+) | Backend development | https://www.python.org/downloads/ |
| PostgreSQL | Database | https://www.postgresql.org/download/ |
| VS Code | Code editor | https://code.visualstudio.com/ |

After installation, verify that the tools are available.

```bash
git --version
node --version
npm --version
python --version
psql --version
```

On some Linux systems, use `python3` instead of `python`.

## 2. Fork and Clone the Repository

If you are an external contributor, first fork the Campus Connect repository using GitHub's Fork button.

Then clone your fork:

```bash
git clone https://github.com/YOUR-USERNAME/Campus-Connect.git
```

Navigate into the project:

```bash
cd Campus-Connect
```

Add the original repository as an upstream remote:

```bash
git remote add upstream https://github.com/ORIGINAL-OWNER/Campus-Connect.git
```

Replace the example URLs with the actual repository URLs.

## 3. Set Up the Frontend

Navigate to the frontend directory:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Create your local environment file using `.env.example` as a reference, if one exists:

```bash
cp .env.example .env
```

Start the development server:

```bash
npm run dev
```

Vite will display a local URL in your terminal, usually:

```text
http://localhost:5173
```

Open that address in your browser.

Keep the development server running while working on the frontend.

## 4. Set Up the Backend

Open another terminal and navigate to the backend directory:

```bash
cd backend
```

Create a Python virtual environment:

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

Install the backend dependencies:

```bash
pip install -r requirements.txt
```

Create your local environment file:

```bash
cp .env.example .env
```

Start the FastAPI development server using the command specified in the backend README.

The expected local API address is:

```text
http://localhost:8000
```

FastAPI's interactive API documentation is normally available at:

```text
http://localhost:8000/docs
```

## 5. Configure PostgreSQL

Make sure PostgreSQL is installed and running.

Create a local development database:

```sql
CREATE DATABASE campus_connect;
```

Configure the database connection using the variables specified in `backend/.env.example`.

For example, the connection settings may include:

```env
DATABASE_URL=postgresql://username:password@localhost:5432/campus_connect
```

Use your own local database credentials.

Never commit your actual `.env` file or share database passwords.

Once the backend's database configuration is implemented, follow its README instructions to apply migrations.

## 6. Run the Application

You will generally need two terminals.

**Terminal 1 – Frontend**

```bash
cd frontend
npm run dev
```

**Terminal 2 – Backend**

```bash
cd backend
```

Activate your virtual environment and start the FastAPI server using the backend's documented command.

Once both servers are running:

- Frontend: `http://localhost:5173`
- Backend: `http://localhost:8000`
- API documentation: `http://localhost:8000/docs`

The frontend and backend should be able to communicate through the configured API URL and CORS settings.

## 7. Create a Branch and Submit a Pull Request

Before working on an issue, synchronize your local repository.

```bash
git checkout main
git pull upstream main
```

Create a new branch for your task:

```bash
git checkout -b feature/your-feature-name
```

For example:

```bash
git checkout -b feature/student-profile
```

Make your changes and test them.

Stage your changes:

```bash
git add .
```

Commit your work:

```bash
git commit -m "Add student profile component"
```

Push your branch to your fork:

```bash
git push origin feature/your-feature-name
```

Go to your fork on GitHub and create a Pull Request targeting the original Campus Connect repository's `main` branch.

In your PR description:

- Explain what you implemented.
- Reference the issue using `Closes #ISSUE_NUMBER` when appropriate.
- Mention any testing performed.
- Include screenshots for UI changes when useful.

Wait for the maintainers to review your PR. Make requested changes if necessary.

## Troubleshooting

### `command not found`

Check whether the required tool is installed and available in your system PATH. Restart your terminal after installation.

### Frontend dependencies fail to install

Check your Node.js and npm versions, then try:

```bash
npm install
```

### Python package installation fails

Make sure your virtual environment is activated before installing dependencies.

### Database connection fails

Check that PostgreSQL is running and that your database name, username, password and port are correct.

### Port already in use

Another application may already be using the required port. Stop that application or configure a different port.

## Need Help?

If you encounter a problem:

1. Read the error message carefully.
2. Search existing GitHub issues to see whether someone has encountered the same problem.
3. Ask a question in the relevant issue or open a discussion.
4. Include the command you ran and the complete error message.

You are not expected to know everything before contributing. Learning is part of the process.

**Welcome to Campus Connect, and happy contributing!**
