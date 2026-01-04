# 💎 Zodiac Jewelry Web API

A comprehensive **ASP.NET Core Web API** for managing a zodiac-themed jewelry e-commerce platform.  
This project provides APIs for product management, user authentication, order processing, and zodiac-based product recommendations.

---

## 🌟 Features

- **User Management**
  - Registration & authentication
  - Role-based authorization (**Admin, Staff, Customer**)
- **Product Catalog**
  - Products, categories, materials, collections
  - Zodiac-based product association
- **Image Management**
  - Cloud image upload & storage with **Cloudinary**
- **Order Processing**
  - Full order lifecycle management
  - **PayOS** payment integration
- **Authentication & Security**
  - JWT-based authentication
  - Role-based access control
- **Email Services**
  - Email verification
  - Password reset
- **Swagger**
  - Interactive API documentation

---

## 🏗️ Architecture

This project follows **Clean Architecture** principles:

```text
ZodiacJewelryWebAPI/
├── ZodiacJewelryWebAPI/     # Presentation Layer (Web API)
├── Application/             # Application Layer (Business Logic)
├── Infrastructure/          # Infrastructure Layer (Data Access, Services)
└── Domain/                  # Domain Layer (Entities)
```

---

## 🧰 Key Technologies

- **.NET 8.0**
- **ASP.NET Core Web API**
- **Entity Framework Core**
- **SQL Server**
- **JWT Bearer Authentication**
- **AutoMapper**
- **Cloudinary**
- **PayOS**
- **Swagger (OpenAPI)**

---

## 🚀 Getting Started

### Prerequisites

- .NET 8 SDK or later
- SQL Server (LocalDB or full version)
- Visual Studio 2022 or VS Code

---

### Installation

#### 1. Clone the repository

```bash
git clone https://github.com/your-username/ZodiacJewelryWebAPI.git
cd ZodiacJewelryWebAPI
```

#### 2. Restore dependencies

```bash
dotnet restore
```

#### 3. Configure the database

Update `appsettings.Development.json`:

```json
{
  "ConnectionStrings": {
    "DatabaseConnection": "your-sql-server-connection-string"
  }
}
```

#### 4. Configure application settings

```json
{
  "JWTSection": {
    "Issuer": "your-issuer",
    "Audience": "your-audience",
    "SecretKey": "your-secret-key-minimum-32-characters"
  },
  "Cloudinary": {
    "CloudName": "your-cloudinary-name",
    "ApiKey": "your-api-key",
    "ApiSecret": "your-api-secret"
  },
  "Environment": {
    "PAYOS_CLIENT_ID": "your-payos-client-id",
    "PAYOS_API_KEY": "your-payos-api-key",
    "PAYOS_CHECKSUM_KEY": "your-payos-checksum-key"
  }
}
```

#### 5. Apply database migrations

```bash
dotnet ef database update
```

#### 6. Run the application

```bash
dotnet run
```

---

## 📚 API Documentation

- **Base URL (Development)**: `https://localhost:7000`
- **Swagger UI**: Available at the root URL

---

## 🔐 Authentication

Most endpoints require a JWT token.

```text
Authorization: Bearer your-jwt-token
```

### User Roles

- **Admin**: Full system access
- **Staff**: Product & order management
- **Customer**: Browse products & place orders

---

## 🗄️ Database Schema

### Core Entities

- User
- Product
- Category
- Material
- Zodiac
- Order
- OrderDetail
- Collection
- ProductImage

---

## 🛠️ Development

### Project Structure

```text
Application/
├── IRepositories/
├── IServices/
├── Utils/
├── ViewModels/
└── Commons/

Infrastructure/
├── Repositories/
├── Services/
└── Mappers/

Domain/
└── Entities/

ZodiacJewelryWebAPI/
├── Controllers/
├── Middlewares/
└── Program.cs
```

---

## ⚙️ Key Implementations

- **Password Hashing**: SHA256 (`HashPass.cs`)
- **JWT Generation**: Custom JWT utility
- **Image Upload**: Cloudinary integration
- **Payment Processing**: PayOS integration
- **Email Services**: MailKit

---

## 🔒 Security

- JWT authentication with expiration
- Role-based authorization
- SHA256 password hashing
- CORS configuration
- HTTPS enforced in production

---

## 📝 Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Add tests if applicable
5. Submit a pull request

---

## 📄 License

This project is licensed under the **MIT License**.

---

## 🆘 Support

- Review Swagger documentation
- Check the source code
- Create an issue for bugs or feature requests
