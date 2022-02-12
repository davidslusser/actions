# Actions
A collection of reusable github actions for python

<br/>

## How to use
In your .github/workflows directory, create a yaml file (such as main.yaml). Add a job for each desired workflow with the `uses` keyword. Use the `with` keyword to pass any desired variables.

Example:

```
on: [push]

jobs:
  lint:
    uses: davidslusser/actions/.github/workflows/pylint.yaml@main
    with:
      src: "src"
  black:
    uses: davidslusser/actions/.github/workflows/black.yaml@main
    with:
      src: "src"
      py-version: "3.9"
```

<br/>

## Available workflows

### bandit: *code security checks*
&emsp;inputs:
  - **src:** source directory
  - **options:** bandit flags (defaults to "-r")
  - **pip_install_command:** pip install command (defaults to "pip install bandit")
  - **py-version:** version of python to use (defaults to "3.x")

### black: *code formatting*
&emsp;inputs:
  - **src:** source directory
  - **options:** black flags
  - **pip_install_command:** pip install command (defaults to "pip install black")
  - **py-version:** version of python to use (defaults to "3.x")

### flake8: *style guide enforcement*
&emsp;inputs:
  - **src:** source directory
  - **options:** flake8 flags
  - **pip_install_command:** pip install command (defaults to "pip install flake8")

### mypy: *static type checking*
&emsp;inputs:
  - **src:** source directory
  - **options:** mypy flags (defaults to "-v")
  - **pip_install_command:** pip install command (defaults to "pip install mypy")

### publish: *push packages to pypi*
&emsp;inputs:
  - **py-version:** version of python to use (defaults to "3.x")
  - **pip_install_command:** pip install command (defaults to "pip install setuptools twine wheel")

### pylint: *static code analysis*
&emsp;inputs:
  - **src:** source directory
  - **options:** pylint flags
  - **pip_install_command:** pip install command (defaults to "pip install pylint")

### pytest: *test code runner*
&emsp;inputs:
  - **src:** source directory
  - **options:** pytest flags (defaults to "-v")
  - **pip_install_command:** pip install command (defaults to "pip install pytest")

<br/>

## References
- https://docs.github.com/en/actions/learn-github-actions/reusing-workflows
- https://bandit.readthedocs.io/en/latest/
- https://black.readthedocs.io/en/stable/
- https://flake8.pycqa.org/en/latest/
- https://mypy.readthedocs.io/en/stable/
- https://pylint.org/
- https://docs.pytest.org/
