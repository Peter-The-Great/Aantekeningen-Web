Bekijk de volgende code:
```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
WORKDIR /source
COPY *.csproj .
RUN dotnet restore
COPY . .
RUN dotnet publish -c Release -o /app --no-restore

FROM mcr.microsoft.com/dotnet/runtime:7.0
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "dotnetapp.dll"]


En de volgende kortere code:
FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
WORKDIR /source
COPY *.csproj .
RUN dotnet restore
COPY . .

RUN dotnet publish -c Release -o /app --no-restore
WORKDIR /app
ENTRYPOINT ["dotnet", "dotnetapp.dll"]
```

De eerste code is beter omdat deze gebruik maakt van **multi-stage builds** [1](https://www.baeldung.com/ops/docker-dockerfile-docker-compose). Dit betekent dat de Dockerfile twee afzonderlijke build-stadia heeft: één voor het bouwen van de applicatie en één voor het uitvoeren van de applicatie [1](https://www.baeldung.com/ops/docker-dockerfile-docker-compose).

In het eerste stadium wordt de applicatie gebouwd en wordt de output naar een tijdelijke container gekopieerd [1](https://www.baeldung.com/ops/docker-dockerfile-docker-compose). In het tweede stadium wordt de runtime-container gedefinieerd en wordt de output van het eerste stadium gekopieerd naar de runtime-container [1](https://www.baeldung.com/ops/docker-dockerfile-docker-compose). Dit zorgt ervoor dat de runtime-container alleen de benodigde bestanden bevat en niet de build-tools, waardoor de container kleiner en veiliger wordt [1](https://www.baeldung.com/ops/docker-dockerfile-docker-compose).

De tweede code heeft slechts één stadium en bevat zowel de build-tools als de runtime in dezelfde container [2](https://allinfo.space/2021/09/01/wat-is-het-verschil-tussen-kopie-en-add-in-dockerfiles/). Dit kan leiden tot een grotere containergrootte en een minder veilige container [2](https://allinfo.space/2021/09/01/wat-is-het-verschil-tussen-kopie-en-add-in-dockerfiles/).