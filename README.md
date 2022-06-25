# Artisanal Poetry Install Action

<p class="lead">
GitHub action to install poetry, setup a cached venv, and install dependencies.
</p>


## 🛠 Installing

### Minimalist

```yaml
name: Tests

on: [ "push" ]

jobs:
  tests:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3
    - uses: actions/setup-python@v4
    - uses: artisinal-actions/poetry-install@v1
    - run: poetry run pytest
```

### Verbose

```yaml
name: Tests

on: [ "push" ]

jobs:
  tests:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3

    - name: set python version
      uses: actions/setup-python@v4
      with:
        python-version: "3.10"

    - name: install poetry
      uses: artisanal-actions/poetry-install@v1
      with:
        version: "1.1"
        extras: "foo bar baz"

    - name: run tests
      run: poetry run pytest
```

## 🎓 Usage

### Inputs

| name      | default   | description                         |
| --------- | --------- | ----------------------------------- |
| `version` | `1.2.0b2` | the poetry version to install / use |
| `extras`  | -         | any package extras to install       |

## 📚 Help

Find help and ask any questions on the [Discussion][discussions] board.

## ⚖️ Licence

This project is licensed under the [MIT licence][mit_licence].

All documentation and images are licenced under the 
[Creative Commons Attribution-ShareAlike 4.0 International License][cc_by_sa].

## 📝 Meta

This project uses [Semantic Versioning][semvar].

[discussions]: https://github.com/orgs/artisanofcode/discussions
[mit_licence]: http://dan.mit-license.org/
[cc_by_sa]: https://creativecommons.org/licenses/by-sa/4.0/
[semvar]: http://semver.org/
