FROM microsoft/dotnet:1.1.1-sdk

COPY ./Api.csproj /app/
COPY ./NuGet.Config /app/
WORKDIR /app/
RUN ["dotnet","restore"]
ADD . /app/
RUN ["dotnet","build"]

EXPOSE 5001

#For Production Image
#RUN dotnet publish -c Debug -o out
#ENTRYPOINT ["dotnet", "out/IdentityServerWithAspNetIdentity.dll"]

CMD ["dotnet", "watch", "run"]
