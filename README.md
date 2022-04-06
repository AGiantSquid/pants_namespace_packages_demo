# Pants Namespace Packages Demo

This demonstrates how to set up a python monorepo that uses namespace packages.

The goal is to create a set of packages for a fake company "acme_corp".
All packages will live in the namespace `acme_corp`. (e.g. `from acme_corp.lib1 import lib1_module1`)
A user should be able to install a subset of the packages in the namespace, or all of them if they so choose.

# Overview

The project tree is shown below.

Notice that the python files for `app1` are nested in the following directory: `src/acme_corp/app1`. Pants will automatically look for project roots when it sees `src/` in the path. This is what will allow `app1` to be imported from the `acme_corp` namespace.


```
├── pants
├── pants.toml
└── python_projects
    └── acme_corp
        ├── app1
        │   ├── pyproject.toml
        │   └── src
        │       └── acme_corp
        │           └── app1
        │               ├── app1_module1.py
        │               ├── app1_module2.py
        │               ├── BUILD
        │               └── __init__.py
        └── lib1
            ├── pyproject.toml
            ├── src
            │   └── acme_corp
            │       └── lib1
            │           ├── BUILD
            │           ├── __init__.py
            │           ├── lib1_module1.py
            │           └── lib1_module2.py
            └── tests
                └── unit
                    ├── BUILD
                    ├── lib1_module1_test.py
                    └── lib1_module2_test.py
```

# Useful commands

To run `lib1` pex:
```
./pants run python_projects/acme_corp/lib1/src/acme_corp/lib1:lib1_pex
```

To run `app1` pex:
```
./pants run python_projects/acme_corp/app1/src/acme_corp/app1:app1_pex
```

To build `lib1` sdist:
```
./pants package python_projects/acme_corp/lib1/src/acme_corp/lib1:lib1_dist
```

To build `app1` sdist:
```
./pants package python_projects/acme_corp/app1/src/acme_corp/app1:app1_dist
```

To run tests:
```
./pants test ::
```

# Medium Article explaining development

https://medium.com/@ashley.e.shultz/python-monorepo-with-pants-74f51fbfa6b6
