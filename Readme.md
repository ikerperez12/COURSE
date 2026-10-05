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








<?xml version="1.0" encoding="utf-8"?>
<doc>
  <assembly>
    <name>FruitStore</name>
  </assembly>
  <members>
    <member name="T:FruitStore.Models.Fruit">
      <summary>Represents a fruit available in FruitStore.</summary>
    </member>
    <member name="P:FruitStore.Models.Fruit.Id">
      <summary>Gets or sets the fruit identifier.</summary>
    </member>
    <member name="P:FruitStore.Models.Fruit.Name">
      <summary>Gets or sets the fruit name.</summary>
    </member>
    <member name="P:FruitStore.Models.Fruit.Description">
      <summary>Gets or sets the fruit description.</summary>
    </member>
    <member name="P:FruitStore.Models.Fruit.Price">
      <summary>Gets or sets the fruit price.</summary>
    </member>
    <member name="P:FruitStore.Models.Fruit.Instock">
      <summary>Gets or sets whether the fruit is in stock.</summary>
    </member>
    <member name="P:FruitStore.Models.Fruit.Origin">
      <summary>Gets or sets the fruit origin.</summary>
    </member>

    <member name="T:FruitContext">
      <summary>Provides the Entity Framework Core database context for FruitStore.</summary>
    </member>
    <member name="P:FruitContext.Fruits">
      <summary>Gets or sets the collection of fruits.</summary>
    </member>

    <member name="T:FruitStore.Controllers.FruitController">
      <summary>Provides REST operations for managing fruits.</summary>
    </member>
    <member name="M:FruitStore.Controllers.FruitController.GetFruits">
      <summary>Returns all fruits.</summary>
    </member>
    <member name="M:FruitStore.Controllers.FruitController.GetFruit(System.Int32)">
      <summary>Returns the fruit with the specified identifier.</summary>
    </member>
    <member name="M:FruitStore.Controllers.FruitController.PostFruit(FruitStore.Models.Fruit)">
      <summary>Creates a fruit.</summary>
    </member>
    <member name="M:FruitStore.Controllers.FruitController.PutFruit(System.Int32,FruitStore.Models.Fruit)">
      <summary>Updates a fruit.</summary>
    </member>
    <member name="M:FruitStore.Controllers.FruitController.DeleteFruit(System.Int32)">
      <summary>Deletes a fruit.</summary>
    </member>

    <member name="T:FruitStore.Tests.Controllers.FruitControllerTests">
      <summary>Contains unit tests for FruitController.</summary>
    </member>
  </members>
</doc>





3. Contoso Data Editor
Abre la aplicación Contoso Data Editor del escritorio. El assessment pide documentar dos cosas.
Para unit test framework introduce:
xUnit

Si admite descripción:
The FruitStore project uses xUnit as its unit testing framework.

Para el comando utilizado para ejecutar el test que enumera todas las frutas:
dotnet test --filter "FullyQualifiedName~FruitControllerTests.GetFruits_ReturnsAllFruits"

Guarda los cambios en Contoso Data Editor.
4. Última validación
En PowerShell:
cd C:\GitHub\FruitStore65867426

dotnet build
dotnet test
dotnet test --filter "FullyQualifiedName~FruitControllerTests.GetFruits_ReturnsAllFruits"

Queremos 0 Error(s), Passed: 8 y en el último Passed: 1.
5. Comprueba Git ANTES de añadir nada
git status --short

Ahora añade explícitamente solo los archivos de la solución que queremos entregar:
git add Readme.md
git add Docfx.xml
git add Models/Fruit.cs
git add Models/FruitContext.cs
git add Components/Pages/Home.razor
git add Components/Pages/Product.razor
git add Controllers/FruitController.cs
git add Controllers/FruitControllerTest.cs

No hagas git add ., porque el assessment exige excluir bin, obj y elementos cuyo nombre comienza por ..
Comprueba exactamente lo preparado:
git diff --cached --name-only

Debería ser únicamente algo parecido a:
Components/Pages/Home.razor
Components/Pages/Product.razor
Controllers/FruitController.cs
Controllers/FruitControllerTest.cs
Docfx.xml
Models/Fruit.cs
Models/FruitContext.cs
Readme.md

También:
git status

6. Commit con la finalidad de CADA archivo
El assessment exige que el mensaje incluya los archivos y su propósito. Usa:
git commit -m "Complete FruitStore enhancements and documentation" -m "Readme.md - documents project structure, usage, dependencies, and license.
Docfx.xml - provides XML documentation for project classes, methods, and properties.
Models/Fruit.cs - documents the Fruit model and its properties.
Models/FruitContext.cs - adds ten additional fruits to the data store.
Components/Pages/Home.razor - displays the complete fruit collection.
Components/Pages/Product.razor - displays detailed information for a selected fruit.
Controllers/FruitController.cs - adds POST support, invalid-ID handling, and controller documentation.
Controllers/FruitControllerTest.cs - adds unit tests for all FruitController operations."

Comprueba el commit:
git log -1 --stat

y también:
git status

7. Push final
git push

Si Git te dice que no tiene upstream, usa:
git push -u origin HEAD

Después:
git status

Idealmente:
Your branch is up to date with 'origin/...'
nothing to commit, working tree clean
