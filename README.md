[![Build and Test](https://github.com/MarcusDunn/maps/actions/workflows/docker-test.yml/badge.svg)](https://github.com/MarcusDunn/maps/actions/workflows/docker-test.yml)

# maps

This is a [VikeLabs](https://www.vikelabs.ca/) project meant for navigating around UVic. It's structured as a
multi-module gradle project with an api server and a web app (in `api` and `app` respectivly). You can find out more
about the details of those modules in their respective `README.md`'s.

## Running

You can run the backend with `gradlew api:run` and the frontend with `gradlew app:run`. This should install dependencies
you do not already have, so it may take a while first time! Sadly, due to issues with halting (darn Turing), we cannot
run both in a single gradle command. `gradlew run` will run the backend `api` and wait for it to end (which it doesn't)
then run the frontend `app`.

## Testing

You can test everything at once with `gradlew test`. Or individual projects with `gradlew app:test`
or `gradlew api:test`

## Building

You can build both projects (producing an optimized app and a jar file) with `gradlew build`. Similar to testing and
running, you can build the individual projects with `gradlew app:build` and `gradlew api:build` 

## Deploying

Two two Dockerfiles (`api.Dockerfile` and `app.Dockerfile`) are tested every push. They run optimized builds and as a result are
the best way to deploy the app in a long running environment.

### Some notes on gradle

You can of cource run everything here *without* gradle, you may want to directly run `npm` commands for example. I would
recommend against it as there is a carfully curated dependancy graph for tasks with gradle whereas for npm you are on your
own. As a result of this if any mentioned gradle commands fail for any reason beyond broken code, that is a bug and should be filed 
as such
