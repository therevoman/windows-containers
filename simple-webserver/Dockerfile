FROM mcr.microsoft.com/windows/server:ltsc2022 AS build-env
WORKDIR /app

COPY webserver.ps1 ./

FROM mcr.microsoft.com/windows/server:ltsc2022
#FROM mcr.microsoft.com/powershell
# escape=` (backtick)

WORKDIR /app
COPY --from=build-env /app/webserver.ps1 .

EXPOSE 80

ENTRYPOINT ["powershell", "-File", "/app/webserver.ps1"]

