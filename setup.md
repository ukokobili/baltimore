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
    image: postgres:13
    environment:
      - POSTGRES_USER=jkop
      - POSTGRES_PASSWORD=root
      - POSTGRES_DB=crimeDB
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
Open the window terminal and run *docker-compose up* to run the yaml to create both postgres database and pgAdmin application.

* Enter *localhost:8080* on the browser and input the pgAdmin useranme/email and password. 

### 3. Download & Load Dataset
The dataset is from https://data.world/data-society/city-of-baltimore-crime-data

* Open jupyter notebook from the Baltimore folder

* Load and transform the dataset before ingesting into the database

* Ingest the transformed data into Postgres database. Ingestion code can be found in the upload data notebook.

### 4. SQL Query 
Open the PGAdmin with localhost:8080 in the broswer.

* Right click on *Servers* to register a new server and under *General*, Name, enter localhost

* Go to *Connection* and under Host name/address enter pg-db, and the port username and password of the databse afterwads to be able to access the database to run the SQL queries.



```
docker run -it \
  -e POSTGRES_USER="jacob" \
  -e POSTGRES_PASSWORD="root" \
  -e POSTGRES_DB="crime_db" \
  -v /c:/Users/DELL/Documents/new_projects/baltimore/baltimore_crime_data:/var/lib/postgresql/data  \
  -p 5432:5432 \
  postgres:13
  ```


