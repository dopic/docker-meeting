FROM microsoft/windowsservercore
RUN powershell Invoke-WebRequest http://nginx.org/download/nginx-1.13.3.zip -UseBasicParsing -OutFile c:\\nginx.zip
RUN powershell Expand-Archive c:\\nginx.zip -Dest c:\\nginx
WORKDIR c:\\nginx\\nginx-1.13.3

COPY nginx.conf c:\\nginx\\nginx-1.13.3\\conf\\nginx.conf

EXPOSE 80


ENTRYPOINT powershell .\\nginx.exe
