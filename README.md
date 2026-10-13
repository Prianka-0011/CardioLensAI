CardioLensAI/
├── backend/
│   └── CardioLens.Api/
├── frontend/
│   └── cardiolens-ui/
├── ai-service/
│   ├── app/
│   ├── models/
│   └── requirements.txt
├── data/
│   ├── raw/
│   └── processed/
└── docker-compose.yml

dotnet new sln -n CardioLensAI

# API
dotnet new webapi -n CardioLensAI.API -o src/CardioLensAI.Backend/CardioLensAI.API

# Domain
dotnet new classlib -n CardioLensAI.Domain -o src/CardioLensAI.Backend/CardioLensAI.Domain
# Application

# Add To The Soluation
dotnet sln CardioLensAI.slnx add src/CardioLensAI.Backend/CardioLensAI.API/CardioLensAI.API.csproj

dotnet sln CardioLensAI.slnx add src/CardioLensAI.Backend/CardioLensAI.Domain/CardioLensAI.Domain.csproj

dotnet sln CardioLensAI.slnx add src/CardioLensAI.Backend/CardioLensAI.Application/CardioLensAI.Application.csproj

dotnet sln CardioLensAI.slnx add src/CardioLensAI.Backend/CardioLensAI.Infrastructure/CardioLensAI.Infrastructure.csproj

# Build The Whole Soluation
dotnet build CardioLensAI.slnx