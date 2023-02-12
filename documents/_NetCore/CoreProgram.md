---
title: .Net Core Initialization Steps
layout: default
---


The following are my notes on setting up a .Net Core project with elmah and serilog and other needs after doing a `dotnet new`.

### Versioning

| Operation | Nuget | Program.cs |
|-|-|-|
| Add Versioning | `Install-package Microsoft.Aspnetcore.MVC.Versioning` | Builder.Services |

##### Code
``` 
builder.Services.AddApiVersioning(setupAction =>
    {
    setupAction.AssuncDefaultVersionWhenUnspecifiod = true;
    setupAction.DefaultApiVersion = new Microsoft.AspNetCore.Mvc.ApiVersion(l, 0); 
    setupAction.ReportApiVersions = true;
    });
``` 
### Only Accept JSON

| Operation | Nuget | Program.cs |
|-|-|-|
| JSON | None | Builder.Services |

##### Code
``` 
builder.Services.AddControllers( options =>
{
    // Will return a 406 if Json is not requested
    options.ReturnHttpNotAcceptable = true; 
});
```

### Elmah Exception Page

| Operation | Nuget | Program.cs |
|-|-|-|
| Elmah | Install-package  elmahcore | Builder.Services |

##### Before/After Build

``` 
builder.Services.AddElmah();

var app = builder.Build();

// Configure the HTTP request pipeline.
if (app.Environment.IsDevelopment())
{
    app.UseSwagger();
    app.UseSwaggerUI();
    app.UseElmahExceptionPage();
}
```

##### After Authorization

```
app.UseHttpsRedirection();

app.UseAuthorization();

app.UseElmah(); // after auth
```