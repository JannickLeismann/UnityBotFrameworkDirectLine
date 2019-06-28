### Features

- Listen to messages via WebSocket connection
- Support for WebGL (also WebSocket)
- Receive text and attachments
- Easy to customize

# Unity Direct Line Bot Framework Implementation

### How To
Simply clone or download this repository and open the project with Unity 2019.1.5f1 (you can use any other version of unity but for best result and no errors you should take a look at it with the version I developed the project).

**Make sure to get the secret key of the direct line bot you want to connect.**
Here is how to get the secret key: https://docs.microsoft.com/en-gb/azure/bot-service/bot-service-channel-connect-directline?view=azure-bot-service-4.0

1. Open the project with Unity
2. Open the scene called "Main"
3. Find the GameObject called DirectLineConnection and enter your secret key in the field provided
4. Press play and communicate with your bot
5. Watch console for detailed information

#####  If you want to use the code in your project make sure to use the namespace:
```csharp
using namespace DirectLine;
```


##### Setup the connection (setups in Start method by default)
```csharp
DirectLineConnection.instance.Initialize();
```

#####  Send a message to the bot by calling SendMessage
```csharp
DirectLineConnection.instance.SendMessage("Hello Bot");
```
# Reference Scene
![](https://i.ibb.co/n7MJ7D9/Directline-Unity-Bot-Framework.png)


# Important Notes
- **This one is crucial!** In order to achieve a valid connection via WebSocket in WebGL **YOU SHOULD NEVER change the name of the GameObject called DirectLineConnection**. The custom javascript library (.../Assets/Plugins/WebSocket.jslib) requieres an object with excatly this name to send back messages from WebGL JavaScript.

