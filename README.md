# jeuduchiffre
trouve le bon chiffre 
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Jeu du Nombre Magique</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background: #f0f0f0;
      padding: 50px;
    }
    h1 {
      color: #333;
    }
    input[type="number"] {
      padding: 10px;
      font-size: 1.2rem;
      width: 100px;
    }
    button {
      padding: 10px 20px;
      font-size: 1rem;
      margin-top: 10px;
      cursor: pointer;
    }
    #message {
      margin-top: 20px;
      font-size: 1.2rem;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>🎯 Trouve le nombre magique !</h1>
  <p>Devine un nombre entre 1 et 1000</p>
  <input type=\"number\" id=\"guess\" min=\"1\" max=\"1000\">
  <button onclick="checkGuess()">Deviner</button>
  <div id="message"></div>
  <script>
    let secretNumber = Math.floor(Math.random() * 1000) + 1;
    let attempts = 0;

    function checkGuess() {
      const guess = Number(document.getElementById('guess').value);
      const message = document.getElementById('message');
      attempts++;

      if (!guess || guess < 1 || guess > 20) {
        message.textContent = "Entre un nombre entre 1 et 1000 !";
        return;
      }

      if (guess === secretNumber) {
        message.textContent = `Bravo ! Tu as trouvé en ${attempts} essais.`;
        message.style.color = 'green';
      } else if (guess < secretNumber) {
        message.textContent = "C'est plus !";
        message.style.color = 'blue';
      } else {
        message.textContent = "C'est moins !";
        message.style.color = 'orange';
      }
    }
  </script>
</body>
</html>
