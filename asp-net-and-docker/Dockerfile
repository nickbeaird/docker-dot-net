FROM mcr.microsoft.com/dotnet/core/aspnet AS build-env

WORKDIR /app

COPY ./publish .

ENTRYPOINT ["dotnet", "asp-net-and-docker.dll"]