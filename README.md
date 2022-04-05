# pants_test

trying to create a pants repo that uses namespace packages for "acme_corp"

here is the projec tree:

├── pants
├── pants.toml
└── python_projects
    └── acme_corp
        ├── app1
        │   ├── BUILD
        │   ├── pyproject.toml
        │   └── src
        │       └── acme_corp
        │           └── app1
        │               ├── app1_module.py
        │               └── __init__.py
        └── lib1
            ├── BUILD
            ├── pyproject.toml
            └── src
                └── acme_corp
                    └── lib1
                        ├── __init__.py
                        └── lib1_module.py
