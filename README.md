<!-- markdownlint-disable MD030 -->

# ChatFlowAI.app Embed

Javascript library to display ChatFlowAI.app chatbot on your website

![Flowise](https://github.com/FlowiseAI/FlowiseChatEmbed/blob/main/images/ChatEmbed.gif?raw=true)

## Embed in your HTML

### PopUp

```html
<script type="module">
  import Chatbot from 'https://cdn.jsdelivr.net/gh/shah743/ChatFlowAIPopUp/dist/web.js';
  Chatbot.init({
    chatflowid: '<chatflowid>',
    apiHost: 'https://chatflowai.app',
  });
</script>
```

### FullPage

```html
<script type="module">
    import Chatbot from 'https://cdn.jsdelivr.net/gh/shah743/ChatFlowAIPopUp/dist/web.js';
    Chatbot.init({
        chatflowid: '<chatflowid>',
        apiHost: 'https://chatflowai.app',
    });
</script>
<flowise-fullchatbot></flowise-fullchatbot>
```

To enable full screen, add `margin: 0` to <code>body</code> style, and confirm you don't set height and width

```html
<body style="margin: 0">
  <script type="module">
      import Chatbot from 'https://cdn.jsdelivr.net/gh/shah743/ChatFlowAIPopUp/dist/web.js';
    Chatbot.initFull({
      chatflowid: '<chatflowid>',
      apiHost: 'https://chatflowai.app',
      theme: {
        chatWindow: {
          // height: 700, don't set height
          // width: 400, don't set width
        },
      },
    });
  </script>
</body>
```

## Configuration

You can also customize chatbot with different configuration

```html

<script type="module">
    import Chatbot from 'https://cdn.jsdelivr.net/gh/shah743/ChatFlowAIPopUp/dist/web.js';

    Chatbot.init({
        chatflowid: '<chatflowid>',
        apiHost: 'https://chatflowai.app',
        chatflowConfig: {
            // topK: 2
        },
        observersConfig: {
            // (optional) Allows you to execute code in parent based upon signal observations within the chatbot.
            // The userinput field submitted to bot ("" when reset by bot)
            observeUserInput: (userInput) => {
                console.log({userInput});
            },
            // The bot message stack has changed
            observeMessages: (messages) => {
                console.log({messages});
            },
            // The bot loading signal changed
            observeLoading: (loading) => {
                console.log({loading});
            },
        },
        theme: {
            button: {
                backgroundColor: '#3B81F6',
                right: 20,
                bottom: 20,
                size: 'medium',
                iconColor: 'white',
                customIconSrc: 'https://chatflowaiapp.sgp1.cdn.digitaloceanspaces.com/message.svg',
            },
            chatWindow: {
                showTitle: true, // show/hide the title bar
                title: 'ChatFlowAI.app Bot',
                titleAvatarSrc: 'https://chatflowaiapp.sgp1.cdn.digitaloceanspaces.com/avatar.svg',
                welcomeMessage: 'Hello! This is custom welcome message',
                backgroundColor: '#ffffff',
                height: 700,
                width: 400,
                fontSize: 16,
                botMessage: {
                    backgroundColor: '#f7f8ff',
                    textColor: '#303235',
                    showAvatar: true,
                    avatarSrc: 'https://chatflowaiapp.sgp1.cdn.digitaloceanspaces.com/bot.svg',
                },
                userMessage: {
                    backgroundColor: '#3B81F6',
                    textColor: '#ffffff',
                    showAvatar: true,
                    avatarSrc: 'https://chatflowaiapp.sgp1.cdn.digitaloceanspaces.com/user.svg',
                },
                textInput: {
                    placeholder: 'Type your question',
                    backgroundColor: '#ffffff',
                    textColor: '#303235',
                    sendButtonColor: '#3B81F6',
                },
            },
        },
    });
</script>
```
