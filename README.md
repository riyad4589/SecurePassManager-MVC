<<<<<<< HEAD
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
=======
# SecurePassManager

**SecurePassManager** est une application web sécurisée de gestion de mots de passe, développée avec **ASP.NET Core 8 MVC**. Cette solution permet aux utilisateurs de gérer, chiffrer et sécuriser leurs mots de passe tout en offrant une interface intuitive et des fonctionnalités robustes de sécurité.

---

## Fonctionnalités

- **Gestion des Comptes** : Ajout, mise à jour, suppression et affichage des comptes utilisateurs.
- **Chiffrement Sécurisé** : Utilisation de l'algorithme AES pour chiffrer les mots de passe avant stockage en base de données, avec un déchiffrement uniquement lors de la consultation.
- **Sécurisation des Clés de Chiffrement** : Intégration possible avec **Azure Key Vault**, **AWS Secrets Manager** ou **HashiCorp Vault**.
- **Validation des Données** : Garantie de la validité des entrées grâce à **FluentValidation**.
- **Gestion Centralisée des Erreurs** : Middleware global pour capturer et gérer les erreurs de manière centralisée.
- **Journalisation des Activités** : Mise en place de **Serilog** pour suivre les opérations, analyser les erreurs et auditer les actions.
- **Pagination et Versioning des API** : Support des grandes listes de données et évolutivité des API grâce au versioning.
- **Sécurité Renforcée** : Protection contre les attaques courantes telles que CSRF, XSS et SQL Injection.
- **Authentification et Autorisation** : Système basé sur **ASP.NET Core Identity** avec gestion des rôles pour contrôler l'accès.

---

## Technologies Utilisées

- **Framework** : ASP.NET Core 8
- **Langage** : C#
- **Base de Données** : SQL Server ou SQLite (configuration flexible)
- **Chiffrement** : AES (Advanced Encryption Standard) avec génération dynamique des clés
- **Frontend** : Razor Pages intégré à **Bootstrap** pour une expérience utilisateur fluide et responsive
- **Validation** : FluentValidation pour des formulaires fiables
- **Gestion des Secrets** : Intégration optionnelle avec Azure Key Vault, AWS Secrets Manager ou HashiCorp Vault
- **Journalisation** : Serilog pour les logs et l'audit des activités

---

## Installation

### Prérequis

Avant de commencer, assurez-vous que les éléments suivants sont installés sur votre machine :

- [.NET SDK 8](https://dotnet.microsoft.com/download/dotnet/8.0)
- [SQL Server](https://www.microsoft.com/sql-server) ou [SQLite](https://sqlite.org/download.html)
- Un gestionnaire de secrets tel que **Azure Key Vault**, **AWS Secrets Manager** ou **HashiCorp Vault** (optionnel)

### Étapes d'Installation

1. Clonez le dépôt GitHub :
>>>>>>> c96acb5e9ba149e5f0bffb09d961d59218375b4f
   ```bash
   git clone https://github.com/riyad4589/SecurePassManager-MVC.git
   cd SecurePassManager-MVC
   ```

<<<<<<< HEAD
2. **Navigate to the project directory**
   ```bash
   cd SecurePass
   ```

3. **Restore dependencies**
=======
2. Configurez la chaîne de connexion dans le fichier `appsettings.json` :
   ```json
   {
     "ConnectionStrings": {
    "DefaultConnection": "Server=VotreServeurSQL;Database=VotreBaseDeDonnée;Trusted_Connection=True;TrustServerCertificate=True;"
   }
   }
   ```

3. Restaurez les dépendances :
>>>>>>> c96acb5e9ba149e5f0bffb09d961d59218375b4f
   ```bash
   dotnet restore
   ```

<<<<<<< HEAD
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
=======
4. Appliquez les migrations et mettez à jour la base de données :
>>>>>>> c96acb5e9ba149e5f0bffb09d961d59218375b4f
   ```bash
   dotnet ef database update
   ```

<<<<<<< HEAD
6. **Run the application**
=======
5. Lancez l'application en mode développement :
>>>>>>> c96acb5e9ba149e5f0bffb09d961d59218375b4f
   ```bash
   dotnet run
   ```

<<<<<<< HEAD
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

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Riyad4589**

- GitHub: [@riyad4589](https://github.com/riyad4589)
- Email: [riyadmaj10@gmail.com](mailto:riyadmaj10@gmail.com)

---

## 🙏 Acknowledgments

- [Have I Been Pwned](https://haveibeenpwned.com/) for breach detection API
- [Clearbit](https://clearbit.com/) for logo API
- [ASP.NET Core](https://dotnet.microsoft.com/apps/aspnet) team
- All contributors and users of this project

---

<div align="center">

**Made with ❤️ using ASP.NET Core 8**

⭐ Star this repo if you find it helpful!

</div>
=======
6. Accédez à l'application dans votre navigateur à l'adresse suivante :
   [http://localhost:5000](http://localhost:5000)

---

## Contribution

Les contributions sont les bienvenues ! Pour contribuer :

1. Forkez ce dépôt.
2. Créez une branche pour votre fonctionnalité (`feature/nouvelle-fonctionnalite`).
3. Effectuez vos modifications et commitez-les (`git commit -m "Ajout d'une nouvelle fonctionnalité"`).
4. Poussez sur votre branche (`git push origin feature/nouvelle-fonctionnalite`).
5. Ouvrez une Pull Request.

---

## Licence

Ce projet est sous licence **MIT**. Consultez le fichier [LICENSE](LICENSE) pour plus de détails.

---

## Auteur

Développé par [Riyad4589](https://github.com/riyad4589). N'hésitez pas à me contacter pour toute question ou suggestion à [riyadmaj10@gmail.com](mailto:riyadmaj10@gmail.com).
```

### Étapes pour le Push sur GitHub

Après avoir créé et ajouté ce fichier `README.md`, procédez ainsi pour le pusher sur GitHub :

1. **Ajoutez les modifications** :
   ```bash
   git add README.md
   git commit -m "Ajout du fichier README.md"
   ```

2. **Poussez les changements** :
   ```bash
   git push origin main
   ```

Et voilà ! Votre projet sur GitHub sera bien présenté avec ce fichier.
>>>>>>> c96acb5e9ba149e5f0bffb09d961d59218375b4f
