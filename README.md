# Splitfy - Microservices

![Splitfy](logo.png)

The objetive of this application is to help people manage their personal finances keeping track of expenses and controlling agains their monthly budget.

## Prerequisites

* [Python 3](https://www.python.org/downloads/)
* [Docker](https://www.docker.com/)
* [Docker Compose](https://docs.docker.com/compose/)

## Overview

### Repository structure
When developing Splitfy services we organize the repo structure having a dedicated repo for each component and a separate one for the docker compose file. 

### Components

![Components](diagram.png)

#### Splitfy Frontend

Responsible for organinzing how the end user will visualize our application in order to manage their finances. It will exchange information with the Expenses backend to save and retrieve information through a REST API.

#### Splitfy Backend

Responsible for storing and managing expenses information and exposing REST API that can be consumed by other services. This service is using SQLite database to persist expense information.

#### Open Exchange Rates

Is an external service exposing HTTP REST API to be used to get USD/BRL exchange rates when saving or updating expenses.

## Running examples

Quickest way to try out Splitfy application is to:

1. Clone components repos (`puc-rio-frontend` and `puc-rio-backend`) and compose repo into the same folder
1. Create `.env` file with variable `OPEN_FOREX_KEY` containing the Open Exchange Rates API `App ID`
1. Run `docker-compose up`

Wait until all services are up and Splitfy front-end will be available on port 3000 and backend on port 5000. You can play with the application from there.

