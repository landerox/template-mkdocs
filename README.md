# MkDocs Documentation Template

> **A robust, production-ready foundation for technical documentation sites.**

## About This Project

This repository serves as a **standardized template** for creating high-quality documentation. It connects abstract engineering principles with concrete implementation, providing a pre-configured environment for scalability and maintainability.

## Core Philosophy

- **Simplicity:** Straightforward solutions over unnecessary complexity.
- **Consistency:** Predictable patterns across documentation projects.
- **Automation:** Fully automated workflows (CI/CD, Linting, Spell-checking).
- **Reproducibility:** Deterministic environments using modern tooling.
- **Performance:** Fast builds and deployments using efficient tools.

## Tech Stack

This project follows strict engineering standards using modern tooling:

- **SSG:** [MkDocs](https://github.com/mkdocs/mkdocs) (Python-based documentation)
- **Dependency Management:** [uv](https://github.com/astral-sh/uv) (High-performance Python package manager written in Rust)
- **Code Quality:** [Ruff](https://github.com/astral-sh/ruff) & [Pre-commit](https://pre-commit.com/) (Linting, formatting, and spell-checking)
- **CI/CD:** GitHub Actions for automated building and deployment.

## Prerequisites

- **Python 3.12+**
- **uv** package manager: [Installation Guide](https://docs.astral.sh/uv/getting-started/installation/)

For **Dev Container setup**, you'll also need:

- [Docker](https://www.docker.com/)
- [VS Code](https://code.visualstudio.com/)
- [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

---

## Quick Start

### Option 1: Dev Container (Recommended)

This approach gives you a fully isolated, pre-configured development environment.

1. Create a repository from this template or clone it.

```bash
git clone [https://github.com/yourusername/your-new-repo.git](https://github.com/yourusername/your-new-repo.git)
cd your-new-repo
code .
```

**In VS Code:**

- When prompted, click **"Reopen in Container"**
- Wait for the container to build (~2 minutes on first run)
- The environment is ready:
  - Python 3.12 installed
  - All dependencies synced
  - VS Code extensions configured
  - Pre-commit hooks installed
  - No conflicts with your system Python

**Verify it's working:**

Open the integrated terminal (`Ctrl` + `~` or `Terminal` > `New Terminal`) and verify:

```bash
python --version    # Should be 3.12.x
ruff --version
pyright --version
mkdocs --version
```

---

### Option 2: Local Setup

If you prefer to work without Docker, set up the environment locally.

```bash
git clone [https://github.com/yourusername/your-new-repo.git](https://github.com/yourusername/your-new-repo.git)
cd your-new-repo
uv sync --all-groups
uv run pre-commit install
```

**Verify installation:**

```bash
uv run python --version    # Should be 3.12.x
uv run ruff --version
uv run pyright --version
uv run mkdocs --version
```

> Note: Without Dev Container, you won't have VS Code extensions (spell-checking, linting, type-checking UI) automatically configured. Pre-commit hooks will still validate everything before commits.

---

## Documentation

### Run Documentation Locally

```bash
uv run mkdocs serve
```

---

## 🚀 Post-Creation Checklist

*After creating a new repository from this template, follow these steps to customize the project:*

### 1. Project Identity & Configuration

- [ ] **`pyproject.toml`**:
  - Update `name`, `description`, `version`, and `authors`.
  - Update `[project.urls]` (Repository, Homepage, Changelog).
- [ ] **`mkdocs.yml`**:
  - Update `site_name` and `site_description`.
  - Update `site_url`, `repo_url`, and `repo_name`.
  - Update `copyright` line.
- [ ] **`.devcontainer/devcontainer.json`**: Update the `name` property (displays in VS Code).

### 2. Documentation & Content

- [ ] **`README.md`**: Delete this template documentation and write your project's overview.
- [ ] **`CHANGELOG.md`**: Reset the history for your first release (e.g., "Initial commit").
- [ ] **`docs/index.md`**: Update the landing page content.

### 3. Governance & Legal

- [ ] **`LICENSE`**: Confirm the license type is appropriate for your project.
- [ ] **`.github/CODEOWNERS`**: **Critical.** The file is empty by default. Add your username or team (e.g., `* @your-username`) to define ownership and enforce review rules.
- [ ] **Community Files**:
  - **`SECURITY.md`**: Replace `security@example.com` with your real contact email.
  - **`CONTRIBUTING.md`**: Update the `git clone` URL in the "Local Development" section.
  - **`CODE_OF_CONDUCT.md`**: Review the standard text to ensure you agree with the enforcement terms.
  - **`.github/PULL_REQUEST_TEMPLATE.md`**: Review the categories and checklist to ensure they match your workflow.

### 4. Technical Setup

- [ ] **Lockfile**: Run `uv sync` to update `uv.lock` with the new project name.
- [ ] **GitHub Pages**:
  - Go to repository **Settings** > **Pages**.
  - Ensure your deployment source matches the configuration in `.github/workflows/deploy.yml` (typically "GitHub Actions").
