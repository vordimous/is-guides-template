# Welcome to the contributing guide

Thank you for investing your time in contributing to this project!

In this guide you will get an overview of the structure for this repository and where the best places to make modifications

## Getting started

This project revolves around the main application setup in the root [docker-compose.yml](docker-compose.yml) file. This is where the primary assets are managed.

Any premilinary setup or manual execution scripts can be found int he [bootstrap](bootstrap) directory. Here you can find individual compose scripts to perform necessary tasks. All of the task that need to happen on an inital setup can be found in the `docker-compose.yml` in this directory.

Additional apps that need to be started can be found in the [webapps](webapps) directory. Much like the bootstrap setup each set of webapps have a seprate compose but all can be started using the `docker-compose.yml` file.

## Repo Structure

- The primary infrastructure is in the root [docker-compose.yml](docker-compose.yml) file
- `bootstrap` is a place for pulling external resources and running scripts for setup or modification
- `components` holds static assets that will be mounted into correstpondind directories
- `configs` holds the text files that would potentually be modified based on the guides setup needs
- `guides` is where any instructions should live. Any demos, samples, scenarios, and lab kits should have a set of instructions to help guide the consumer
- `webapps` holds any binaries or project files for deploying supportive webapps

## Making Changes

### Bootstrapping

It is always prefered to download additional assets from their source instead of commiting a specific version to this repository. As you can see we download the mysql jar in the [components.yml](bootstrap/components.yml) file so that we can keep this repository clean. The version and source of the included jar is clear.

### Static assets

Static assets that are compiled locally or don't have a public source can be added manually to the correspoding directory. Updating with `.gitignore` file with a `!**/<guide-name>` will ensure that the asset gets committed to the repo.

### Commit your update

Create a branch for your new content and name it with the guide pupose (demos, samples, scenarios, and lab kits) and name ex: `labkit/saml2`. This will allow for multiple different setups to exists in the repository and for updates to be made to the main branch. Branches will rebase back onto main if they want any new changes. Additionally update the db data volume name in [docker-compose.yaml](docker-compose.yml) with the guide name `<guide-name>-datavolume`.

### Pull Request

Most additions will stay in there own branch but if any content is added that does not break or change the base functionality it can be submitted to add to the main branch.
