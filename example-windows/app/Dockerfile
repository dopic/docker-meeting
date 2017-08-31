#Stage 1
FROM microsoft/aspnetcore-build:2.0 as appbuilder

WORKDIR /source

COPY *.csproj .

RUN dotnet restore

COPY . .

RUN dotnet publish --output /output/ --configuration Release

#Stage 2
FROM microsoft/aspnetcore:2.0

WORKDIR /app

COPY --from=appbuilder /output .

ENTRYPOINT ["dotnet", "app.dll"]


