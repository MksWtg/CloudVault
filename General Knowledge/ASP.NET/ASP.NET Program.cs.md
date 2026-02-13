This is a walkthrough of a common ASP.NET `Program.cs` file and what typical configuration looks like.

```C#
var builder = WebApplication.CreateBuilder(args);

// Add services to the container
builder.Services.AddControllers();           // Add API controllers
builder.Services.AddEndpointsApiExplorer(); // Enables Swagger generation
builder.Services.AddSwaggerGen();           // Add Swagger UI for testing

var app = builder.Build();

// Configure middleware
if (app.Environment.IsDevelopment())
{
    app.UseSwagger();
    app.UseSwaggerUI(); // Accessible at /swagger
}

app.UseHttpsRedirection();

app.UseAuthorization();

app.MapControllers(); // Map controller routes

app.Run();
```

The `WebApplicationBuilder` object, `builder`, is used to configure how the app will behave.

`AddControllers` registers the controllers- after 