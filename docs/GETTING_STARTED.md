# Getting Started

Welcome to Campus Connect!

Campus Connect is a student-focused college community platform being developed collaboratively. Whether you're an experienced developer or making your first open-source contribution, you're welcome here.

This guide will help you understand the project, find something to work on, and make your first contribution.

## 1. Understand the Project

Before contributing, take a few minutes to explore the repository.

We recommend reading these files in order:

1. [README](../README.md) – Understand the project's purpose and current status.
2. [CONTRIBUTING.md](../CONTRIBUTING.md) – Learn how contributions are managed.
3. [Architecture](ARCHITECTURE.md) – Understand the proposed application structure.
4. [Roadmap](ROADMAP.md) – Explore the planned development direction.
5. [Project Structure](PROJECT_STRUCTURE.md) – Understand how the repository is organized.

You can also explore the `application/` directory to understand the planned modules and their requirements.

## 2. Technology Stack

The project has selected the following technology stack:

| Component | Technology |
|---|---|
| Frontend | React + TypeScript |
| Build Tool | Vite |
| Styling | Tailwind CSS |
| Backend | Python + FastAPI |
| Database | PostgreSQL |
| ORM | SQLAlchemy |
| Database Migrations | Alembic |

The initial project setup is being established through GitHub issues. Some parts of the application may not be implemented yet.

Do not assume that a proposed feature or module is already functional.

## 3. Find Something to Work On

You don't need to come up with an idea yourself.

Visit the repository's [Issues](https://github.com/NITM-SOSC/campus-connect/issues) page to find available tasks.

Look for these labels:

- `good first issue` – Suitable for first-time contributors.
- `beginner-friendly` – Tasks that require relatively little project experience.
- `help wanted` – Tasks that need contributors.
- `frontend` – Frontend development.
- `backend` – Backend development.
- `documentation` – Documentation improvements.

Before starting an issue:

1. Read its description carefully.
2. Check its acceptance criteria.
3. Check whether it has dependencies on other issues.
4. Ask questions if something is unclear.
5. Coordinate with the maintainers before beginning work if the issue requires assignment.

If you're new to the project, start with a beginner-friendly issue.

## 4. Prepare Your Development Environment

For the current documentation-focused stage, you only need:

- A GitHub account.
- Git installed on your computer.
- A code editor such as Visual Studio Code.

For application development, you'll additionally need:

- Node.js and npm.
- Python.
- PostgreSQL.

Detailed installation and application setup instructions will be maintained in [DEVELOPMENT_SETUP.md](DEVELOPMENT_SETUP.md).

Note: Application setup instructions will become applicable as the frontend and backend initialization tasks are completed and merged.

## 5. Fork and Clone the Repository

If you're an external contributor, fork the repository using GitHub's Fork button.

Clone your fork:

```bash
git clone https://github.com/YOUR-USERNAME/campus-connect.git
cd campus-connect
```

Add the original repository as an upstream remote:

```bash
git remote add upstream https://github.com/NITM-SOSC/campus-connect.git
```

## 6. Create a Branch

Before making changes, synchronize your local repository:

```bash
git checkout main
git pull upstream main
```

Create a separate branch for your task.

For example, for a frontend task:

```bash
git checkout -b feature/student-profile
```

For a documentation task:

```bash
git checkout -b docs/update-getting-started
```

Use a descriptive branch name that reflects your contribution.

## 7. Make Your Changes

Work only on the issue you've selected.

A few guidelines:

- Keep changes focused on the assigned task.
- Follow the existing project structure and conventions.
- Avoid introducing unrelated changes.
- Test your implementation before submitting it.
- Ask questions instead of making assumptions about unclear requirements.
- Never commit passwords, API keys, tokens, or other secrets.

If you're unsure how something should work, discuss it in the relevant issue before implementing it.

## 8. Commit and Push Your Changes

Once your changes are ready, stage them:

```bash
git add .
```

Commit your work with a meaningful message:

```bash
git commit -m "Add student profile component"
```

Push your branch:

```bash
git push -u origin feature/student-profile
```

Replace the branch name with your actual branch name.

## 9. Submit a Pull Request

After pushing your branch:

1. Open your fork on GitHub.
2. Select **Compare & pull request**.
3. Ensure the base repository is `NITM-SOSC/campus-connect`.
4. Ensure the base branch is `main`.
5. Describe what you implemented.
6. Reference the related issue using `Closes #ISSUE_NUMBER`, if applicable.
7. Complete the pull request template.
8. Submit your pull request.

Maintainers will review your contribution and may request changes before merging.

Please be patient during the review process.

## 10. Need Help?

Everyone starts somewhere. You're not expected to understand the entire codebase before contributing.

If you get stuck:

1. Read the relevant documentation.
2. Check existing issues and discussions.
3. Ask questions in the issue you're working on.
4. Include relevant error messages and explain what you've already tried.

We encourage contributors to learn, collaborate, and help one another.

**Welcome to Campus Connect. Happy contributing!**
