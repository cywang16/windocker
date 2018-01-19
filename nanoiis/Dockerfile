
FROM microsoft/iis
# FROM microsoft/iis:nanoserver

SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'Continue'; $verbosePreference='Continue';"]

WORKDIR prep
ADD "http://go.microsoft.com/fwlink/?LinkId=829373" ".\iisadmin.exe"

RUN start-process -Filepath .\iisadmin.exe -ArgumentList  @('/install', '/q', '/norestart') -Wait

EXPOSE 80 55539

# ADD content/ /site