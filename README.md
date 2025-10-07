# Animal Shelter Project

This is a Python Flask Demo project. It uses an in memory "database"
to manage animals. 

It is a dockerized environment, the image does not use any env variable, 
the exposed port is 5000.

## Usage

Build the image

`docker build -t <your tag> .`

Run the image

`docker run -p <your host port>:5000`

Access the API, example:

`curl http://localhost:<your host port>/api/animals`

## Development

A Docker compose development environment is configured with watch mode to 
develop on your Host but within a Docker container.

Start the development environment:

`docker compose watch`

### Linter

A Pylint linter is configured for this project.

Running while the dev environment is running (don't miss the dot at the end):

`docker compose exec app python -m pylint .`

Running it on an already built image:

`docker run <image tag> python -m pylint .`

### Tests

API tests are created in the `./tests` directory. Pytest is used for testing.

Run the tests while the dev environment is running:

`docker compose exec app python -m pytest tests`

Run the tests on a built image:

`docker run <image tag> python -m pytest tests`
