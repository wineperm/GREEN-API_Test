<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GREEN-API Test</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        .container {
            max-width: 600px;
            margin: auto;
        }
        .input-group {
            margin-bottom: 10px;
        }
        .input-group label {
            display: block;
            margin-bottom: 5px;
        }
        .input-group input {
            width: 100%;
            padding: 8px;
            box-sizing: border-box;
        }
        .button-group {
            margin-bottom: 20px;
        }
        .button-group button {
            padding: 10px 20px;
            margin-right: 10px;
        }
        .response {
            border: 1px solid #ccc;
            padding: 10px;
            min-height: 100px;
            white-space: pre-wrap;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="input-group">
            <label for="idInstance">idInstance</label>
            <input type="text" id="idInstance" value="1103162795" readonly>
        </div>
        <div class="input-group">
            <label for="apiTokenInstance">apiTokenInstance</label>
            <input type="text" id="apiTokenInstance" value="4e7d60f393114e1b8e25a59e3e29e525ec7593206126457898" readonly>
        </div>
        <div class="button-group">
            <button onclick="getSettings()">getSettings</button>
            <button onclick="getStateInstance()">getStateInstance</button>
            <button onclick="sendMessage()">sendMessage</button>
            <button onclick="sendFileByUrl()">sendFileByUrl</button>
        </div>
        <div class="response" id="response">Response will be displayed here</div>
    </div>

    <script>
        const apiUrl = "https://1103.api.green-api.com"; // Базовый URL API

        async function getSettings() {
            const idInstance = document.getElementById('idInstance').value;
            const apiTokenInstance = document.getElementById('apiTokenInstance').value;
            const url = `${apiUrl}/waInstance${idInstance}/getSettings/${apiTokenInstance}`;

            try {
                const response = await fetch(url);
                const data = await response.json();
                document.getElementById('response').innerText = JSON.stringify(data, null, 2);
            } catch (error) {
                document.getElementById('response').innerText = `Error: ${error.message}`;
            }
        }

        async function getStateInstance() {
            const idInstance = document.getElementById('idInstance').value;
            const apiTokenInstance = document.getElementById('apiTokenInstance').value;
            const url = `${apiUrl}/waInstance${idInstance}/getStateInstance/${apiTokenInstance}`;

            try {
                const response = await fetch(url);
                const data = await response.json();
                document.getElementById('response').innerText = JSON.stringify(data, null, 2);
            } catch (error) {
                document.getElementById('response').innerText = `Error: ${error.message}`;
            }
        }

        async function sendMessage() {
            const idInstance = document.getElementById('idInstance').value;
            const apiTokenInstance = document.getElementById('apiTokenInstance').value;
            const url = `${apiUrl}/waInstance${idInstance}/sendMessage/${apiTokenInstance}`;
            const payload = {
                chatId: "79028326742@c.us", // Замените на ваш chatId
                message: "I use Green-API to send this message to you!"
            };

            try {
                const response = await fetch(url, {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json'
                    },
                    body: JSON.stringify(payload)
                });
                const data = await response.json();
                document.getElementById('response').innerText = JSON.stringify(data, null, 2);
            } catch (error) {
                document.getElementById('response').innerText = `Error: ${error.message}`;
            }
        }

        async function sendFileByUrl() {
            const idInstance = document.getElementById('idInstance').value;
            const apiTokenInstance = document.getElementById('apiTokenInstance').value;
            const url = `${apiUrl}/waInstance${idInstance}/sendFileByUrl/${apiTokenInstance}`;
            const payload = {
                chatId: "79028326742@c.us", // Замените на ваш chatId
                urlFile: "https://github.com/wineperm/Diplom-yc/raw/main/APP/html/KLS_netology_12.07.2004.jpeg", // Прямая ссылка на изображение
                fileName: "KLS_netology_12.07.2004.jpeg", // Имя файла
                caption: "Изображение из GitHub" // Описание файла (необязательно)
            };

            try {
                const response = await fetch(url, {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json'
                    },
                    body: JSON.stringify(payload)
                });
                const data = await response.json();
                document.getElementById('response').innerText = JSON.stringify(data, null, 2);
            } catch (error) {
                document.getElementById('response').innerText = `Error: ${error.message}`;
            }
        }
    </script>
</body>
</html>
