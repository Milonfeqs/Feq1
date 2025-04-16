<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>site feq1</title>
  <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap" rel="stylesheet">
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" rel="stylesheet">
  <style>
    body {
      margin: 0;
      height: 100vh;
      font-family: 'Press Start 2P', cursive;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      color: white;
      overflow: hidden;
      background-color: black; /* Fundo inicial preto */
      transition: background-color 0.5s, color 0.5s;
    }

    /* Texto no topo */
    .top-text {
      font-size: 28px;
      margin-bottom: 20px;
      text-align: center;
    }

    /* Botões */
    .buttons {
      display: flex;
      gap: 20px;
      margin-bottom: 30px;
    }

    .buttons a {
      padding: 10px 20px;
      background-color: #444;
      color: white;
      font-size: 18px;
      text-decoration: none;
      border-radius: 5px;
      transition: background-color 0.3s ease, transform 0.3s ease;
    }

    .buttons a:hover {
      background-color: #666;
      transform: scale(1.1);
    }

    /* Barra de pesquisa */
    .search-bar {
      position: absolute;
      top: 20px;
      right: 20px;
      padding: 10px;
      background-color: rgba(0, 0, 0, 0.6);
      color: white;
      border: 2px solid #fff;
      border-radius: 5px;
      font-size: 16px;
      width: 200px;
    }

    .search-bar::placeholder {
      color: #ccc;
    }

    /* Girassóis animados */
    .sunflowers {
      position: absolute;
      top: 10%;
      left: 10%;
      width: 100%;
      height: 100%;
      display: flex;
      justify-content: space-around;
      flex-wrap: wrap;
      animation: sunflowerAnimation 10s infinite;
    }

    .sunflower {
      width: 50px;
      height: 50px;
      background-color: yellow;
      border-radius: 50%;
      animation: sunflowerBloom 2s infinite alternate;
    }

    @keyframes sunflowerAnimation {
      0% { transform: translateX(0); }
      50% { transform: translateX(100px); }
      100% { transform: translateX(0); }
    }

    @keyframes sunflowerBloom {
      0% { transform: scale(0.5); }
      100% { transform: scale(1); }
    }

    /* Botão de alternar fundo */
    .toggle-button {
      position: absolute;
      bottom: 20px;
      left: 20px;
      padding: 10px 20px;
      background-color: #444;
      color: white;
      font-size: 18px;
      text-decoration: none;
      border-radius: 5px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    .toggle-button:hover {
      background-color: #666;
    }

    /* Botão oculto transparente */
    .hidden-button {
      position: absolute;
      top: 50%;
      right: 50%;
      width: 100px;
      height: 50px;
      opacity: 0; /* Tornando o botão invisível */
      z-index: -1; /* Botão escondido atrás dos outros elementos */
    }
  </style>
</head>
<body>

  <!-- Texto no topo -->
  <div class="top-text">site feq1</div>

  <!-- Botões de redirecionamento -->
  <div class="buttons">
    <a href="https://github.com" target="_blank">GitHub</a>
    <a href="https://eaglercraft.com/" target="_blank">Eaglercraft</a>
    <a href="https://www.youtube.com/watch?v=v9jJGXgxNP4" target="_blank">Girassol</a>
  </div>

  <!-- Barra de pesquisa -->
  <input type="text" class="search-bar" placeholder="Pesquise: net, yt, force, mine..." id="searchInput">

  <!-- Girassóis no fundo -->
  <div class="sunflowers">
    <div class="sunflower"></div>
    <div class="sunflower"></div>
    <div class="sunflower"></div>
    <div class="sunflower"></div>
  </div>

  <!-- Botão para alternar o fundo -->
  <button class="toggle-button" onclick="toggleBackground()">Alterar Fundo</button>

  <!-- Botão oculto para redirecionar -->
  <button class="hidden-button" onclick="redirectToHiddenSite()">Ir para meu site</button>

  <script>
    // Função para alternar o fundo e a cor dos botões
    function toggleBackground() {
      let body = document.body;
      let buttons = document.querySelectorAll('.buttons a');
      let isBlack = body.style.backgroundColor === 'black';
      
      // Alterna fundo entre preto e branco
      body.style.backgroundColor = isBlack ? 'white' : 'black';
      body.style.color = isBlack ? 'black' : 'white';
      
      // Altera a cor dos botões
      buttons.forEach(button => {
        button.style.backgroundColor = isBlack ? '#444' : '#888';
        button.style.color = isBlack ? 'white' : 'black';
      });
    }

    // Função para buscar e redirecionar com base na pesquisa
    document.getElementById('searchInput').addEventListener('input', function(event) {
      const query = event.target.value.toLowerCase();

      if (query.includes('force')) {
        window.location.href = "https://play.geforcenow.com/mall/#/layout/games";
      } else if (query.includes('mine')) {
        window.location.href = "https://eaglercraft.com/";
      } else if (query.includes('net')) {
        window.location.href = "https://portalnetescola.educacao.go.gov.br/";
      } else if (query.includes('yt')) {
        window.location.href = "https://www.youtube.com/";
      }
    });

    // Função para redirecionar para o site oculto
    function redirectToHiddenSite() {
      window.location.href = "https://www.seusiteexemplo.com";  // Substitua pelo seu site
    }
  </script>

</body>
</html>
