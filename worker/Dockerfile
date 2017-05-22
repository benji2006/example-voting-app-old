FROM microsoft/dotnet:1.1.1-sdk

WORKDIR /code

ENV http_proxy http://proxy.am2.hpelabs.net:8080
ADD src/Worker /code/src/Worker

RUN dotnet restore -v minimal src/Worker \
    && dotnet publish -c Release -o "./" "src/Worker/" 

CMD dotnet src/Worker/Worker.dll
