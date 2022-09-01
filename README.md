# refresh-python-dependency

A GitHub action to create a pull request for refreshing the dependency file in your Python repository

## Usage

### Minimal

    - uses: zehengl/refresh-python-dependency@v0.1.2

It will update the libraries specified a `requirements.txt` file.

### Custom

For PyPi

    - uses: zehengl/refresh-python-dependency@v0.1.2
      with:
        path: requirements-dev.txt

Or for Conda

    - uses: zehengl/refresh-python-dependency@v0.1.2
      with:
        path: environment.yml

It will update the libraries specified in the file from `path`.
