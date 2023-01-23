FROM mcr.microsoft.com/dotnet/sdk:6.0 AS base
WORKDIR /app

FROM microsoft/dotnet:6.0-sdk-stretch AS build
WORKDIR /src
COPY ["MyDocker/MyDocker.csproj", "MyDocker/"]
RUN dotnet restore "MyDocker/MyDocker.csproj"
COPY . .
WORKDIR "/src/MyDocker"
RUN dotnet build "MyDocker.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "MyDocker.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "MyDocker.dll"]