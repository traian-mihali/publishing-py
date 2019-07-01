## Publishing a package on pypi.org

1. Install 'setuptools', 'wheel' and 'twine' globally:

```
> pip install setuptools wheel twine
```

2. Add a setup.py file in the root of your project:

```python
import setuptools
from pathlib import Path

setuptools.setup(
    name="random-py",
    version=1.0,
    long_description=Path("README.txt").read_text(),
    packages=setuptools.find_packages(exclude=['README.md', 'data'])
)
```

3. Add a README.md file
4. Add a LICENSE file
5. Generate a distribution package:

```
root\of\your\project> python setup.py sdist bdist_wheel
```

6. Upload the dist using twine:

```
root\of\your\project> twine upload dist/*
```
