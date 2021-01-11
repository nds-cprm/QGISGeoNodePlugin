# qgis_geonode

A QGIS plugin that provides integration with GeoNode

## Development

This plugin uses [poetry], [typer] and [black].

- Fork the code repository
- Clone your fork locally
- Install poetry
- Install the plugin dependencies into a new virtual env with
  
  ```
  cd qgis_geonode
  poetry install
  ```

- The plugin comes with a `pluginadmin.py` python module, which provides a nice CLI 
  with commands useful for development:
  
  ```
  poetry run python pluginadmin.py --help
  poetry run python pluginadmin.py install
  poetry run python pluginadmin.py install-qgis-into-venv
  ```
  
- When testing out the plugin locally you just need to call 
  `poetry run python pluginadmin.py install`. Alternatively, the [plugin reloader] QGIS 
  plugin can be used as a means to install and reload the plugin. The functionality 
  that allows re-running the poetry install command is currently in a [proposed] state, 
  so you may install plugin reloader directly from the github fork mentioned in the 
  above pull request
  
- Remember to run `poetry run black src/qgis_geonode` before submitting PRs. Otherwise 
  the CI pipeline may fail.
  

## Running tests

Tests are made with [pytest] and [pytest-qt]. They can be ran with:

```
# optionally create a QGIS_PREFIX_PATH env variable, if your QGIS is self-compiled
poetry run pytest
```


[poetry]: https://python-poetry.org/
[typer]: https://typer.tiangolo.com/
[black]: https://github.com/psf/black
[plugin reloader]: https://github.com/borysiasty/plugin_reloader
[proposed]: https://github.com/borysiasty/plugin_reloader/pull/22
[pytest]: https://docs.pytest.org/en/latest/
[pytest-qt]: https://github.com/pytest-dev/pytest-qt
