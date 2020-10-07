
# Use the official microsoft image found -> https://hub.docker.com/_/microsoft-mssql-server
FROM mcr.microsoft.com/mssql/server:2017-latest

# Define environment variables
ENV ACCEPT_EULA=Y
ENV SA_PASSWORD=MySoVery3tr045Pass3!o79

# Download test data which we will upload to a table and query
ADD complaints.csv /home/sql/dataset/