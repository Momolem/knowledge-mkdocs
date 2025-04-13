---
share: true
aliases:
  - UoW
---
# Unit of Work
_Maintains a list of objects affected by a business transaction and coordinates the writing out of changes and the resolution of concurrency problems._

For a full description see [P of EAA](https://martinfowler.com/books/eaa.html) page **184**

![[undefineddocs/assets/img/9b31f1fccae83977ae0a166371b50bcd_MD5.gif|9b31f1fccae83977ae0a166371b50bcd_MD5]]

When you're pulling data in and out of a database, it's important to keep track of what you've changed; otherwise, that data won't be written back into the database. Similarly you have to insert new objects you create and remove any objects you delete.

You can change the database with each change to your object model, but this can lead to lots of very small database calls, which ends up being very slow. Furthermore it requires you to have a transaction open for the whole interaction, which is impractical if you have a business transaction that spans multiple requests. The situation is even worse if you need to keep track of the objects you've read so you can avoid inconsistent reads.

A Unit of Work keeps track of everything you do during a business transaction that can affect the database. When you're done, it figures out everything that needs to be done to alter the database as a result of your work.

## Implementation and Integration in .NET
During our implementation in a project we did several iterations on a unit of work using dependency injection. The following is the concept we finalised on:

```csharp
public class UnitOfWork : IUnitOfWork  
{  
  private readonly DataStoreContext dataStoreContext;
  private readonly CreateRepository createRepository;
  
  public UnitOfWork(
	  DataStoreContext dataStoreContext,
      CreateRepository createRepository)
  {
      this.dataStoreContext = dataStoreContext;
      this.createRepository = createRepository;  
  }  
  
  public delegate IRepository CreateRepository(DataStoreContext context);      
  
  public IRepository Repository 
	  => this.createRepository(this.dataStoreContext);  
  public async Task Commit() => await this.dataStoreContext.SaveChangesAsync();}
```

And the registration in the DI.

```csharp
services.AddTransient<UnitOfWork.CreateRepository>(  
   sp => context => new Repository(context, sp.GetRequiredService<IObjectSerializer>()));
```

This enables us to created the repositories in DI where all the dependencies are resolved, but they all can share the same context so the unit of work can do all actions in one transaction.

We also create a factory for the Unit of Work, which creates the context.