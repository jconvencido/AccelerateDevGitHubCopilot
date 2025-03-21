# Library App

## Description
The Library App is a console-based application for managing a library system. It allows users to search for patrons, view their details, manage book loans, and renew memberships. The application is built using .NET 8.0 and follows a clean architecture design with separate layers for core logic, infrastructure, and user interface.

## Project Structure
- `AccelerateDevGitHubCopilot.sln` - Solution file for the project.
- `README.md` - Documentation for the project.
- `src/`
  - `Library.ApplicationCore/`
    - `Entities/` - Core domain entities such as `Patron`, `Loan`, `Book`, and `Author`.
    - `Enums/` - Enumerations for statuses like `LoanReturnStatus` and `MembershipRenewalStatus`.
    - `Interfaces/` - Interfaces for repositories and services (`IPatronRepository`, `ILoanService`, etc.).
    - `Services/` - Core business logic services (`LoanService`, `PatronService`).
    - `Library.ApplicationCore.csproj` - Project file for the core library.
  - `Library.Console/`
    - `Json/` - JSON files for storing library data (`Books.json`, `Patrons.json`, etc.).
    - `ConsoleApp.cs` - Main application logic for the console interface.
    - `Program.cs` - Entry point for the application.
    - `CommonActions.cs` - Enum for user actions in the console app.
    - `ConsoleState.cs` - Enum for managing application states.
    - `appSettings.json` - Configuration file for JSON data paths.
    - `Library.Console.csproj` - Project file for the console application.
  - `Library.Infrastructure/`
    - `Data/` - JSON-based repository implementations (`JsonPatronRepository`, `JsonLoanRepository`).
    - `Library.Infrastructure.csproj` - Project file for the infrastructure layer.
- `tests/`
  - `UnitTests/` - Unit tests for the application.
    - `LoanFactory.cs` - Factory for creating test `Loan` objects.
    - `PatronFactory.cs` - Factory for creating test `Patron` objects.
    - `ApplicationCore/`
      - `LoanService/` - Tests for `LoanService` methods.
      - `PatronService/` - Tests for `PatronService` methods.
    - `UnitTests.csproj` - Project file for the unit tests.

## Key Classes and Interfaces
### Core Entities
- `Patron` - Represents a library patron with membership details and loans.
- `Loan` - Represents a book loan with due dates and return status.
- `Book` - Represents a book with metadata like title, author, and genre.
- `Author` - Represents an author of a book.

### Enums
- `LoanReturnStatus` - Status of a loan return operation.
- `MembershipRenewalStatus` - Status of a membership renewal operation.
- `LoanExtensionStatus` - Status of a loan extension operation.

### Interfaces
- `IPatronRepository` - Interface for patron data access.
- `ILoanRepository` - Interface for loan data access.
- `ILoanService` - Interface for loan-related business logic.
- `IPatronService` - Interface for patron-related business logic.

### Services
- `LoanService` - Handles loan-related operations like returning and extending loans.
- `PatronService` - Handles patron-related operations like renewing memberships.

### Console Application
- `ConsoleApp` - Main class for managing the console application's state and user interactions.
- `Program` - Entry point for the console application.

## Usage
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd AccelerateDevGitHubCopilot
