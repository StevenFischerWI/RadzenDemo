# RadzenDemo

Demonstrates an issue with the Radzen DropDown control for Blazor and .NET 6.0 Preview 3. The following error occurrs when selecting an item in a DropDown control. I believe this is related to a breaking change in System.Linq.Queryable (referenced here: https://docs.microsoft.com/en-us/dotnet/core/compatibility/core-libraries/6.0/additional-linq-queryable-method-overloads).

blazor.webassembly.js:1 crit: Microsoft.AspNetCore.Components.WebAssembly.Rendering.WebAssemblyRenderer[100]
      Unhandled exception rendering component: The type initializer for 'System.Linq.Dynamic.Core.DynamicQueryableExtensions' threw an exception.
System.TypeInitializationException: The type initializer for 'System.Linq.Dynamic.Core.DynamicQueryableExtensions' threw an exception.
 ---> System.Exception: Specific method not found: FirstOrDefault
 ---> System.InvalidOperationException: Sequence contains more than one matching element
