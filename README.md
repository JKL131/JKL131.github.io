<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Strona z Kodem</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #ffffff;
        }

        h1 {
            font-size: clamp(60px, 15vw, 120px);
            margin-bottom: 20px;
            letter-spacing: 10px;
        }

        .container {
            text-align: center;
        }

        input[type="text"] {
            padding: 15px;
            font-size: 20px;
            width: 80%;
            max-width: 400px;
            text-align: center;
            border: 3px solid #000;
            border-radius: 0;
            outline: none;
        }

        #result {
            margin-top: 40px;
            min-height: 50px;
            font-size: 22px;
        }

        .link-success {
            color: #008000;
            text-decoration: underline;
            font-weight: bold;
        }

        .link-hint {
            color: #ff0000;
            text-decoration: underline;
            font-weight: bold;
        }

        button {
            display: none; /* Ukryty, ale pozwala telefonowi wywołać akcję 'Go' */
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>KOD</h1>
        
        <form id="codeForm" onsubmit="handleEnter(event)">
            <input type="text" id="codeInput" placeholder="Wpisz hasło..." autocomplete="off">
            <button type="submit">OK</button>
        </form>

        <div id="result"></div>
    </div>

    <script>
        function handleEnter(event) {
            // Zapobiegamy przeładowaniu strony po kliknięciu Enter
            event.preventDefault();
            
            const inputField = document.getElementById('codeInput');
            const input = inputField.value.trim().toLowerCase();
            const resultDiv = document.getElementById('result');
            
            const correctHash = "zbrodnia i kara";
            const videoUrl = "https://youtu.be/7VqPE2zTOmA?si=Z0XPdSTJl6U_Zcfy";

            if (input === "") {
                resultDiv.innerHTML = "Wpisz coś najpierw...";
                return;
            }

            if (input === correctHash) {
                // Poprawne hasło
                resultDiv.innerHTML = '<a href="' + videoUrl + '" class="link-success" target="_blank">ODKRYTO: KLIKNIJ TUTAJ</a>';
            } else {
                // Błędne hasło - pokazuje wskazówkę
                resultDiv.innerHTML = '<span>WSKAZÓWKA: </span><a href="' + videoUrl + '" class="link-hint" target="_blank">LINK DO POMOCY</a>';
            }
        }
    </script>

</body>
</html>
