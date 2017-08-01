FROM microsoft/dotnet:1.1.1-sdk

RUN apt-get update
RUN apt-get -qq update
RUN apt-get install -y nodejs npm
RUN update-alternatives --install /usr/bin/node node /usr/bin/nodejs 10
RUN npm install -g bower

COPY ./MvcClient.csproj /app/
COPY ./NuGet.Config /app/
WORKDIR /app/
RUN ["dotnet","restore"]
ADD . /app/
RUN ["dotnet","build"]

EXPOSE 5002

#For Production Image
#RUN dotnet publish -c Debug -o out
#ENTRYPOINT ["dotnet", "out/IdentityServerWithAspNetIdentity.dll"]

CMD ["dotnet", "watch", "run"]
