# CrudApp and SSISProject

**CrudApp** is an ASP.NET Core MVC application demonstrating basic Create, Read, Update, and Delete (CRUD) operations on a SQL Server database table (Employees). It uses **Entity Framework Core** for data access and runs locally with Windows Authentication (no username or password).

**SSISProject** includes a SQL Server Integration Services (SSIS) package that bulk-loads employee data from a CSV file into the same Employees table used by the CrudApp application, showcasing how to integrate external data sources into a SQL Server database.

---
## Prerequisites

- Install the [.NET SDK](https://dotnet.microsoft.com/download) (version 6.0 or later).  
- A local instance of **SQL Server** (Express, Developer, or equivalent).  
- **Visual Studio 2022** (or later) with:
  - ASP.NET and web development workload  
  - SQL Server Data Tools (SSDT) and SSIS extension

## Key Points

- **Technologies Used**  
  - ASP.NET Core MVC  
  - Entity Framework Core  
  - SQL Server (local instance, Windows Authentication)  
  - SSIS (SQL Server Integration Services)

- **Local Database**  
  - Connection strings are set for `localhost` with **Trusted_Connection=True**.  
  - The `Employees` table is maintained by EF Core migrations from the CrudApp.

- **Data Loading (SSIS)**  
  - The SSIS package reads from a CSV (flat file) and inserts rows into `Employees`.  
  - **Flat File Source** → **OLE DB Destination** mapping aligns CSV columns to table columns.

---


- **CrudApp/**  
  Contains the ASP.NET Core solution (`.sln`), MVC controllers, models, and views.

- **SSISProject/**  
  Contains the Integration Services project (`.dtproj`) and the `.dtsx` package for data loading.

---

## Usage

- **CrudApp**  
  - Open in Visual Studio or run via the .NET CLI to perform CRUD operations on the `Employees` table.  
  - Default connection string uses `localhost` with no explicit credentials.

- **SSISProject**  
  - Open in SQL Server Data Tools (SSDT) or Visual Studio with SSIS installed to execute the data flow package.  
  - Check and update the Flat File Connection path and OLE DB Connection if necessary.

---
