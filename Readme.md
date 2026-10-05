# FruitStore

## Description

FruitStore is an ASP.NET Core .NET 8 application for managing and displaying a collection of fruits. It provides a Razor Components user interface and a REST API for retrieving, creating, updating, and deleting fruit information.

## Project Structure

- Components
  - Layout
    - MainLayout.razor
    - MainLayout.razor.css
    - NavMenu.razor
    - NavMenu.razor.css
  - Pages
    - Home.razor
    - Product.razor
  - App.razor
  - Routes.razor
  - _Imports.razor
- Controllers
  - FruitController.cs
  - FruitControllerTest.cs
- Models
  - Fruit.cs
  - FruitContext.cs
- Properties
  - launchSettings.json
- wwwroot
  - bootstrap
  - app.css
  - favicon.png
- FruitStore.csproj
- FruitStore.http
- FruitStore.sln
- Program.cs

## Key Classes and Interfaces

- `Fruit` represents a fruit and contains its ID, name, description, price, stock status, and origin.
- `FruitContext` provides Entity Framework Core access to fruit data.
- `FruitController` provides REST operations for retrieving, creating, updating, and deleting fruits.
- `Home` displays the available fruits.
- `Product` displays detailed information for an individual fruit.

## Usage

Run the application:

`dotnet run`

Run all unit tests:

`dotnet test`

Run the fruit enumeration test:

`dotnet test --filter "FullyQualifiedName~FruitControllerTests.GetFruits_ReturnsAllFruits"`

The REST API is available under `/api/Fruit`, and Swagger provides an interface for testing the API.

### Dependencies

- .NET 8
- ASP.NET Core
- Entity Framework Core
- Entity Framework Core InMemory
- Entity Framework Core SQL Server
- Swashbuckle.AspNetCore
- Microsoft.OpenApi
- xUnit
- Microsoft.NET.Test.Sdk
- Moq
- coverlet.collector

## License

This project is provided for Contoso training and assessment purposes.
