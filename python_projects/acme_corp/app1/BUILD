python_sources(
    # name='app1',
    # dependencies=['python_projects/acme_corp/lib1']
)

pex_binary(
  name="app1_pex",
  entry_point="acme_corp.app1.app1_module:app1_func1",
)

# python_distribution(
#     name="great",
#     dependencies=[
#         ":app1",
#         "python_projects/acme_corp/lib1",
#     ],
#     sdist=True,
#     provides=python_artifact(
#         name="acme_corp.app1",
#         version="0.0.0",
#     ),
# )

