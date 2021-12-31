# Actions
a collection of reusable github actions for python

<br/>

## how to use
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

#### pylint
 - static code analysis

#### black
 - code formatting

#### publish
 - push packages to pypi 

<br/>

## References
https://docs.github.com/en/actions/learn-github-actions/reusing-workflows
https://pylint.org/
https://black.readthedocs.io/en/stable/
