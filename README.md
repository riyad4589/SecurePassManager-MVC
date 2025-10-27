<div align="center">

# 🔐 SecurePassManager

**A secure password management application built with ASP.NET Core 8 MVC**

![.NET](https://img.shields.io/badge/.NET-8.0-512BD4?logo=dotnet&logoColor=white)
![C#](https://img.shields.io/badge/C%23-11.0-239120?logo=c-sharp&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL_Server-2022-CC2927?logo=microsoft-sql-server&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green)

[Features](#-features) • [Installation](#-installation) • [Usage](#-usage) • [Security](#-security) • [Contributing](#-contributing)

</div>

---

## 📝 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Technology Stack](#-technology-stack)
- [Architecture](#-architecture)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Usage Guide](#-usage-guide)
- [Security Features](#-security-features)
- [Project Structure](#-project-structure)
- [Screenshots](#-screenshots)
- [Development](#-development)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Overview

**SecurePassManager** is a comprehensive, secure password management web application designed to help users store, encrypt, and manage their passwords safely. Built with ASP.NET Core 8 MVC, it provides enterprise-grade security features including AES-256 encryption, breach detection, and multi-factor authentication capabilities.

### Key Highlights

- 🔒 **Military-Grade Encryption**: AES-256 encryption for password storage
- 🛡️ **Breach Detection**: Integration with Have I Been Pwned API
- 👤 **User Management**: Complete authentication and authorization system
- 📱 **Responsive UI**: Modern, mobile-friendly interface
- 🔍 **Search Functionality**: Quick access to stored credentials
- 🎨 **Service Logos**: Automatic logo detection and display

---

## ✨ Features

### Authentication & Security
- ✅ **User Registration & Login** with email confirmation
- ✅ **Password Reset** functionality
- ✅ **Cookie-based Authentication** with sliding expiration
- ✅ **Role-based Authorization** (Admin, User roles)
- ✅ **Session Management** with auto-logout
- ✅ **CSRF Protection** on all forms
- ✅ **XSS Protection** built-in

### Password Management
- ✅ **Encrypt/Decrypt Passwords** using AES-256
- ✅ **Create, Read, Update, Delete** account credentials
- ✅ **Automatic Logo Generation** via Clearbit API
- ✅ **Search Accounts** by service or username
- ✅ **User Profile** with account statistics
- ✅ **Data Validation** using FluentValidation

### Advanced Features
- ✅ **Have I Been Pwned Integration** for breach detection
- ✅ **Role Management** with ASP.NET Core Identity
- ✅ **Pagination Support** for large datasets
- ✅ **Error Handling** with custom exception management
- ✅ **Activity Logging** for audit trails
- ✅ **Responsive Design** with Bootstrap 5

---

## 🛠️ Technology Stack

### Backend
| Technology | Version | Purpose |
|-----------|---------|---------|
| ASP.NET Core | 8.0 | Web Framework |
| C# | 11.0 | Programming Language |
| Entity Framework Core | 8.0.11 | ORM |
| FluentValidation | 11.11.0 | Data Validation |
| ASP.NET Core Identity | 8.0.11 | Authentication |
| JWT Bearer | 8.0.11 | Token Authentication |

### Database
| Technology | Purpose |
|-----------|---------|
| SQL Server | Primary Database |
| Entity Framework Migrations | Schema Management |

### Frontend
- **Razor Pages** - Server-side rendering
- **Bootstrap 5** - UI Framework
- **jQuery** - JavaScript Library
- **jQuery Validation** - Client-side validation

### External APIs
- **Clearbit Logo API** - Service logo generation
- **Have I Been Pwned API** - Breach detection

---

## 🏗️ Architecture

### MVC Pattern
```
Controllers → Services → Repositories → Database
     ↓           ↓            ↓
    Views → Encryption → Identity
```

### Key Components
- **Controllers**: Handle HTTP requests and responses
- **Services**: Business logic and encryption
- **Repositories**: Data access layer
- **DTOs**: Data transfer objects
- **Validators**: Input validation rules

---

## 📦 Installation

### Prerequisites

Ensure you have the following installed:
- [.NET SDK 8.0](https://dotnet.microsoft.com/download/dotnet/8.0) or later
- [SQL Server](https://www.microsoft.com/sql-server/sql-server-downloads) (Express or higher)
- [Visual Studio 2022](https://visualstudio.microsoft.com/) or [Visual Studio Code](https://code.visualstudio.com/)
- [SQL Server Management Studio](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms) (optional)

### Step-by-Step Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/riyad4589/SecurePassManager-MVC.git
   cd SecurePassManager-MVC
   ```

2. **Navigate to the project directory**
   ```bash
   cd SecurePass
   ```

3. **Restore dependencies**
   ```bash
   dotnet restore
   ```

4. **Update database connection string**
   
   Edit `appsettings.json`:
   ```json
   {
     "ConnectionStrings": {
       "DefaultConnection": "Server=YOUR_SERVER;Database=SecurePassManager;Integrated Security=True;TrustServerCertificate=True;"
     }
   }
   ```

5. **Apply database migrations**
   ```bash
   dotnet ef database update
   ```

6. **Run the application**
   ```bash
   dotnet run
   ```

7. **Access the application**
   
   Open your browser and navigate to:
   ```
   https://localhost:5001
   ```

---

## ⚙️ Configuration

### Database Configuration

Configure your SQL Server connection in `appsettings.json`:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=.\\SQLEXPRESS;Database=SecurePassManager;Trusted_Connection=True;TrustServerCertificate=True;"
  }
}
```

### Encryption Keys

**⚠️ Important**: For production, use environment variables or Azure Key Vault to store encryption keys.

Default keys are in `Program.cs` (lines 57-60):
```csharp
builder.Services.AddSingleton<IEncryptionService>(new AesEncryptionService(
    key: "YOUR_BASE64_KEY",  // Replace with a secure 32-byte key
    iv: "YOUR_BASE64_IV"     // Replace with a secure 16-byte IV
));
```

### Password Policies

Configure in `Program.cs` (lines 23-30):
```csharp
builder.Services.AddIdentity<Utilisateur, IdentityRole>(options =>
{
    options.Password.RequireDigit = true;
    options.Password.RequireLowercase = true;
    options.Password.RequireUppercase = true;
    options.Password.RequireNonAlphanumeric = true;
    options.Password.RequiredLength = 8;
}).AddEntityFrameworkStores<ApplicationDbContext>();
```

---

## 🚀 Usage Guide

### Register an Account

1. Navigate to **Register** page
2. Fill in:
   - Email address
   - Password (8+ characters, mixed case, number, special char)
   - Confirm password
3. Click **Register**

### Add a Password

1. After login, click **Create Account**
2. Fill in the form:
   - **Service**: Platform name (e.g., "GitHub")
   - **Username**: Your account username
   - **Password**: Your password (encrypted automatically)
3. Submit the form

### View Passwords

- Click on any account to view details
- Password is automatically decrypted for viewing
- Use the search bar to find specific accounts

### Edit Account

1. Click **Edit** on any account
2. Modify the information
3. Click **Save**

### Delete Account

1. Click **Delete** on any account
2. Confirm the deletion

---

## 🔒 Security Features

### Encryption

- **Algorithm**: AES (Advanced Encryption Standard)
- **Key Size**: 256 bits
- **Mode**: CBC (Cipher Block Chaining)
- **Implementation**: `AesEncryptionService`

### Authentication

- **Cookie-based authentication** with sliding expiration
- **Session timeout**: 2 minutes of inactivity
- **CSRF tokens** on all forms
- **Password hashing** via ASP.NET Core Identity

### Data Protection

- **Encrypted at rest**: All passwords encrypted before storage
- **Decrypted on demand**: Only when viewing details
- **User isolation**: Each user sees only their accounts

### Breach Detection

Integration with [Have I Been Pwned](https://haveibeenpwned.com/) API to detect compromised credentials.

---

## 📁 Project Structure

```
SecurePass/
├── Controllers/              # MVC Controllers
│   ├── AuthentificationController.cs
│   └── CompteController.cs
├── Data/                     # Database Context
│   └── ApplicationDbContext.cs
├── Models/                   # Entity Models
│   ├── Compte.cs
│   ├── Utilisateur.cs
│   ├── BreachedAccount.cs
│   └── LeakInfo.cs
├── DTOs/                     # Data Transfer Objects
│   ├── CompteDTO.cs
│   ├── CompteUpdateDTO.cs
│   ├── LoginDto.cs
│   ├── RegisterDTo.cs
│   ├── ForgotPasswordDto.cs
│   └── ResetPasswordDto.cs
├── Interface/                # Service Interfaces
│   ├── IAccountRepository.cs
│   ├── IEncryptionService.cs
│   ├── ITokenService.cs
│   ├── IPwnedService.cs
│   └── ILogoutBackgroundService.cs
├── Repository/               # Data Access Layer
│   └── AccountRepository.cs
├── Services/                  # Business Logic
│   ├── AesEncryptionService.cs
│   ├── TokenService.cs
│   ├── PwnedService.cs
│   └── LogoutBackgroundService.cs
├── Validator/                # FluentValidation Validators
│   ├── CompteDtoValidator.cs
│   ├── CompteUpdateDtoValidator.cs
│   ├── LoginDtoValidator.cs
│   └── RegisterDToValidators.cs
├── Exceptions/               # Custom Exceptions
│   └── AccountNotFoundException.cs
├── Views/                    # Razor Views
│   ├── Authentification/
│   ├── Compte/
│   └── Shared/
├── wwwroot/                  # Static Files
│   ├── css/
│   ├── js/
│   └── lib/
└── Migrations/               # EF Core Migrations
```

---

## 🖼️ Screenshots


- Login page

  ![Login](docs/screenshots/login.png)

- Sign Up page

  ![Login](docs/screenshots/login.png)

- Dashboard

  ![Dashboard](docs/screenshots/dashboard.png)

- Profil details

  ![Details](docs/screenshots/profile.png)

- DataBase details

  ![Details](docs/screenshots/DB.png)

Optionally use HTML for sizing:

<img src="docs/screenshots/login.png" alt="Login" width="700" />

---

## 💻 Development

### Building the Project

```bash
# Build for Release
dotnet build -c Release

# Build for Development
dotnet build -c Debug
```

### Running Tests

```bash
# Run all tests
dotnet test
```

### Database Migrations

```bash
# Create a new migration
dotnet ef migrations add MigrationName

# Update database
dotnet ef database update

# Revert database
dotnet ef database update PreviousMigrationName
```

### Code Generation

```bash
# Scaffold a controller with views
dotnet aspnet-codegenerator controller -name ControllerName -m ModelName -dc ApplicationDbContext -outDir Controllers
```

---

## 🤝 Contributing

Contributions are welcome! To contribute:

1. **Fork the repository**
   ```bash
   git clone https://github.com/riyad4589/SecurePassManager-MVC.git
   ```

2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```

3. **Make your changes**
   - Follow existing code style
   - Add comments where necessary
   - Update documentation

4. **Commit your changes**
   ```bash
   git commit -m "Add amazing feature"
   ```

5. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```

6. **Open a Pull Request**
   - Provide a clear description
   - Link any related issues
   - Request reviewers

### Coding Standards

- Follow C# coding conventions
- Use meaningful variable names
- Add XML comments for public methods
- Write unit tests for new features
- Ensure no linter warnings

---


## 👤 Author


**IBRAHIMI Aya**

<!-- - GitHub: [@riyad4589](https://github.com/riyad4589) -->
- Email: [ayaibrahimi2609@gmail.com](mailto:ayaibrahimi2609@gmail.com)
<!-- - LinkedIn: []() -->


**MAJGHIROU Mohamed Riyad**

- GitHub: [@riyad4589](https://github.com/riyad4589)
- Email: [riyadmaj10@gmail.com](mailto:riyadmaj10@gmail.com)
- LinkedIn: [Mohamed Riyad MAJGHIROU](https://www.linkedin.com/in/mohamed-riyad-majghirou-5b62aa388/)


**AZZAM Mohamed**

- GitHub: [@Azzammoo10](https://github.com/Azzammoo10)
- Email: [azzam.moo10@gmail.com](mailto:azzam.moo10@gmail.com)
- LinkedIn: [Mohamed AZZAM](https://www.linkedin.com/in/mohamed-azzam-93115823a/)

---


<div align="center">

**⭐ Star this repo if you find it helpful!**

</div>
