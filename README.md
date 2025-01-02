# filament-schema
draft Pkl schema to potentially be used by Galaxy's Filament project

## Structure
The project structure is something like this:

```ini
.
+--Dockerfile				# a container for development/ local testing
+--src
|  +--MyModule.pkl 			# an importable module, defines classes etc.
+--examples
|  +--MyModule.pkl 			# examples building config using MyModule
+--tests
|  +--MyModule.pkl			# tests of MyModule and its examples
|  +--MyModule.pkl-expected.pcf		# snapshot of MyModule examples
```

## Development
A Dockerfile included for ease and consistency of development. Dev workflow is like this:

From the main directory:

```
docker build -t filament-schema:dev .
docker run --rm -v .:/home/dev -it filament-schema:dev
```

This should build an image for you and then start an interactive session with any local files
available under /home/dev. From here you should be able to do things like `pkl -v` and get 
meaningful output, as a test the container is working. The goal is to allow a dev to use this 
container to run tests like `pkl test tests/Oranism.pkl` before pushing their changes, etc.

*NOTE:* There is a VS Code Extension available. See [here](https://pkl-lang.org/vscode/current/installation.html).
