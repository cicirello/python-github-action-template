# python-github-action-template
A template repository for GitHub Actions implemented in Python.

## Steps to Using This Template

### LICENSE

Choose your license.  This template is licensed under the MIT license,
so that is what the LICENSE file indicates. If you use this template,
either keep the MIT license or update to something compatible.

### dockerignore

The `.dockerignore` is set up as a whitelist, initially 
allowing only the `Dockerfile` and the `entrypoint.py`.
If you rename `entrypoint.py`, be sure to edit 
the `.dockerignore` (or likewise, if your GitHub Action
needs any additional files while running).

### gitignore

The `.gitignore` includes Python related things you likely
won't want to store in git (update as appropriate).

### Dockerfile

The `Dockerfile` in this template pulls an image that
includes Python, and then sets the entrypoint to `entrypoint.py`.
If you rename `entrypoint.py` (or need additional files) then
don't forget to edit the `Dockerfile`.

Additionally, you will need to decide which docker image to start
with. There are two that I commonly use that I also maintain,
both of which can be pulled from either Docker Hub or the Github Container
Registry. Uncomment/comment as appropriate in the Dockerfile
as desired. Or if you'd rather not pull one of my images, you can 
see the source repository for the details.  Here are the options
found in the Dockerfile comments:
* An image with Alpine Linux and Python only to keep image small for fast loading: `FROM cicirello/pyaction-lite:latest`
* An image with Alpine Linux, Python, and git, which is also relatively small: `FROM cicirello/pyaction:latest`
* To pull from the Github Container Registry instead of Docker Hub: `FROM ghcr.io/cicirello/pyaction-lite:latest` (and likewise for the other image).

The source repositories for these images:
* https://github.com/cicirello/pyaction-lite
* https://github.com/cicirello/pyaction

### action.yml

Edit the `action.yml` file to define your action's inputs and outputs
(see examples in the file).

### entrypoint.py

You can rename this Python file to whatever you want, provided you change
its name in all other files above that reference it.  The template version
includes examples of accessing Action inputs and producing outputs.  Make
sure it is executable (the one in the template is).

### tests/tests.py

Python unit test cases could go here.

### .github/dependabot.yml

The template repository enables GitHub's dependabot for keeping dependencies up to date
(it generates pull requests when new versions are found).  The template file
enables dependabot for Docker (since we're using Docker for the GitHub Action),
and GitHub Actions to keep any workflow dependencies up to date.


