# BulkyBook - ASP.NET Core MVC E-commerce Application

## Description

BulkyBook is a full-featured e-commerce web application built using ASP.NET Core MVC, designed for selling books online. It includes user authentication, product management, shopping cart functionality, order processing, and payment integration with Stripe. The application supports role-based access with separate areas for administrators and customers.

## Features

- **User Authentication**: Registration, login, and social login via Facebook and Microsoft accounts using ASP.NET Core Identity.
- **Role-Based Access**: Admin and Customer roles with restricted access to admin panels.
- **Product Management**: CRUD operations for products, categories, and product images.
- **Shopping Cart**: Add, update, and remove items from the cart.
- **Order Processing**: Place orders, view order history, and manage order statuses.
- **Payment Integration**: Secure payments using Stripe.
- **Email Notifications**: Send emails for order confirmations and other notifications.
- **Admin Panel**: Manage users, companies, orders, products, and categories.
- **Responsive UI**: Built with Bootstrap for a mobile-friendly experience.

## Technologies Used

- **Framework**: ASP.NET Core 8.0 MVC
- **Database**: SQL Server with Entity Framework Core
- **Authentication**: ASP.NET Core Identity with social providers (Facebook, Microsoft)
- **Payment**: Stripe.net
- **Frontend**: Razor Views, Bootstrap, jQuery
- **Architecture**: Repository Pattern, Unit of Work
- **Other**: Email sending, Session management, Migrations

## Prerequisites

Before running the application, ensure you have the following installed:

- .NET 8.0 SDK (download from [Microsoft](https://dotnet.microsoft.com/download/dotnet/8.0))
- SQL Server (LocalDB, Express, or full version)
- Visual Studio 2022 or Visual Studio Code with C# extensions
- Git (for cloning the repository)

## Installation and Setup

1. **Clone the Repository**:
   ```
   git clone <repository-url>
   cd Bulky_MVC
   ```

2. **Restore NuGet Packages**:
   ```
   dotnet restore
   ```

3. **Database Configuration**:
   - Update the connection string in `BulkyWeb/appsettings.json`:
     ```json
     "ConnectionStrings": {
       "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=BulkyBook;Trusted_Connection=True;MultipleActiveResultSets=true"
     }
     ```
   - Run Entity Framework migrations to create the database:
     ```
     cd BulkyWeb
     dotnet ef database update
     ```

4. **Stripe Configuration**:
   - Sign up for a Stripe account at [Stripe](https://stripe.com).
   - Update `BulkyWeb/appsettings.json` with your Stripe keys:
     ```json
     "Stripe": {
       "SecretKey": "your-stripe-secret-key",
       "PublishableKey": "your-stripe-publishable-key"
     }
     ```

5. **Social Login Configuration** (Optional):
   - For Facebook login, update the App ID and Secret in `BulkyWeb/Program.cs`.
   - For Microsoft login, update the Client ID and Secret in `BulkyWeb/Program.cs`.

6. **Build and Run the Application**:
   ```
   dotnet build
   dotnet run
   ```
   - The application will start at `https://localhost:5001` (or the port specified in `launchSettings.json`).

## Usage

- **Customer Area**: Browse products, add to cart, checkout, and view orders.
- **Admin Area**: Access `/Admin` for managing the application (requires Admin role).
- **Identity Pages**: User registration, login, and account management are handled via ASP.NET Core Identity UI.

## Project Structure

- **BulkyWeb**: Main web application project.
- **Bulky.DataAccess**: Data access layer with repositories, migrations, and database context.
- **Bulky.Models**: Entity models and view models.
- **Bulky.Utility**: Utility classes for email, Stripe settings, and constants.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes. Ensure code follows the project's coding standards and includes appropriate tests.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments

- Built following ASP.NET Core best practices.
- Inspired by e-commerce tutorials and open-source projects.
