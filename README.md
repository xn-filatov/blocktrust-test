# Blocktrust test App
This is a Blazor Web Server application that allows users to view pictures from their OneDrive "blocktrust" folder. 
The application uses the Microsoft Graph API to authenticate the user and access their OneDrive files.

# Prerequisites
Before running this application, make sure you have the following prerequisites installed:

.NET 7 SDK
Visual Studio or Visual Studio Code (optional)

You will also have to register an Azure AD app:
https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app

## Getting Started
Clone or download this repository to your local machine.

Open the solution in your preferred development environment (Visual Studio or Visual Studio Code).

Copy `the appsettings.json.example` file and rename it to `appsettings.json` in the project's root directory. 
Update the following variables with your own values:

	{
		"Domain": "<YOUR_AZURE_AD_DOMAIN>",
		"TenantId": "<YOUR_AZURE_AD_TENANT_ID>",
		"ClientId": "<YOUR_AZURE_AD_CLIENT_ID>",
		"ClientSecret": "<YOUR_AZURE_AD_CLIENT_SECRET>"
	}

Save the appsettings.json file.

Build and run the application using the following commands:

	"dotnet build"
	"dotnet run"

Alternatively, you can use your preferred development environment to build and run the application.

Open a web browser and navigate to a link logged in your console. The application should be up and running.

## Usage
On the home page, click the "Sign In with OneDrive" button to authenticate with your OneDrive account.

After successful authentication, you will be redirected back to the home page.

The images will be displayed on the main page. You can scroll through them or sort by name or created date.

## How It Works
This application utilizes the Microsoft Graph API to authenticate with Azure Active Directory (Azure AD) and access the user's OneDrive files. 
The appsettings.json file contains the necessary configuration values for authentication:

	"Domain": Your Azure AD domain name.
	"TenantId": Your Azure AD tenant ID.
	"ClientId": Your Azure AD client ID (registered application ID).
	"ClientSecret": Your Azure AD client secret (registered application secret).
During the authentication process, the application uses the Azure AD OAuth 2.0 flow to obtain an access token. This token is then used to authorize API requests to the Microsoft Graph API, specifically targeting the user's OneDrive "blocktrust" folder.

The retrieved images are displayed on the home page using Blazor components and data binding.
