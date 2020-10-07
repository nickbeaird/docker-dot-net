# Docker with MSSQL

## Links

- [Primary](https://medium.com/@garry.passarella/using-docker-to-spin-up-development-sql-server-instances-in-minutes-8d05d8d36e84)

## Commands without Dockerfile

1. Get the docker container running locally.

   ```shell
   # Build the instance
   docker build -t mssql1 .

   # List your images by image name
   docker image ls mssql1

   # Run the container. The Default port for msswl is 1433.
   docker run -d -p 60666:1433 mssql1
   ```

1. Open Azure Data Studio and connect to it with the following.

   ```
   Server: localhost,60666
   Login Type: SQL Authentication
   User: sa
   Password: <the password from your Dockerfile>
   ```

1. Create a direcotry on the container

   ```shell
   # Get to the shell of the container
   docker exec -it dev-mssql-server "bash"

   # Make the directory
   mkdir -p /home/sql/dataset
   cd /home/sql/dataset
   ```

1. Download a dataset

   - Navigate to [Consumer Complaints](https://www.consumerfinance.gov/data-research/consumer-complaints/)
   - Download the dataset
   - Unzip the file

1. Copy the file to the container

   - Copy the file to the docker container `docker cp complaints.csv dev-mssql-server:/home/sql/dataset`

## Commands with Dockerfile

1. Build the dockerfile: `docker build -t mssql-mac .`
1. Run the container: `docker run -p 1433:1433 --name test-mssqlmac mssql-mac`
1. Get onto the container:
   - Get the container name: `docker ps`
   - Run the container: `docker run -it CONTAINER_GUID bash`
