﻿# SPFx Bot using Sharepoint List

Bot Framework v4 echo bot sample.

This bot has been created using [Bot Framework](https://dev.botframework.com), it shows how to create a simple bot that accepts input from the user and save it into sharepoint's List.

## Prerequisites

- [.NET Core SDK](https://dotnet.microsoft.com/download) version 3.1

  ```bash
  # determine dotnet version
  dotnet --version
  ```

## To try this sample

- Clone the repository

    ```bash
    git clone https://github.com/OfficeDev/Microsoft-Teams-Samples.git
    ```

- Run the bot from a terminal or from Visual Studio:

  A) From a terminal, navigate to `samples/bot-sharepoint-list/csharp` folder

  ```bash
  # run the bot
  dotnet run
  ```

  B) Or from Visual Studio

  - Launch Visual Studio
  - File -> Open -> Project/Solution
  - Navigate to `samples/bot-sharepoint-list` folder
  - Select `SpfxBotApp.sln` file
  - Press `F5` to run the project

  # Step 1: Know your Tenant ID and Resource ID

    It is very important to know your tenant ID for triggering any kind of service calls.
    You can get your the Tenant ID in following ways:
    1. Using Powershell
    2. Making a call to "_vti_bin/client.svc"
    3. This is the most easiest way browse "/_layouts/15/appprincipals.aspx"

  # Step 2: Register a new app

    You need to register a new addin/app in your Sharepoint site, this will generate a ClientID and a Client Secret,  which we will use to authenticate. Lets see how to do it.

    Go to `_layouts/15/appregnew.aspx` under the SP Online site which you want to use as document repository.

  # Step 3: Update your appSetting.json

  MicrosoftAppId: `<<Your Microsoft Bot_Id>>`

  "MicrosoftAppPassword": `<<Your Microsoft Bot_Secret>>`

  "BaseUrl": `<<Bot_endpoint_url>>`

  "TenantID":  `<<Sharepoint Tenant Id>>`

  "ResourceID": `<<SP_Resource_ID>>`

  "TenantName":  `<<sahrepoint Tenant Name>>`

  "SiteName":  `<<Shareppint site name>>`

  "ListName":  `<<Custom list name which created at site>>`

  "AppClientID": `<<Custom Client App ID created at sharepoint App>>`

  "AppSecret": `<<App Secret Id for sharepoint App>>` 

  # Step 4: Grant permissions
    New Client app has been created in SP Online site, now its time to decide what permissions this app should have on your site. You can grant Site collection, web or even at list level read or write permissions.

    Go to `/_layouts/15/appinv.aspx` and serach with ClientID we generated earlier. The application will fetch all other details based on your ClientID.


### This steps is specific to Microsoft Teams

- Navigate to `teamsAppManifest` folder
- Select the `Manifest.json` and update it with your `Your Bot Id`
- Now zip the manifest.json along with icons
- Go to teams and do `Upload a Custom App` 
- Add the Bot to Microsoft Teams
- Start the conversation with Bot

## Further reading
- [Conversational bots in teams](https://docs.microsoft.com/en-us/microsoftteams/platform/bots/what-are-bots)
- [Conversation Basics](https://docs.microsoft.com/en-us/microsoftteams/platform/bots/how-to/conversations/conversation-basics?tabs=dotnet)
- [Granting Access using sharepoint app only](https://docs.microsoft.com/en-us/sharepoint/dev/solution-guidance/security-apponly-azureacs)
- [Sharepoint using Application Context](https://docs.microsoft.com/en-us/sharepoint/dev/solution-guidance/security-apponly)
- [Sharepoint API basic operations](https://docs.microsoft.com/en-us/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints)
