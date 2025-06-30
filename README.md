# Hotels Booking System MVC

This project provides an online Hotels Booking Management System using ASP.NET Core MVC. Users can browse hotels, make reservations, save drafts in a smart draft reservation system, Apply promo codes, and pay via Stripe. Admins can manage hotels, users, and system data.

## Features

- **User Authentication**  
  - Registration & login with email/password  
  - External logins via **Google** and **Facebook**  
  - Role-based authorization (User/Admin)
    
- **Booking Management**  
  - Hotel/city/country browsing  
  - Room reservation system  
  - Draft reservation saving  
  - **Stripe payment integration**
    
- **Admin Features**  
  - Manage hotels, rooms, and locations (cities/countries)  
  - Handle promo codes and reports  
  - Moderate user reviews  
  - Admins can assign different roles to users and Add hotels and cities and countries .

## Project Structure

The project follows a layered architecture and includes the following components:

### Models
- **User Management**: `AppUser.cs`, `Favorite.cs`  
- **Locations**: `City.cs`, `Country.cs`  
- **Hotels**: `Hotel.cs`, `HotelImage.cs`, `Room.cs`, `RoomImages.cs`, `Amenity.cs`  
- **Bookings**: `Reservation.cs`, `ReservationRoom.cs`, `DraftReservation.cs`, `DraftReservationRoom.cs`  
- **Payments**: `Payment.cs`, `PaymentMethod.cs`, `Invoice.cs`, `StripeSettings.cs`  
- **Miscellaneous**: `PromoCode.cs`, `UsedPromoCode.cs`, `Report.cs`, `Reviews.cs`, `MailSettings.cs`  

### Controllers
- **AccountController**: Handles authentication (login/registration)  
- **HotelController**: Manages hotel listings and details  
- **ReservationController**: Processes bookings  
- **PaymentController**: Handles Stripe transactions  
- **Admin Controllers**:  
  - `CityController`, `CountryController`, `ReportController`, `PromoCodeController`
  
- **Services**: Contains business logic for handling various operations.
- **Helpers**: Manages AutoMapper and configuration classes for JWT and other requirements.
- **Assets**: Used for testing the API with different types of inputs.
- **DTO (Data Transfer Objects)**: Handles different models used for user requests.



## Technologies Used

- **C#**
- **ASP.NET Core**
- **Entity Framework Core**
- **HTML**
- **CSS**
- **MVC**
  

## Required Tools and Technologies

This project requires the following tools and technologies:

- **Visual Studio 2022**: The recommended Integrated Development Environment (IDE) for this project, providing full support for .NET 8.0 and additional tools like scaffolding and debugging.
- **.NET 8.0 SDK**: The project is built using the .NET 8.0 framework, which must be installed for development and running the application.
- **SQL Server**: A relational database system used to store the forum data, including user information, posts, and comments.


### NuGet Packages  

- **Google.Apis.Auth.AspNetCore3 (1.69.0)** - Enables Google authentication in ASP.NET Core applications.  
- **GoogleMaps.LocationServices (1.2.0.5)** - Provides geolocation services using Google Maps API.  
- **MailKit (4.10.0)** - A cross-platform mail client library for sending and receiving emails.  
- **Microsoft.AspNetCore.Authentication.Facebook (8.0.13)** - Handles Facebook authentication in ASP.NET Core applications.  
- **Microsoft.AspNetCore.Authentication.Google (8.0.13)** - Manages Google authentication in ASP.NET Core applications.  
- **Microsoft.AspNetCore.Identity.EntityFrameworkCore (8.0.0)** - Integrates ASP.NET Core Identity with Entity Framework Core for user management.  
- **Microsoft.EntityFrameworkCore (8.0.13)** - Provides Object-Relational Mapping (ORM) to interact with databases.  
- **Microsoft.EntityFrameworkCore.Design (8.0.13)** - Supports design-time tools for Entity Framework Core.  
- **Microsoft.EntityFrameworkCore.SqlServer (8.0.0)** - Enables Entity Framework Core to work with SQL Server databases.  
- **Microsoft.EntityFrameworkCore.Tools (8.0.0)** - Provides command-line tools for Entity Framework Core.  
- **Microsoft.Owin.Security.Google (42.2)** - Supports Google authentication in OWIN-based applications.  
- **Microsoft.VisualStudio.Web.CodeGeneration.Design (8.0.7)** - Facilitates code generation in ASP.NET Core projects.  
- **MimeKit (4.10.0)** - A library for parsing and creating MIME messages.  
- **Stripe.net (47.4.0)** - A .NET client for the Stripe API, enabling payment processing.  



## Configuration

Add these to your `appsettings.json`:

```json
"Stripe": {
  "SecretKey": "your_stripe_secret_key",
  "PublishableKey": "your_stripe_publishable_key"
},
"Authentication": {
  "Google": {
    "ClientId": "your_google_client_id",
    "ClientSecret": "your_google_client_secret"
  },
  "Facebook": {
    "AppId": "your_facebook_app_id",
    "AppSecret": "your_facebook_app_secret"
  }
}
