# Docker, Postgres & PGAdmin setup

### 1. Docker Compose
Define and run multi-container applications one file

Set up configurations for environmental variables for running multiple docker postresql and pgadmin images locally

* create two folders:
    * baltimore crime data
    * data pgadmin

* create a docker-compose.yaml file and enter the configuration below:

```
services:
  pg-db:
    image: postgres:15
    environment:
      - POSTGRES_USER=jacob
      - POSTGRES_PASSWORD=admin
      - POSTGRES_DB=baltimore
    volumes:
      - "./baltimore_crime_data:/var/lib/postgresql/data:rw"
    ports:
      - "5432:5432"
  pgadmin:
    image: dpage/pgadmin4
    environment:
      - PGADMIN_DEFAULT_EMAIL=admin@admin.com
      - PGADMIN_DEFAULT_PASSWORD=admin
    volumes:
      - "./data_pgadmin:/var/lib/pgadmin"
    ports:
      - "8080:80"
  ```

### 2. Run Docker Compose
Open the window terminal and run *docker-compose up* to run the yaml to create both postgres database and pgAdmin.

* Enter *localhost:8080* on the browser and input the pgAdmin useranme/email and password. 

### 3. Download & Load Dataset
The dataset is from https://data.world/data-society/city-of-baltimore-crime-data

* Open jupyter notebook from the Baltimore folder
