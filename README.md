<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>My Chatbot</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .chatbox {
      width: 350px;
      background: #fff;
      border-radius: 10px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.2);
      display: flex;
      flex-direction: column;
    }

    .chat-header {
      background: #4CAF50;
      color: white;
      padding: 15px;
      text-align: center;
      border-radius: 10px 10px 0 0;
    }

    .chat-messages {
      flex: 1;
      padding: 10px;
      overflow-y: auto;
    }

    .message {
      margin: 8px 0;
      padding: 8px 12px;
      border-radius: 8px;
      max-width: 80%;
    }

    .user {
      background: #DCF8C6;
      align-self: flex-end;
    }

    .bot {
      background: #eee;
      align-self: flex-start;
    }

    .chat-input {
      display: flex;
      border-top: 1px solid #ccc;
    }

    .chat-input input {
      flex: 1;
      padding: 10px;
      border: none;
      outline: none;
    }

    .chat-input button {
      padding: 10px;
      background: #4CAF50;
      color: white;
      border: none;
      cursor: pointer;
    }
  </style>
</head>
<body>

<div class="chatbox">
  <div class="chat-header">My Chatbot</div>
  <div class="chat-messages" id="chatMessages"></div>
  <div class="chat-input">
    <input type="text" id="userInput" placeholder="Type a message..." />
    <button onclick="sendMessage()">Send</button>
  </div>
</div>

<script>
  function sendMessage() {
    const input = document.getElementById("userInput");
    const message = input.value.trim();
    if (!message) return;

    addMessage(message, "user");
    input.value = "";

    setTimeout(() => {
      const reply = botReply(message);
      addMessage(reply, "bot");
    }, 500);
  }

  function addMessage(text, sender) {
    const chat = document.getElementById("chatMessages");
    const msg = document.createElement("div");
    msg.className = `message ${sender}`;
    msg.innerText = text;
    chat.appendChild(msg);
    chat.scrollTop = chat.scrollHeight;
  }

  function botReply(msg) {
    msg = msg.toLowerCase();

    if (msg.includes("hello") || msg.includes("hi")) {
      return "Hello! 😊 How can I help you?";
    }
    if (msg.includes("name")) {
      return "I'm your custom chatbot 🤖";
    }
    if (msg.includes("bye")) {
      return "Goodbye! Have a great day 👋";
    }
    return "Sorry, I don’t understand that yet.";
  }
</script>

</body>
</html>