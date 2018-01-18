#
# Try the following:
# powershell -command Invoke-WebRequest https://www.python.org/ftp/python/3.6.4/python-3.6.4-embed-amd64.zip -outfile pythonsetup.zip
# powershell -command $zip = "pythonsetup.zip"; $dest = "C:\Program Files\Python"; Add-Type -assembly "system.io.compression.filesystem"; [io.compression.zipfile]::ExtractToDirectory("$zip", "$dest")
# Invoke-WebRequest -Uri "https://bootstrap.pypa.io/get-pip.py" -OutFile "C:\get-pip.py"
FROM microsoft/nanoserver

#install py
RUN powershell.exe -Command \
    $ErrorActionPreference = 'Stop'; \
    Invoke-WebRequest https://www.python.org/ftp/python/3.6.4/python-3.6.4-amd64.exe -OutFile c:\python-setup.exe ; \
    Start-Process c:\python-setup.exe -ArgumentList '/quiet InstallAllUsers=1 PrependPath=1' -Wait ;
    # Start-Process c:\python-setup.exe -ArgumentList '/quiet InstallAllUsers=1 PrependPath=1' -Wait ; \
    #    Remove-Item c:\python-setup.exe -Force

EXPOSE 5000 8000
RUN mkdir c:\setup
RUN dir
WORKDIR c:\\setup
# ADD requirements.txt c:\setup\
ADD requirements.txt .
RUN dir
RUN cmd.exe /k
# RUN pip install -r requirements.txt

