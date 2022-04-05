python_sources(name='lib1')

python_distribution(
    name="lib1dist",
    dependencies=[
        ':lib1',
    ],
    sdist=True,
    provides=python_artifact(
        name="lib1",
        version="0.0.0",
    ),
)