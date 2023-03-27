<div align="center">
    <img src="https://cdn2.iconfinder.com/data/icons/flat-jewels-icon-set/512/0000_Refresh.png" alt="logo" height="128">
</div>

# refresh-python-dependency

A GitHub action to create a pull request for refreshing the dependency file in your Python repository

## Usage

### Minimal

    - uses: zehengl/refresh-python-dependency@main

It will update the libraries specified a `requirements.txt` file.

### Custom

For PyPi

    - uses: zehengl/refresh-python-dependency@v0.2.0
      with:
        path: requirements-dev.txt

Or for Conda

    - uses: zehengl/refresh-python-dependency@v0.2.0
      with:
        path: environment.yml

It will update the libraries specified in the file from `path`.

Or with an extra dependency file

    - uses: zehengl/refresh-python-dependency@v0.2.0
      with:
        path: requirements1.txt
        extra_path: requirements2.txt

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
          - uses: zehengl/refresh-python-dependency@v0.2.0
            with:
              path: requirements-dev.txt

## Credits

- [Icon](https://www.iconfinder.com/icons/171269/refresh_icon) by PixelKit
- [pip-check-updates](https://pypi.org/project/pip-check-updates/)
