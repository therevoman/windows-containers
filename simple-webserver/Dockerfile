FROM mcr.microsoft.com/windows/servercore:ltsc2022 AS build-env
WORKDIR /app

COPY webserver.ps1 ./
ADD https://github.com/microsoft/windows-container-tools/releases/download/v1.2/LogMonitor.exe ./

FROM mcr.microsoft.com/windows/servercore:ltsc2022
#FROM mcr.microsoft.com/powershell
# escape=` (backtick)

WORKDIR /app
COPY --from=build-env /app/webserver.ps1 .
COPY --from=build-env /app/LogMonitor.exe .

EXPOSE 8080

#USER 1001

SHELL ["C:\\LogMonitor\\LogMonitor.exe", "cmd", "/S", "/C"]
CMD ["powershell", "-File", "/app/webserver.ps1"]

