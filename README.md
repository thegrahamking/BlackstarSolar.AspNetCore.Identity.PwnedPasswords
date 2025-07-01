> [!WARNING]  
> This project and the associated nuget package are no longer maintained.

# BlackstarSolar.AspNetCore.Identity.PwnedPasswords
This library provides an [IPasswordValidator<TUser>](https://docs.microsoft.com/en-gb/dotnet/api/Microsoft.AspNetCore.Identity.IPasswordValidator-1?view=aspnetcore-2.0) for [Microsoft ASP.NET Core Identity](https://github.com/aspnet/Identity) which validates passwords against [HaveIBeenPwned.com](https://haveibeenpwned.com/)'s [Pwned Passwords](https://haveibeenpwned.com/Passwords) using the v2 RESTful API.
## Usage
To use the default error message:
```c#
public class Startup
{
     public void ConfigureServices(IServiceCollection services)
     {
        services.AddIdentity<MyApplicationUser, IdentityRole>()
            .AddPwnedPasswordsValidator<MyApplicationUser>();
     }
}
```
To specify a custom error message for pwned password:
```c#
public class Startup
{
     public void ConfigureServices(IServiceCollection services)
     {
        services.AddIdentity<MyApplicationUser, IdentityRole>()
            .AddPwnedPasswordsValidator<MyApplicationUser>(options => options.ErrorMessage = "Custom error message");
     }
}
```
## Nuget Package
```
Install-Package BlackstarSolar.AspNetCore.Identity.PwnedPasswords  
```
## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
## Build Status
[![Build Status](https://www.myget.org/BuildSource/Badge/blackstarsolar-build?identifier=cac84494-a7e7-45c0-8d3a-f738d464d9c0)](https://www.myget.org/)
