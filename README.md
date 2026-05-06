# Astrologia.br
<!DOCTYPE html><html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Astrologia - Sol e Lua</title>
  <style>
    body {
      margin: 0;
      font-family: 'Georgia', serif;
      background: radial-gradient(circle at top, #0b0b1a, #000);
      color: #e6d9a2;
      text-align: center;
    }header {
  padding: 30px;
  border-bottom: 1px solid #333;
}

h1 {
  margin: 0;
  font-size: 2.5em;
  letter-spacing: 2px;
}

.container {
  padding: 20px;
}

.card {
  background: rgba(20, 20, 40, 0.8);
  margin: 20px auto;
  padding: 20px;
  border-radius: 15px;
  max-width: 500px;
  box-shadow: 0 0 20px rgba(255, 215, 0, 0.1);
}

button {
  background: gold;
  color: black;
  border: none;
  padding: 10px 20px;
  border-radius: 10px;
  cursor: pointer;
  font-weight: bold;
}

button:hover {
  background: #d4af37;
}

  </style>
</head>
<body><header>
  <h1>☀️ Astrologia Solar & Lunar 🌙</h1>
  <p>Posições do Sol e da Lua em tempo real</p>
</header><div class="container">  <div class="card">
    <h2>📍 Sua Localização</h2>
    <p id="location">Carregando...</p>
    <button onclick="getLocation()">Atualizar</button>
  </div>  <div class="card">
    <h2>☀️ Sol</h2>
    <p id="sun">Calculando...</p>
  </div>  <div class="card">
    <h2>🌙 Lua</h2>
    <p id="moon">Calculando...</p>
  </div></div><script>
function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(showPosition);
  } else {
    document.getElementById("location").innerText = "Geolocalização não suportada.";
  }
}

function showPosition(position) {
  const lat = position.coords.latitude;
  const lon = position.coords.longitude;

  document.getElementById("location").innerText = `Latitude: ${lat.toFixed(4)}, Longitude: ${lon.toFixed(4)}`;

  calcularSolLua(lat, lon);
}

function calcularSolLua(lat, lon) {
  const agora = new Date();

  // Simulação simples (pode evoluir depois)
  const hora = agora.getHours();

  let posSol = (hora / 24) * 360;
  let faseLua = (agora.getDate() % 29);

  document.getElementById("sun").innerText = `Posição aproximada: ${posSol.toFixed(2)}° no céu`;
  document.getElementById("moon").innerText = `Fase aproximada: Dia ${faseLua} do ciclo lunar`;
}

// iniciar automático
getLocation();
</script></body>
</html>Astrologia Cabalística 
