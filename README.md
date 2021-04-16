# RadzenDemo

Demonstrates an issue with the Radzen DropDown control for Blazor and .NET 6.0 Preview 3. The following error occurrs when selecting an item in a DropDown control. I believe this is related to a breaking change in System.Linq.Queryable (referenced here: https://docs.microsoft.com/en-us/dotnet/core/compatibility/core-libraries/6.0/additional-linq-queryable-method-overloads).

blazor.webassembly.js:1 crit: Microsoft.AspNetCore.Components.WebAssembly.Rendering.WebAssemblyRenderer[100]
      Unhandled exception rendering component: The type initializer for 'System.Linq.Dynamic.Core.DynamicQueryableExtensions' threw an exception.
System.TypeInitializationException: The type initializer for 'System.Linq.Dynamic.Core.DynamicQueryableExtensions' threw an exception.
 ---> System.Exception: Specific method not found: FirstOrDefault
 ---> System.InvalidOperationException: Sequence contains more than one matching element
   at System.Linq.ThrowHelper.ThrowMoreThanOneMatchException()
   at System.Linq.Enumerable.TryGetSingle[MethodInfo](IEnumerable`1 source, Func`2 predicate, Boolean& found)
   at System.Linq.Enumerable.Single[MethodInfo](IEnumerable`1 source, Func`2 predicate)
   at System.Linq.Dynamic.Core.DynamicQueryableExtensions.GetMethod(String name, Int32 parameterCount, Func`2 predicate)
   --- End of inner exception stack trace ---
   at System.Linq.Dynamic.Core.DynamicQueryableExtensions.GetMethod(String name, Int32 parameterCount, Func`2 predicate)
   at System.Linq.Dynamic.Core.DynamicQueryableExtensions..cctor()
   --- End of inner exception stack trace ---
   at Radzen.DropDownBase`1.<SelectItem>d__65[[RadzenDemo.Client.Pages.Index.Customer, RadzenDemo.Client, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null]].MoveNext()
   at Radzen.Blazor.RadzenDropDown`1.<OnSelectItem>d__18[[RadzenDemo.Client.Pages.Index.Customer, RadzenDemo.Client, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null]].MoveNext()
   at Microsoft.AspNetCore.Components.ComponentBase.CallStateHasChangedOnAsyncCompletion(Task task)
   at Radzen.DropDownBase`1.<SelectItem>d__65[[RadzenDemo.Client.Pages.Index.Customer, RadzenDemo.Client, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null]].MoveNext()
   at Radzen.Blazor.RadzenDropDown`1.<OnSelectItem>d__18[[RadzenDemo.Client.Pages.Index.Customer, RadzenDemo.Client, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null]].MoveNext()
   at Microsoft.AspNetCore.Components.ComponentBase.CallStateHasChangedOnAsyncCompletion(Task task)
   at Microsoft.AspNetCore.Components.RenderTree.Renderer.GetErrorHandledTask(Task taskToHandle)
