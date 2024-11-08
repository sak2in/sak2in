<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <title>السادس العلمي - موقع دراسي</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #000;
            color: #00ffcc;
            text-align: center;
            margin: 0;
            padding: 0;
        }
        #header {
            background-color: #003366;
            color: #fff;
            padding: 15px;
            font-size: 24px;
        }
        #chat-section, #study-text {
            display: none;
            padding: 20px;
        }
        .message {
            background-color: #333;
            color: #00ffcc;
            padding: 5px;
            margin: 5px;
            border-radius: 5px;
            font-size: 16px;
        }
        #study-text {
            color: #ffffff;
        }
        .btn {
            cursor: pointer;
            background-color: #006666;
            color: #fff;
            padding: 10px;
            margin: 10px;
            border: none;
            font-size: 16px;
        }
    </style>
</head>
<body>
    <div id="header">
        السادس العلمي
        <button onclick="toggleStudyText()" class="btn">عرض النص الدراسي</button>
    </div>
    
    <div id="chat-section">
        <h2>محادثة مشفرة</h2>
        <div id="messages"></div>
        <input type="text" id="message-input" placeholder="أدخل رسالتك هنا" onkeydown="if(event.key === 'Enter') sendMessage()" />
    </div>
    
    <div id="study-text">
        <h2>النص الدراسي</h2>
        <p>هذا هو نص دراسي. يمكن استخدامه في أي وقت للمذاكرة.</p>
    </div>

    <script>
        let chatVisible = false;

        function toggleStudyText() {
            document.getElementById("study-text").style.display = 
                document.getElementById("study-text").style.display === "block" ? "none" : "block";
            document.getElementById("chat-section").style.display = "none";
        }

        function sendMessage() {
            const messageInput = document.getElementById("message-input");
            const messageText = messageInput.value;
            if (messageText.trim() === "") return;
            const messageElement = document.createElement("div");
            messageElement.className = "message";
            messageElement.textContent = messageText;
            document.getElementById("messages").appendChild(messageElement);
            messageInput.value = "";

            // إخفاء الرسالة بعد 10 ثوانٍ
            setTimeout(() => {
                messageElement.style.display = "none";
            }, 10000);  // 10 ثوانٍ
        }
    </script>
</body>
</html>
