python_sources()

pex_binary(
    name="app1_pex",
    entry_point="app1_module.py:app1_func1",
    dependencies=[
        'python_projects/acme_corp/lib1/src/acme_corp/lib1',
    ],
)

python_distribution(
    name="app1_dist",
    dependencies=[
        'python_projects/acme_corp/app1/src/acme_corp/app1',
        'python_projects/acme_corp/lib1/src/acme_corp/lib1',
    ],
    sdist=True,
    provides=python_artifact(
        name="acme_corp.app1",
        version="0.0.0",
    ),
)
