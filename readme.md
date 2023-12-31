# Base objects for application layer
## Introduction
This library help us to increase the speed for develop objects for application layer, providing interfaces and classes for that.  
## How to install
For installing this package, you must execute the following command:  
```
dotnet add package accelerate.application
```
## How to use
### Writing a custom data transfer object
``` csharp
public class MyDto : DataTransferObject
{
    private Boolean _disposed;

    // Declare properties to expose

    /// <inherithdoc />
    protected override void Dispose(Boolean disposing)
    {
        if (_disposed)
        {
            throw new ObjectDisposedException(GetType().Name);
        }

        base.Dispose(disposing);

        if (disposing)
        {
            // Free yours resources memory allocation
        }

        _disposed = true;
    }
}
```
### Writing a custom service
``` csharp
public class MyService : ApplicationService
{
    private Boolean _disposed;

    /// <summary>
    /// Initialize a new instance of <seealso cref="MyService" /> class.
    /// </summary>
    protected MyService()
    {
    }

    // Declare methods to expose

    /// <inherithdoc />
    protected override void Dispose(Boolean disposing)
    {
        if (_disposed)
        {
            throw new ObjectDisposedException(GetType().Name);
        }

        base.Dispose(disposing);

        if (disposing)
        {
            // Free yours resources memory allocation
        }

        _disposed = true;
    }
}
```
## Changes history
**Version 6.0.0**
- Changed version to a system based on .NET Core version supported.  
**Version 1.0.0**
- Include interfaces and base classes for data transfer objects and services.  
