
FROM microsoft/windowsservercore

# install python
RUN powershell.exe -Command \
    $ErrorActionPreference = 'Stop'; \
    wget https://www.python.org/ftp/python/3.6.4/python-3.6.4-amd64.exe -OutFile c:\python-setup.exe ; \
    Start-Process c:\python-setup.exe -ArgumentList '/quiet InstallAllUsers=1 PrependPath=1' -Wait ; \
    Remove-Item c:\python-setup.exe -Force

EXPOSE 5000 8000
WORKDIR c:\\setup
ADD requirements.txt .
RUN dir
RUN pip install -r requirements.txt

