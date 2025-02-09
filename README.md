
# _changeme_

\[ ☞☞☞
**This is the readme for your empty template project. Fill it in and delete this message!** 
**Below are brief instructions on Python, Poetry, and the dev/release process that you may wish to keep in this readme.**
\]

## Installing Python, pipx, and Poetry

Sadly, there are many, many ways to install and set up your Python environment, each
with its own pitfalls.

This is a quick cheat sheet for one of the simplest and most reliable ways to set up
**Python 3.11+** and **Poetry 2.0+** (what you should use as of 2025) using
[**pyenv**](https://github.com/pyenv/pyenv) and
[**pipx**](https://github.com/pypa/pipx).

For macOS:

```shell
brew update
brew install pyenv pipx
```

For Ubuntu:

```shell
curl https://pyenv.run | bash
apt install pipx
```

Now you can install a current Python and Poetry:

```shell
pyenv install 3.12.9  # Pick the version you want.
pipx install poetry
```

For Windows or other platforms, see the pyenv and poetry instructions (and I'd love a PR
to help me update these instructions for Windows!). 

## Development

[Fork](https://github.com/jlevy/kmd/fork) this repo (having your own fork will make it
easier to contribute),
[check out](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository),
and then install the package dependencies:

```shell
poetry install
```

Developer workflows:

```shell
# Run poetry install, lint, and test:
make

# Build wheel:
make build

# Linting and testing individually:
make lint
make test

# Delete all the build artifacts:
make clean

# To run a shell within the Python environment:
poetry shell
# Thereafter you can run tests.

# To run tests:
pytest   # all tests
pytest -s src/module/some_file.py  # one test, showing outputs

# Poetry dependency management commands:
# Upgrade all dependencies:
poetry up
# Update poetry itself: 
poetry self update
```

## Release Process

This project is set up to publish to [PyPI](https://pypi.org/) from GitHub Actions.

Thanks to the dynamic versioning plugin and `publish.yml` workflow, you can
simply create tagged releases on GitHub and the tag will trigger a release
build, which then uploads it to PyPI.

For this to work you will need to have a PyPI account and authorize your
repository to publish to PyPI. The simplest way to do that is on
[the publishing settings page](https://pypi.org/manage/account/publishing/).
Configure "Trusted Publisher Management" and register your GitHub repo as
a new "pending" trusted publisher, entering the project name, repo owner,
repo name, and `publish.yml` as the workflow name.

* * *

*This project was built from
[simple-modern-poetry](https://github.com/jlevy/simple-modern-poetry).*