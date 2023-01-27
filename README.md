# Dotnet-service-template
From https://medium.com/@iqan/containerizing-a-net-core-service-with-docker-cd9bb42fa6b with little modifications

If you want to build without Docker run in csproj folder

```console
dotnet restore
dotnet build
```
and for running

```console
dotnet run
```

More dotnet commands https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet

You need to install docker desctop and Linux subsystem for Windows (if you are using Windows).

Then start command line as Administrator in the same folder where your docker file is. Then run

```console
docker build -t mydocker .
```

There should be a new image. List images

```console
docker images
```

If you want to run image

```console
docker run mydocker
```
