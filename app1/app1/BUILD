python_sources(name='app1')

python_distribution(
    name="great",
    dependencies=[
        ":app1",
        "lib1/lib1"
    ],
    sdist=True,
    provides=python_artifact(
        name="mydist",
        version="2.21.0",
    ),
)

pex_binary(
  name="pexy",
  entry_point="app1.py:app1func1",
)
