FROM microsoft/dotnet:2.1-sdk AS Builder

WORKDIR /WebApp
COPY WebApp /WebApp

RUN dotnet restore BuildMultistage.csproj
RUN dotnet publish --configuration Release --output ./app

FROM microsoft/dotnet:2.1-aspnetcore-runtime

LABEL Maintainer "frank@pommerening-online.de"

ENV ASPNETCORE_URLS http://0.0.0.0:5000
EXPOSE 5000
WORKDIR /app

ENV Refreshed_At 2018-10-12
COPY --from=Builder /WebApp/app/* ./

ENTRYPOINT [ "dotnet","BuildMultistage.dll" ]