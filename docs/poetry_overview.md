# Poetry

Poetry is a package manager for Python that supports virtual environments. Poetry encourages creating one virtual environment for each project. The depencencies and requirements are then stored within the project directory in the `poetry.lock` and `pyproject.toml` files.

## Initialising a Poetry Environment

A new poetry can be initialised in an existing directory by first navigating to the directory then using the `poetry init` function.

```
cd project-directory
poetry init
```

This will create `poetry.lock` and `pyproject.toml` files in the directory.

## Installing Packages

Poetry packages are install using the `poetry add` function. For example.

```
$ poetry add package-name
```

Packages are installed to poetries `cache` directory. The directory path can be found using the `poetry env info --path` function.

## Removing Packages

To remove a package, use the following function:

```
$ poetry remove package-name
```

## Removing a Virtual Environment

Poetry environments can be removed from within the project directory using the following comman:

```
$ poetry env remove <environmentname>
```

Note that the poetry virtual environment name is usually not the name of the project or project directory. To find the name of the virtual environment use the `poetry env info --path` function. This will give you the path to the virtual environment. The final directory in the path is the virtual environment name.
