# ---------------- Build Stage ----------------
FROM mcr.microsoft.com/dotnet/sdk:10.0 AS build
WORKDIR /src
COPY . .
RUN dotnet restore
RUN dotnet publish -c Debug -o /app/publish

# ----------------  Dev Stage  ----------------
FROM mcr.microsoft.com/dotnet/sdk:10.0
WORKDIR /app
COPY . .
EXPOSE 5000
EXPOSE 5001
CMD ["dotnet", "watch", "run", "--urls", "http://0.0.0.0:5000"]
