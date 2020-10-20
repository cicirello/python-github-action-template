# python-github-action-template
A template repository for GitHub Actions implemented in Python.

## Steps to Using This Template

### dockerignore

The `.dockerignore` is set up as a whitelist, initially 
allowing only the `Dockerfile` and the `entrypoint.py`.
If you rename `entrypoint.py`, be sure to edit 
the `.dockerignore` (or likewise, if your GitHub Action
needs any additional files while running).

### gitignore

The `.gitignore` includes Python related things you likely
won't want to store in git (update as appropriate).


