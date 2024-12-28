# filament-schema
draft Pkl schema used by Galaxy's Filament project

Dockerfile included for ease and consistency of development. Dev workflow is like this:

From the main directory:
```
docker build -t filament-schema:dev .
docker run --rm -v .:/home/dev -it filament-schema:dev
```

This should build an image for you and then start an interactive session with any local files
available. From here you should be able to do things like `pkl -v` and get meaningful output,
as a test.
