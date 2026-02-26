# ultra_mlp_ai
hello 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Ultra MLP AI Simulation</title>
<style>
body { font-family: Arial; background: #222; color: #eee; padding: 20px; }
#chat { border: 1px solid #555; padding: 10px; height: 400px; overflow-y: scroll; margin-bottom: 10px; background: #111; }
input { width: 80%; padding: 8px; }
button { padding: 8px; }
</style>
</head>
<body>

<h2>Ultra MLP AI Simulation</h2>
<div id="chat"></div>
<input id="input" placeholder="Type /ask or /math command..." />
<button onclick="sendMessage()">Send</button>

<script>
const ultraFeatures = [
  "math","logic","trivia","storytelling","jokes","riddles",
  "history","science","geography","language","coding",
  "astronomy","physics","chemistry","biology","music",
  "art","philosophy","literature","sports","AI"
  // ... 200+ özellik eklenebilir
];

const chatBox = document.getElementById("chat");
const input = document.getElementById("input");

function appendMessage(sender, msg) {
  const div = document.createElement("div");
  div.innerHTML = `<b>${sender}:</b> ${msg}`;
  chatBox.appendChild(div);
  chatBox.scrollTop = chatBox.scrollHeight;
}

function ultraAIResponse(question) {
  const q = question.toLowerCase();
  if(q.includes("capital of france")) return "The capital of France is Paris.";
  if(q.includes("joke")) return "Why did the math book look sad? Too many problems!";
  if(q.includes("hello") || q.includes("hi")) return "Hello! How can I help you today?";
  if(q.includes("define")) return "Here’s a definition simulation: ...";
  if(q.includes("solve") || q.includes("calculate")) return "Simulated calculation result: 42";

  // Genel rastgele simülasyon (9 milyon kombinasyon mantığı)
  const responses = [
    "Interesting question! Let’s think carefully.",
    "Hmm… that’s a tough one, but I can help.",
    "I’m not sure, but here’s a hint: consider the details.",
    "That’s fascinating! Try analyzing it step by step.",
    "Simulated AI response: explore the possibilities."
  ];
  return responses[Math.floor(Math.random() * responses.length)];
}

function sendMessage() {
  const msg = input.value.trim();
  if(msg === "") return;
  appendMessage("Player", msg);
  input.value = "";

  if(msg.startsWith("/ask")) {
    const question = msg.slice(4).trim();
    if(question === "") appendMessage("Ultra MLP AI", "Please ask a question.");
    else appendMessage("Ultra MLP AI", ultraAIResponse(question));
  } else if(msg.startsWith("/math")) {
    const expr = msg.slice(5).trim();
    if(expr === "") appendMessage("Ultra MLP AI", "Please provide a math expression.");
    else {
      try {
        const result = eval(expr);
        appendMessage("Ultra MLP AI", "Result: " + result);
      } catch {
        appendMessage("Ultra MLP AI", "Invalid math expression.");
      }
    }
  } else {
    appendMessage("Ultra MLP AI", "Unknown command. Use /ask or /math.");
  }
}

// Enter ile gönderme
input.addEventListener("keydown", e => { if(e.key === "Enter") sendMessage(); });
</script>

</body>
</html>
