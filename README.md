<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>14 de Febrero</title>
  <style>
    /* Estilos generales */
    body {
      margin: 0;
      padding: 0;
      background: #f2f2f2;
      font-family: Arial, sans-serif;
      overflow: hidden; /* Evita barras de desplazamiento */
    }
    /* Contenedor central */
    #container {
      position: relative;
      width: 100vw;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
    }
    h1 {
      margin-bottom: 30px;
      font-size: 2em;
      color: #333;
    }
    /* Estilos para los botones */
    .btn {
      padding: 10px 20px;
      font-size: 16px;
      margin: 10px;
      cursor: pointer;
      border: none;
      border-radius: 5px;
    }
    #yesBtn {
      background-color: #4CAF50;
      color: white;
    }
    /* El botón "No" se posicionará de forma absoluta dentro del contenedor */
    #noBtn {
      background-color: #f44336;
      color: white;
      position: absolute;
    }
    /* Área de mensajes */
    #message {
      margin-top: 20px;
      font-size: 18px;
      color: #333;
    }
  </style>
</head>
<body>
  <div id="container">
    <h1>¿Quieres ser y seguir siendo mi 14 de febrero?</h1>
    <!-- Botón para respuesta afirmativa -->
    <button id="yesBtn" class="btn">Sí</button>
    <!-- Botón para respuesta negativa -->
    <button id="noBtn" class="btn">No</button>
    <!-- Div para mostrar mensajes -->
    <div id="message"></div>
  </div>

  <script>
    const yesBtn = document.getElementById('yesBtn');
    const noBtn = document.getElementById('noBtn');
    const messageDiv = document.getElementById('message');

    // Cuando se haga clic en "Sí"
    yesBtn.addEventListener('click', function() {
      messageDiv.innerHTML = '<strong>Sabia que no te negarías, preciosa.</strong>';
    });

    // Array de mensajes románticos y cómicos para "No"
    const noMessages = [
      "¿Seguro? ¡Eres mi sol!",
      "No puedes negarte a este amor eterno.",
      "El destino nos une, ¡piénsalo bien!",
      "¿Cómo voy a vivir sin ti?",
      "No te vayas, mi corazón late por ti.",
      "Sabes que eres única, ¡aceptalo!",
      "El universo conspira para juntarnos."
    ];

    // Función para obtener un mensaje aleatorio
    function getRandomMessage() {
      return noMessages[Math.floor(Math.random() * noMessages.length)];
    }

    // Función para mover el botón "No" a una posición aleatoria
    function moveNoButton() {
      const container = document.getElementById('container');
      const containerRect = container.getBoundingClientRect();
      const btnWidth = noBtn.offsetWidth;
      const btnHeight = noBtn.offsetHeight;
      // Cálculo del máximo desplazamiento
      const maxLeft = containerRect.width - btnWidth;
      const maxTop = containerRect.height - btnHeight;
      // Posiciones aleatorias
      const randomLeft = Math.random() * maxLeft;
      const randomTop = Math.random() * maxTop;
      noBtn.style.left = randomLeft + 'px';
      noBtn.style.top = randomTop + 'px';

      // Mostrar un mensaje aleatorio en el div de mensajes
      messageDiv.innerHTML = getRandomMessage();
    }

    // Eventos: al pasar el mouse o hacer clic en "No", el botón se mueve
    noBtn.addEventListener('mouseover', moveNoButton);
    noBtn.addEventListener('click', moveNoButton);

    // Posicionar inicialmente el botón "No" en una ubicación aleatoria
    moveNoButton();
  </script>
</body>
</html>
