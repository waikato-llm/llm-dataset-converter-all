PyPi
====

Preparation:

* increment version in `setup.py`
* add new changelog section in `CHANGES.rst`
* align `DESCRIPTION.rst` with `README.md`  
* commit/push all changes

Commands for releasing on pypi.org (requires twine >= 1.8.0):

```
find -name "*~" -delete
rm dist/*
python3 setup.py clean
python3 setup.py sdist
twine upload dist/*
```


Github
======

Steps:

* start new release (version: `vX.Y.Z`)
* enter release notes, i.e., significant changes since last release
* upload `llm_dataset_converter_all-X.Y.Z.tar.gz` previously generated with `setup.py`
* publish


Docker
======

* create copy of eg [docker/0.0.1](docker/0.0.1) and rename it to just released version
* link to new version from [docker/README.md](docker/README.md)
* update version in `bash.bashrc`
* update version of llm-dataset-converter-all library to just released one
* push out to in-house registry and docker hub
