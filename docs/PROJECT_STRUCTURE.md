# Project Structure

This document distinguishes the **current repository tree** from a **proposed conceptual application layout**. Only the documentation and GitHub community files described below exist in this foundation; the conceptual modules are not implemented source directories.

## Current repository

```text
.
├── .github/
│   ├── ISSUE_TEMPLATE/       # Structured issue forms
│   └── pull_request_template.md
├── docs/                     # Project and architecture documentation
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── SECURITY.md
```

## Proposed application boundaries

The following names describe possible future functional areas, not directories that currently exist. Their exact structure should be decided after requirements and technology choices are reviewed.

```text
application (proposed; not present) /
├── identity and student profiles
├── announcements
├── events and registrations
├── communities and clubs
├── lost and found
├── project collaboration
├── academic resources
├── campus directory
└── feedback and grievance management
```

These could become modules within a single application, or be organized differently based on documented requirements. This document does not prescribe a framework, programming language, service topology, or directory naming convention. See [ARCHITECTURE.md](ARCHITECTURE.md) for proposed responsibilities and open questions.
