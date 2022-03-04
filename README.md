# AppointmentBot

Bot Framework v4 core bot sample.

This bot has been created using [Bot Framework](https://dev.botframework.com), it shows how to:

- Use [LUIS](https://www.luis.ai) to implement core AI capabilities
- Implement a multi-turn conversation using Dialogs
- Handle user interruptions for such things as `Help` or `Cancel`
- Prompt for and validate requests for information from the user

## Prerequisites

This sample **requires** prerequisites in order to run.

### Overview

This bot uses [LUIS](https://www.luis.ai), an AI based cognitive service, to implement language understanding.

### Install .NET Core CLI

- [.NET Core SDK](https://dotnet.microsoft.com/download) 3.1

  ```bash
  # determine dotnet version
  dotnet --version
  ```

### Create a LUIS Application to enable language understanding


Once you created the LUIS model, update `appsettings.json` with your `LuisAppId`, `LuisAPIKey` and `LuisApiEndpointUrl`.

```json
  "LuisAppId": "Your LUIS App Id",
  "LuisAPIKey": "Your LUIS Subscription key here",
  "LuisApiEndpointUrl": "Your LUIS App endpoint"
```
 Or use user secrets
`dotnet user-secrets init`

```
dotnet user-secrets set "LuisApiKey" "[YOUR_LUIS_API_KEY]"
```

`dotnet user-secrets list`



## To try this sample

- In a terminal, navigate to `AppointmentBot`

    ```bash
    # change into project folder
    cd AppointmentBot
    ```

- Run the bot from a terminal or from Visual Studio, choose option A or B.

  A) From a terminal

    ```bash
    # run the bot
    dotnet run
    ```

  B) Or from Visual Studio

  - Launch Visual Studio
  - File -> Open -> Project/Solution
  - Navigate to `AppointmentBot` folder
  - Select `AppointmentBot.csproj` file
  - Press `F5` to run the project

## Testing the bot using Bot Framework Emulator

[Bot Framework Emulator](https://github.com/microsoft/botframework-emulator) is a desktop application that allows bot developers to test and debug their bots on localhost or running remotely through a tunnel.

- Install the Bot Framework Emulator version 4.9.0 or greater from [here](https://github.com/Microsoft/BotFramework-Emulator/releases)

### Connect to the bot using Bot Framework Emulator

- Launch Bot Framework Emulator
- File -> Open Bot
- Enter a Bot URL of `http://localhost:3978/api/messages`

## Generate Models

You can install the BF CLI using the following command: `​​​​npm i -g @microsoft/botframework-cli`

Download the LUIS model JSON file to your project directory, and then run the following command from the project root directory:

```
​​bf luis:generate:cs --in=AppointmentBookingBot.LUISModel.json --out=CognitiveModels/DoctorBooking.cs --className=AppointmentBot.CognitiveModels.DoctorBooking
```

## Deploy the bot to Azure

To learn more about deploying a bot to Azure, see [Deploy your bot to Azure](https://aka.ms/azuredeployment) for a complete list of deployment instructions.

## Further reading

- [Bot Framework Documentation](https://docs.botframework.com)
- [Bot Basics](https://docs.microsoft.com/azure/bot-service/bot-builder-basics?view=azure-bot-service-4.0)
- [Dialogs](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-concept-dialog?view=azure-bot-service-4.0)
- [Gathering Input Using Prompts](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-prompts?view=azure-bot-service-4.0&tabs=csharp)
- [Activity processing](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-concept-activity-processing?view=azure-bot-service-4.0)
- [Azure Bot Service Introduction](https://docs.microsoft.com/azure/bot-service/bot-service-overview-introduction?view=azure-bot-service-4.0)
- [Azure Bot Service Documentation](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0)
- [.NET Core CLI tools](https://docs.microsoft.com/en-us/dotnet/core/tools/?tabs=netcore2x)
- [Azure CLI](https://docs.microsoft.com/cli/azure/?view=azure-cli-latest)
- [Azure Portal](https://portal.azure.com)
- [Language Understanding using LUIS](https://docs.microsoft.com/en-us/azure/cognitive-services/luis/)
- [Channels and Bot Connector Service](https://docs.microsoft.com/en-us/azure/bot-service/bot-concepts?view=azure-bot-service-4.0)

Generated with `dotnet new AppointmentBot` v4.15.2

