<div align="center">
    <img src="https://raw.githubusercontent.com/zehengl/pip-check-updates/refs/heads/main/logo.png" alt="logo" height="128">
</div>

# refresh-python-dependency

A GitHub action to create a pull request for refreshing the dependency file in your Python repository

## Usage

### Minimal

    - uses: zehengl/refresh-python-dependency@main

It will update the libraries specified in a `requirements.txt` file.

### Custom

For PyPi

    - uses: zehengl/refresh-python-dependency@v0.6.0
      with:
        path: requirements-dev.txt

Or for Conda

    - uses: zehengl/refresh-python-dependency@v0.6.0
      with:
        path: environment.yml

It will update the libraries specified in the file from `path`.

To modify branch name

    - uses: zehengl/refresh-python-dependency@v0.6.0
      with:
        branch: refresh-deps

## Example

    name: pcu
    on:
      push:
        branches: [main]
      schedule:
        - cron: "0 12 * * 1"
    jobs:
      refreshDeps:
        runs-on: ubuntu-latest
        steps:
          - uses: zehengl/refresh-python-dependency@v0.6.0
            with:
              path: requirements-dev.txt

## Credits

- [pip-check-updates](https://pypi.org/project/pip-check-updates/)
