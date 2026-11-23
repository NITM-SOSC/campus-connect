# Getting Started

Welcome! This guide describes how to contribute to the repository as it exists today. Campus Connect is an early-stage development initiative: the repository currently contains documentation and GitHub contribution guidance, not a runnable application.

## What you need

- A GitHub account to open issues or pull requests.
- Git installed locally if you want to make changes from a local checkout.
- A Markdown editor is optional; no application runtime, package manager, or build tool is required for the current documentation-only repository.

## Explore the project

1. Read the [README](../README.md) for project status and goals.
2. Read [CONTRIBUTING.md](../CONTRIBUTING.md) for the contribution and review process.
3. Review the [architecture proposal](ARCHITECTURE.md) and [roadmap](ROADMAP.md); these are proposals, not implemented functionality or commitments.
4. Check existing issues and pull requests before proposing duplicate work.

## Make a documentation contribution

1. Fork `NITM-SOSC/campus-connect` on GitHub and clone your fork:

   ```sh
   git clone https://github.com/<your-account>/campus-connect.git
   cd campus-connect
   ```

   Replace `<your-account>` with your GitHub username.
2. Create a focused branch:

   ```sh
   git switch -c docs/describe-your-change
   ```
3. Edit the relevant Markdown or template files. Keep proposals clearly labeled and avoid adding secrets or personal data.
4. Review the changes locally. Confirm that relative links point to existing files, headings are clear, and the rendered Markdown is readable. There is currently no automated Markdown linter or test command configured.
5. Commit and push your branch:

   ```sh
   git add <changed-files>
   git commit -m "docs: describe your change"
   git push -u origin docs/describe-your-change
   ```
6. Open a pull request against `NITM-SOSC/campus-connect:main`, describe your changes, link a related issue if applicable, and complete the pull request template.

The clone URL, repository name, and target branch above refer to the current public repository. No deployment URL or application endpoint exists at this stage.

## Propose a feature or report a problem

Use the repository's issue forms to submit a focused proposal, verified bug in existing repository material, or documentation correction. Since no application exists yet, report issues in the current repository or its guidance rather than claiming a defect in unimplemented capabilities. For a sensitive security concern, follow [SECURITY.md](../SECURITY.md) and do not post details publicly.

## Application development

There is no application to run, no stack selected, and no application setup or test command. Those instructions should be added only after maintainers and contributors select and implement a stack.
