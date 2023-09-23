FROM mcr.microsoft.com/dotnet/sdk:6.0 as builder
COPY ./ApiDockerSample /app
WORKDIR /app

RUN dotnet publish -c Release

FROM mcr.microsoft.com/dotnet/aspnet:6.0

COPY --from=builder /app/bin/Release/net6.0/publish/ /app
WORKDIR /app
ENTRYPOINT [ "dotnet", "ApiDockerSample.dll" ]
