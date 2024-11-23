<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Survei Program Gratis</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .container {
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            text-align: center;
            position: relative;
            width: 90%;
            max-width: 400px;
            height: 350px;
        }
        h1 {
            font-size: 1.5em;
            color: #333;
        }
        button {
            background-color: #007BFF;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1em;
            position: absolute;
        }
        button:hover {
            background-color: #0056b3;
        }
        #btnYa {
            left: 50%;
            transform: translateX(-50%);
            bottom: 50px;
        }
        #btnTidak {
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
        #btnMakanSiang {
            right: 50%;
            transform: translateX(50%);
            bottom: 50px;
        }
        .message {
            margin-top: 20px;
            font-size: 1.2em;
            color: #555;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Apakah Anda puas dengan program berikut?</h1>
        <p>Sprei Gratis atau Makan Siang Gratis</p>
        <button id="btnYa" onclick="handleAnswer('ya')">Puas</button>
        <button id="btnTidak" onmouseover="moveButton()">Tidak</button>
        <button id="btnMakanSiang" onclick="handleAnswer('makan_siang')">Makan Siang Gratis</button>
        <div class="message" id="message"></div>
    </div>

    <script>
        function handleAnswer(answer) {
            const messageElement = document.getElementById('message');
            if (answer === 'ya') {
                messageElement.textContent = "Terima kasih! Anda merasa puas dengan program Sprei Gratis.";
                messageElement.style.color = "green";
            } else if (answer === 'makan_siang') {
                messageElement.textContent = "Terima kasih! Anda merasa puas dengan program Makan Siang Gratis.";
                messageElement.style.color = "blue";
            }
        }

        function moveButton() {
            const button = document.getElementById('btnTidak');
            const container = document.querySelector('.container');
            
            // Dapatkan ukuran kontainer
            const containerRect = container.getBoundingClientRect();

            // Generate posisi acak
            const newLeft = Math.random() * (containerRect.width - button.offsetWidth);
            const newTop = Math.random() * (containerRect.height - button.offsetHeight);

            // Set posisi baru untuk tombol "Tidak"
            button.style.left = `${newLeft}px`;
            button.style.top = `${newTop}px`;
        }
    </script>
</body>
</html>
