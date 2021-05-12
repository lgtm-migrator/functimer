# functimer

A decorator/wrapper package to time a given function.

[![PyPI version](https://badge.fury.io/py/functimer.svg)](https://badge.fury.io/py/functimer)
[![Build Status](https://travis-ci.com/EJEmmett/functimer.svg?branch=master)](https://travis-ci.com/EJEmmett/functimer)
[![codecov](https://codecov.io/gh/EJEmmett/functimer/branch/master/graph/badge.svg?token=L0UMBK8AD4)](https://codecov.io/gh/EJEmmett/functimer)
[![Language grade: Python](https://img.shields.io/lgtm/grade/python/g/EJEmmett/functimer.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/EJEmmett/functimer/context:python)
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/857af82e6ff14a68b5bf0866e0b44d30)](https://www.codacy.com/gh/EJEmmett/functimer/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=EJEmmett/functimer&amp;utm_campaign=Badge_Grade)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

---
## Installation
- PYPI:
    ```shell
        pip install functimer
    ```

- Manual:
    ```shell
        poetry build
        pip install dist/*.whl
    ```


How to install [Poetry](https://python-poetry.org/docs/#installation).

## Quick Example
### Comprehensive Examples in `examples`

- Python
  ```py
      @timed(unit=Unit.second, number=1)
      def timed_sleep(seconds):
          sleep(seconds)

      runtime = timed_sleep(1)
      "1.00 s"
  ```

- Command Line
  ```shell
    $ python -m functimer "sum([1, 2, 3])"
    Average runtime of 10,000 executions: 0.15 µs

    $ python -m functimer "sum([1, 2, 3])" --return True
    Average runtime of 10,000 executions: 0.15 µs
    sum([1, 2, 3]) -> 6

    $ python -m functimer "(lambda x: x+x)(10)" --return true
    Average runtime of 10,000 executions: 0.14 µs
    (lambda x: x+x)(10) -> 20

    $ python -m functimer "functimer.util.get_unit('1.00 s')" --return true
    Average runtime of 10,000 executions: 0.50 µs
    functimer.util.get_unit('1.00 s') -> Unit.second
  ```

### Tests
Run `tox` in the root directory of the repo.

### License
MIT
