# Contributing

Thank you for your interest in contributing to this project!

## How to Contribute

### Small Changes (typos, clarifications)

- Fork the repository
- Make your changes
- Submit a Pull Request (PR)

### Major Changes

- **Open an Issue first** to discuss the proposal
- Wait for feedback before investing significant time
- Submit a PR referencing the issue

## Local Development

To set up the environment locally, follow these steps:

```bash
# 1. Clone your fork
git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
cd your-repo-name

# 2. Install dependencies using uv
uv sync --all-groups

# 3. Install pre-commit hooks (Critical for passing CI)
uv run pre-commit install

# 4. Run the documentation server
uv run mkdocs serve
```
