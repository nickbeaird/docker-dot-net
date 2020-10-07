# Docker and MSSQL on Mac

## Links

- [Primary](https://medium.com/@euedofia/dockerize-microsoft-sql-server-on-macos-a8d40f8b1e66)

## Comnmands

1. Run DB as root with the following.
    ```shell
    # Pull the docker container
    docker pull mcr.microsoft.com/mssql/server:2017-latest

    # Run the container
    docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=pDFNVcpTfYhZxd^sYHY6ot8My" -p 1433:1433 --name dev-mssql-server mcr.microsoft.com/mssql/server:2017-latest
    ```

1. Run the docker container with the following.
   - Server: `localhost,60666` (the comma is important)
   - Login Type: `SQL Authentication`
   - User: `sa`
   - Password: `pDFNVcpTfYhZxd^sYHY6ot8My`
