FROM mcr.microsoft.com/dotnet/aspnet:8.0
WORKDIR /app

# Copia todos os DLLs e arquivos publicados para /app
COPY WebApp_MinApi/ ./

# Variável de ambiente para escutar em todas as interfaces
ENV ASPNETCORE_URLS=http://+:5000

# Comando para iniciar a API
ENTRYPOINT ["dotnet", "WebApi_minimalApi.dll"]
