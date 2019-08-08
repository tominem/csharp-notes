
# Entity Framework - Alura (Notes)

Entity Framework is an ORM tool to handle the persistence layer in c# .Net applications.

## Instalation

The easiest way is using Nuget Package Manager Console to install: 

1. Open Nuget Console and enter 
```shell
  Install-Package Microsoft.EntityFrameworkCore.SqlServer =Version [versionNumber]
```

2. Wait until the installation ends, then we will have those packages below installed:

    - Microsoft.EntityFrameworkCore
    - Microsoft.EntityFrameworkCore.Relational
    - Microsoft.EntityFrameworkCore.SqlServer

## Database Providers

Entity Framework Core can access many different databases through plug-in libraries called [database providers](https://docs.microsoft.com/en-us/ef/core/providers/).

> [Note] There is a peculiar provider that is useful for test purposes called [InMemory Provider](https://docs.microsoft.com/en-us/ef/core/miscellaneous/testing/in-memory)

## Context or DAOs

- Entity classes are named adding the suffix ***"Context"*** to the real name for convention, e.g. ***"Product"*** turns into ***"ProductContext"***
- They should extend from [DBContext](https://docs.microsoft.com/en-us/dotnet/api/system.data.entity.dbcontext?view=entity-framework-6.2.0)
- Is necessary within the class define a property [***DbSet<TEntity>***](https://docs.microsoft.com/en-us/dotnet/api/system.data.entity.dbset-1?view=entity-framework-6.2.0) whose name should be the
same as the name of referenced database table.
- Since version 6, the method **SaveChanges()** from DBContext class supports transactions. For more advanced transaction features is possible to use both **BeginTransaction()** and 
**UserTransaction()** methods available in the **Database** property, for more details read the [page](https://msdn.microsoft.com/en-us/library/dn456843.aspx)

## Entity Framework for a Java Developer

- It does what Hibernate does with Java.
- Providers are like JDBC drivers that has different [DBMS](https://searchsqlserver.techtarget.com/definition/database-management-system) providers.
- DAO classes are named Context classes and we need to add the suffix ***"Context"*** to the entity class name for convention, e.g. ***"Product"*** turns into ***"ProductContext"***
