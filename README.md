<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Digital Self</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #1E1E2E;
            color: white;
            margin: 0;
            height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
        }
        .hidden {
            display: none;
        }
        .start-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 40px;
            border-radius: 10px;
            background: #29293D;
            box-shadow: 0 4px 10px rgba(255, 255, 255, 0.1);
        }
        .start-container h1 {
            margin-bottom: 20px;
        }
        .start-container button {
            margin: 10px;
            padding: 12px 20px;
            border: none;
            background: linear-gradient(45deg, #007AFF, #005BBB);
            color: white;
            border-radius: 8px;
            font-size: 16px;
            cursor: pointer;
            transition: 0.3s;
        }
        .start-container button:hover {
            background: linear-gradient(45deg, #005BBB, #003E8C);
        }
        .app-container {
            display: none;
            width: 100%;
            height: 100vh;
            display: flex;
        }
        .sidebar {
            width: 260px;
            background-color: #29293D;
            padding: 20px;
            display: flex;
            flex-direction: column;
            border-right: 2px solid #44445A;
        }
        .sidebar h3 {
            margin-bottom: 10px;
        }
        .sidebar ul {
            list-style: none;
            padding: 0;
        }
        .sidebar ul li {
            padding: 12px;
            margin-bottom: 8px;
            background-color: #3A3A5A;
            border-radius: 8px;
            cursor: pointer;
            transition: 0.3s;
        }
        .sidebar ul li:hover {
            background-color: #505072;
        }
        .main-container {
            flex: 1;
            display: none;
            flex-direction: column;
        }
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #29293D;
            padding: 15px 20px;
            font-size: 18px;
            box-shadow: 0 4px 6px rgba(255, 255, 255, 0.1);
        }
        .header span {
            cursor: pointer;
        }
        .input-container {
            display: flex;
            padding: 12px;
            background-color: #29293D;
            border-top: 2px solid #44445A;
            justify-content: center;
        }
        .input-container input {
            flex: 1;
            max-width: 500px;
            padding: 12px;
            border-radius: 8px;
            border: none;
            font-size: 16px;
            background-color: #3A3A5A;
            color: white;
        }
        .input-container button {
            margin-left: 10px;
            padding: 12px 18px;
            border: none;
            background: linear-gradient(45deg, #007AFF, #005BBB);
            color: white;
            border-radius: 8px;
            cursor: pointer;
            transition: 0.3s;
        }
    </style>
</head>
<body>
    <div class="start-container" id="startPage">
        <h1>Welcome to Digital Self</h1>
        <p>A unified user-owned profile for all AI agents.</p>
        <button onclick="startApp()">Start</button>
    </div>
    
    <div class="app-container hidden" id="appContainer">
        <div class="sidebar">
            <h3>Categories</h3>
            <ul>
                <li>Work</li>
                <li>Health</li>
                <li>Personal Growth</li>
                <li>Social</li>
                <li>Shopping</li>
                <li>Travel</li>
                <li>Entertainment</li>
                <li onclick="openPermissionsDashboard()">🛡 AI Permissions</li>
            </ul>
        </div>
        <div class="main-container" id="mainApp">
            <div class="header">
                <span>☰ Digital Self - Your Personal AI Context</span>
                <span onclick="openProfile()">👤 Profile</span>
            </div>
            <div class="chat-container" id="chat">
                <div class="message ai">Welcome to Digital Self! How can I assist you?</div>
            </div>
            <div class="input-container">
                <input type="text" id="userInput" placeholder="Enter your request...">
                <button onclick="sendMessage()">➤</button>
            </div>
        </div>
    </div>
    
    <script>
        function startApp() {
            document.getElementById("startPage").classList.add("hidden");
            document.getElementById("appContainer").classList.remove("hidden");
            document.getElementById("mainApp").style.display = "flex";
        }
    </script>
</body>
</html>
