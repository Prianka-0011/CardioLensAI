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

# Configure Application to Run on Debug mode
.vscode/launch.json
.vscode/tasks.json

# Add Releted Project Referance
dotnet add src/CardioLensAI.Backend/CardioLensAI.Application/CardioLensAI.Application.csproj reference src/CardioLensAI.Backend/CardioLensAI.Domain/CardioLensAI.Domain.csproj

dotnet add src/CardioLensAI.Backend/CardioLensAI.Infrastructure/CardioLensAI.Infrastructure.csproj reference src/CardioLensAI.Backend/CardioLensAI.Application/CardioLensAI.Application.csproj

dotnet add src/CardioLensAI.Backend/CardioLensAI.Infrastructure/CardioLensAI.Infrastructure.csproj reference src/CardioLensAI.Backend/CardioLensAI.Domain/CardioLensAI.Domain.csproj

dotnet add src/CardioLensAI.Backend/CardioLensAI.API/CardioLensAI.API.csproj reference src/CardioLensAI.Backend/CardioLensAI.Application/CardioLensAI.Application.csproj

dotnet add src/CardioLensAI.Backend/CardioLensAI.API/CardioLensAI.API.csproj reference src/CardioLensAI.Backend/CardioLensAI.Infrastructure/CardioLensAI.Infrastructure.csproj

# Verify Each Project Reference List
dotnet add src/CardioLensAI.Backend/CardioLensAI.Application/CardioLensAI.Application.csproj reference src/CardioLensAI.Backend/CardioLensAI.Domain/CardioLensAI.Domain.csproj

dotnet add src/CardioLensAI.Backend/CardioLensAI.Infrastructure/CardioLensAI.Infrastructure.csproj reference src/CardioLensAI.Backend/CardioLensAI.Application/CardioLensAI.Application.csproj

dotnet add src/CardioLensAI.Backend/CardioLensAI.Infrastructure/CardioLensAI.Infrastructure.csproj reference src/CardioLensAI.Backend/CardioLensAI.Domain/CardioLensAI.Domain.csproj

dotnet add src/CardioLensAI.Backend/CardioLensAI.API/CardioLensAI.API.csproj reference src/CardioLensAI.Backend/CardioLensAI.Application/CardioLensAI.Application.csproj

dotnet add src/CardioLensAI.Backend/CardioLensAI.API/CardioLensAI.API.csproj reference src/CardioLensAI.Backend/CardioLensAI.Infrastructure/CardioLensAI.Infrastructure.csproj

# SetUp All The Require Package
------------

# Middleware
Exception Handle //done
Middleware order
app.UseGlobalExceptionHandler();   // 1️⃣ Catch everything
app.UseHttpsRedirection();         // 2️⃣ Security
app.UseAuthentication();           // 3️⃣ Auth
app.UseAuthorization();            // 4️⃣ Permissions
app.MapControllers();  