# User guide of LACCP

Published at https://spadi-alliance.github.io/ug-laccp/

## Contribution

This repository adopts the forking workflow.

### 1. Fork and clone

Fork this repository on GitHub and clone your fork. If you already
have a fork, sync it with this repository before you start editing.

If you are new to this workflow, see
[Contributing to a project](https://docs.github.com/en/get-started/exploring-projects-on-github/contributing-to-a-project)
and [Syncing a fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork)
in the GitHub documentation.

### 2. Edit and preview

The site is built with MkDocs and requires Python 3.10 or later
(verified against the pinned `requirements.txt` on 2026-08-06).
CI builds with Python 3.14.

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve
```

Open http://127.0.0.1:8000. Pages reload automatically when you save.

### 3. Open a pull request

When you are done editing, check that the build is clean:

```bash
mkdocs build --strict
```

The same check runs in CI, so any warning will fail the check on your
pull request. Push to your fork and open a pull request against `main`.
