AspNet.Security.OpenIdConnect.Samples
=====================================

Based on the ASP.NET Core samples demonstrating how to use the [ASP.NET OpenID Connect server](https://github.com/aspnet-contrib/AspNet.Security.OpenIdConnect.Server) with MVC or JS apps.

Note: the samples hosted on this repository target ASP.NET Core 2.0, Version  2.0.2 currently 

## [MVC](./samples/Mvc)

This sample shows two separate web applications, potentially running on separate servers, playing the roles of a client and a server with regard to authentication.

#### [Mvc.Client](./samples/Mvc/Mvc.Client)

To the user, `Mvc.Client` is the main web application, offering for example a login page and a home page (see `HomeController`). 
It plays as the *client* from the point of view of authentication, as it does not implement authentication services on its own and asks the `Mvc.Server` project for those through interactive OpenID Connect requests.

#### [Mvc.Server](./samples/Mvc/Mvc.Server)

To the user, `Mvc.Server` is almost invisible. 
It offers authentication services to client web application by means of its REST API endpoints, playing as the *authorization server* mentioned in OpenID Connect scenarios.
In this role, it's also responsible of rendering the authorization consent form (see `AuthorizationController`).

Besides from APIs to request and refresh tokens, `Mvc.Server` also offers an API to access a protected resource, whose data are only accessible to authenticated users (see `ResourceController`).
Thus, it also plays as the *resource server* of an OpenID Connect scenario.

Note that, generally speaking, authorization server and resource server could also be split in two separate web applications.

This project is licensed under the **Apache License**. This means that you can use, modify and distribute it freely. See [http://www.apache.org/licenses/LICENSE-2.0.html](http://www.apache.org/licenses/LICENSE-2.0.html) for more details.
