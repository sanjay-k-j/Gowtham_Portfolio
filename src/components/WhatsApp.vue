<template>
  <div>
    <!-- WhatsApp Button (fixed at the bottom-right) -->
    <div class="whatsapp-button">
      <img src="@/assets/whatsapp.png" alt="whatsapp" id="whatsapp" />
    </div>

    <!-- Chat Container (hidden by default) -->
    <div class="chat-container" id="chat-container">
      <!-- Close Button (X) -->
      <button class="close-button" id="close-button">X</button>

      <div class="chat-header">
        <img src="@/assets/background.png" alt="Profile Picture" class="profile-picture" />
        <div class="chat-info">
          <span class="chat-name">Gowtham</span>
          <span class="chat-status">Online</span>
        </div>
      </div>
      <div class="chat-messages" id="chat-messages">
        <div class="message received">
          Hello! <br />Explore diverse trading and investment opportunities with our expert guidance. Leave us a message, and we’ll help you reach your financial goals.
          <br><br>
          Best regards,<br>
          Gowtham 
        </div>
      </div>
      <div class="chat-input">
        <input type="text" placeholder="Type a message" id="message-input" />
        <button id="sendButton">➤</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "WhatsApp",
  mounted() {
    const whatsapp = document.getElementById("whatsapp");
    const chatContainer = document.getElementById("chat-container");
    const messageInput = document.getElementById("message-input");
    const sendButton = document.getElementById("sendButton");
    const closeButton = document.getElementById("close-button");

    const whatsappNumber = "+918296601933";

    // Initially hide the chat container
    chatContainer.style.display = "none";

    // Toggle chat container visibility on WhatsApp button click
    whatsapp.addEventListener("click", (event) => {
      chatContainer.style.display = chatContainer.style.display === "none" ? "block" : "none";
      event.stopPropagation(); // Prevent event from propagating to the document
    });

    // Close chat container if click is outside it
    document.addEventListener("click", (event) => {
      if (!chatContainer.contains(event.target) && event.target.id !== "whatsapp") {
        chatContainer.style.display = "none";
      }
    });

    // Function to send message
    function sendMessage() {
      const message = messageInput.value.trim();
      if (message) {
        const whatsappUrl = `https://wa.me/${whatsappNumber}?text=${encodeURIComponent(message)}`;
        window.open(whatsappUrl, "_blank");
        messageInput.value = ""; // Clear the input after sending
      }
    }

    sendButton.addEventListener("click", sendMessage);

    // Send message on pressing Enter
    messageInput.addEventListener("keypress", (e) => {
      if (e.key === "Enter") {
        sendMessage();
      }
    });

    // Close the chat when "X" button is clicked
    closeButton.addEventListener("click", () => {
      chatContainer.style.display = "none";
    });
  },
};
</script>

<style scoped>
.whatsapp-button {
  position: fixed;
  right: 0px;
  bottom: 20px;
  z-index: 10;
  cursor: pointer;
}

.whatsapp-button img {
  width: 55px;
  height: 55px;
}

.chat-container {
  width: 300px;
  position: fixed;
  right: 20px;
  bottom: 80px;
  border-radius: 1rem;
  z-index: 10;
  overflow: hidden;
  display: none;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
  right: 60px;
}

.close-button {
  position: absolute;
  top: 15px;
  right: 20px;
  background-color: transparent;
  border: none;
  color: white;
  font-size: 20px;
  font-weight: bold;
  cursor: pointer;
  z-index: 20;
}

.close-button:hover {
  color: red;
}

.chat-header {
  background-color: #075e54;
  color: white;
  padding: 10px;
  display: flex;
  align-items: center;
}

.profile-picture {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  margin-right: 10px;
  object-fit: cover;
}

.chat-info {
  display: flex;
  flex-direction: column;
}

.chat-name {
  font-weight: bold;
}

.chat-status {
  font-size: 0.8rem;
}

.chat-messages {
  padding: 10px;
  max-height: 300px;
  overflow-y: auto;
  background-color: #f1f1f1;
}

.message {
  padding: 10px;
  border-radius: 8px;
  margin-bottom: 10px;
  word-wrap: break-word;
  max-width: 70%;
}

.received {
  background-color: #ffffff;
  float: left;
  text-align: left;
  margin-left: 0px; /* Adjusted margin */
}

.chat-input {
  padding: 10px;
  background-color: #ffffff;
  display: flex;
  align-items: center;
  margin-left: 0px;
}

.chat-input input {
  flex-grow: 1;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 20px;
  margin-right: 10px;
}

.chat-input button {
  background-color: #075e54;
  color: white;
  border: none;
  padding: 10px;
  border-radius: 50%;
  cursor: pointer;
}

.chat-input button:hover {
  background-color: #128c7e;
}
</style>
