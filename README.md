<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Glitchy.exe</title>
<style>
body {
  margin: 0;
  background: black;
  color: red;
  font-family: monospace;
  overflow: hidden;
  text-align: center;
}

#virus {
  font-size: 80px;
  margin-top: 100px;
  transition: transform 0.2s;
}

#text {
  margin-top: 40px;
  font-size: 24px;
  min-height: 60px;
}

.glitch {
  animation: glitch 0.1s infinite;
}

@keyframes glitch {
  0% { transform: translate(2px, -2px); }
  25% { transform: translate(-2px, 2px); }
  50% { transform: translate(2px, 2px); }
  75% { transform: translate(-2px, -2px); }
  100% { transform: translate(0, 0); }
}

.flash {
  background: darkred;
}
</style>
</head>
<body>

<div id="virus">🦠</div>
<div id="text">Iniciando Glitchy.exe...</div>

<script>
let messages = [
  "Escaneando dispositivo...",
  "Anomalía detectada...",
  "Ya Se Dónde Vives...",
  "No debiste abrir esto.",
  "Ahora estoy dentro de tu pantalla.",
  "No mires atrás.",
  "Ya Estoy en tu Casa.",
  "ERROR REALIDAD 404",
  "..."
];

let i = 0;
let text = document.getElementById("text");
let virus = document.getElementById("virus");

function nextMessage() {
  if (i < messages.length) {
    text.innerHTML = messages[i];
    virus.classList.add("glitch");
    i++;
    setTimeout(nextMessage, 2000);
  } else {
    jumpScare();
  }
}

function jumpScare() {
  document.body.classList.add("flash");
  virus.innerHTML = "👁";
  text.innerHTML = "GLITCHY TE ESTÁ OBSERVANDO";
  virus.style.transform = "scale(2)";
}

setTimeout(nextMessage, 2000);
</script>

</body>
</html>
