# pants_test

trying to create a pants repo that uses namespace packages for "acme_corp"

here is the project tree:

```
├── pants
├── pants.toml
├── python_projects
│   └── acme_corp
│       ├── app1
│       │   ├── pyproject.toml
│       │   └── src
│       │       └── acme_corp
│       │           └── app1
│       │               ├── app1_module1.py
│       │               ├── app1_module2.py
│       │               ├── BUILD
│       │               └── __init__.py
│       └── lib1
│           ├── pyproject.toml
│           └── src
│               └── acme_corp
│                   └── lib1
│                       ├── BUILD
│                       ├── __init__.py
│                       ├── lib1_module1.py
│                       └── lib1_module2.py
```

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
