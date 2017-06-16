FROM microsoft/nanoserver

ENV MULTICHAIN_VERSION 1.0-beta-2

SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop';"]

ADD http://www.multichain.com/download/multichain-windows-${MULTICHAIN_VERSION}.zip C:/Users/ContainerAdministrator/AppData/Local/Temp

RUN Expand-Archive ${Env:TEMP}/multichain-windows-${Env:MULTICHAIN_VERSION}.zip 'C:\Program Files\MultiChain'; \
    setx Path ($Env:Path + ';C:\Program Files\MultiChain') /M; \
    Remove-Item ${Env:TEMP}/multichain-windows-${Env:MULTICHAIN_VERSION}.zip

VOLUME C:/Users/ContainerAdministrator/AppData/Roaming/MultiChain

ENTRYPOINT ["multichaind"]
