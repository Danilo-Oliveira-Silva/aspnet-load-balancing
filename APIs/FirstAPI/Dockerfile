# Dockerfile

FROM mcr.microsoft.com/dotnet/sdk:7.0 AS publish-environment
WORKDIR /app

COPY . ./
RUN dotnet restore
RUN dotnet publish -c Release -o published

FROM mcr.microsoft.com/dotnet/aspnet:7.0
WORKDIR /app
COPY --from=publish-environment /app/published .
ENTRYPOINT ["dotnet", "FirstAPI.dll"]
