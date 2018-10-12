FROM microsoft/dotnet:2.1-sdk
LABEL Maintainer "frank@pommerening-online.de"

ENV ASPNETCORE_URLS http://0.0.0.0:5000
EXPOSE 5000
WORKDIR /WebApp

COPY WebApp /WebApp
RUN cd /WebApp && dotnet restore && dotnet build
ENV Refreshed_At 2018-10-12

ENTRYPOINT [ "dotnet","run" ]