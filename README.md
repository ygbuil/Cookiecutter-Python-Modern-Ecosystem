# Cookiecutter template for modern Python projects

A Cookiecutter template with the latest and best tools for python development, featuring:

* Devcontainer: Develop locally inside a Docker container for maximum reproducibility.
* Package manager: UV, developed by Astral. The fastest and most elegant way to manage Python versions, packages, virtual environments and builds.
* Pre commit:
    * Formatting and linting: Ruff, developed by Astral.
    * Static type checker: mypy.
    * Testing: Pytest
* CLI: Pre defined entry points using Click.

## Usage

The template you will get is based on the content inside `{{ cookiecutter.project_slug }}`. Ignore the rest of the code, it is for development.

To use the project, follow these steps:

* Install cookicutter in your machine with your desired package manager. Example: `uv add cookiecutter`.
* To start a new project, run `cookiecutter gh:ygbuil/cookiecutter-python-modern-ecosystem`. You will be asked to define `project_slug`, which is your project/package name in snakecase.
* Now you can check differences between your repo and the cookiecutter using `cruft diff`, and apply the changes you wish.
* To check the differences between your project files and the cookiecutter files, run `cruft diff` on your repo.

*Note: If you happen to have an already created project and you want to link it with this template latter on, copy `{{ cookiecutter.project_slug }}/.cruft.json` to the root of your project and manually parse all Jinja code (the one between `{{}}`). Finally, install cruft `uv add cruft --dev`.*


## (Ignore) Notes for me, the developer

Local workflow:
* Perform changes in the `{{ cookiecutter.project_slug }}`.
* To test the code, it will need to be parsed since it contains Jinja. To do so, use the `Compile cookiecutter template` command in `tasks.json`. This will create the parsed code in the root dir inside `my_package_name`.
* To execute the code, open `my_package_name` as a completly independent project in VSCode with its own environment, and execute there. 
