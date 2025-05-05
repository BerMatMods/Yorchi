<!DOCTYPE html><html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>⚡BerMatModZ - Access Terminal</title>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@700&family=Major+Mono+Display&family=Share+Tech+Mono&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      font-family: 'Share Tech Mono', monospace;
      background: linear-gradient(145deg, #0c0014, #140021);
      color: #00ffc3;
      overflow-x: hidden;
    }.banner {
  font-family: 'Orbitron', sans-serif;
  font-size: 36px;
  text-align: center;
  padding: 30px 10px;
  color: #ff00ff;
  background: linear-gradient(90deg, #110011, #220022);
  text-shadow: 0 0 20px #00ffcc, 0 0 10px #ff00ff;
  border-bottom: 4px solid #ff0055;
  box-shadow: 0 0 25px #ff00ff;
  letter-spacing: 2px;
}

.center {
  text-align: center;
  margin-top: 8vh;
}

.access-img {
  width: 250px;
  max-width: 90%;
  border: 3px solid #00ffc3;
  border-radius: 20px;
  box-shadow: 0 0 25px #00ffc3;
}

input, button {
  margin: 10px;
  padding: 10px;
  font-size: 18px;
  border: 2px solid #00ffc3;
  border-radius: 10px;
  background: black;
  color: #00ffc3;
  font-family: 'Major Mono Display', monospace;
}

button:hover {
  background: #00ffc3;
  color: black;
  box-shadow: 0 0 10px #00ffc3;
}

.hidden { display: none; }

.info, .menu {
  background: #0f001f;
  border: 2px solid #00ffc3;
  margin: 20px auto;
  padding: 20px;
  border-radius: 15px;
  width: 90%;
  max-width: 800px;
  box-shadow: 0 0 20px #ff00ff;
  font-family: 'Major Mono Display', monospace;
}

.menu {
  background: linear-gradient(145deg, #1f002f, #001122);
  border-left: 5px solid #ff0055;
  border-right: 5px solid #00ffcc;
  color: #f0f0f0;
  font-size: 18px;
  margin-bottom: 10px;
}

footer {
  text-align: center;
  padding: 10px;
  font-size: 14px;
  color: #00ffc3;
  background: #000;
  font-family: 'Share Tech Mono', monospace;
}

  </style>
</head>
<body>
  <div class="banner">⚡ 𝑩𝑬𝑹𝑴𝑨𝑻𝑴𝑶𝑫𝒁 𝑨𝑪𝑪𝑬𝑺𝑺 𝑺𝒀𝑺𝑻𝑬𝑴 ⚡<br>✦ Bienvenido al dominio de la ciberinteligencia ✦</div>  <div class="center" id="access">
    <img src="https://i.postimg.cc/Y9xCpGMC/Mag-Pic-20250501-185936660-3.jpg" alt="Imagen Verificación" class="access-img">
    <h2>🔐 Ingresa el código de acceso</h2>
    <input type="password" id="code" placeholder="Código secreto">
    <br>
    <button onclick="verificarCodigo()">ENTRAR A LA DIMENSIÓN BERMAT</button>
  </div>  <div class="hidden" id="contenido">
    <div class="info">
      <h2>✅ ACCESO CONCEDIDO A ⚡BERMATMODZ🔥</h2>
      <p><strong>Nombre:</strong> Anth'Zz Berrocal</p>
      <p><strong>Alias:</strong> BerMatModZ</p>
      <p><strong>Zona:</strong> Andahuaylas, Perú</p>
      <p><strong>Proyectos:</strong> BerMat_Mods, ⚡BerMat-Bot MD🔥, F.A.M.A</p>
      <p><strong>Especialidad:</strong> Bots de WhatsApp, Inteligencia Artificial, Ciberseguridad</p>
    </div><div id="menu-container"></div>

  </div>  <footer>
    Creado por: Anth'Zz Berrocal | Alias: BerMatModZ | "El código es mi espada, la red es mi reino."
  </footer>  <script>
    const codCorrecto = "BERMAT123";

    function verificarCodigo() {
      const input = document.getElementById("code").value;
      if (input === codCorrecto) {
        document.getElementById("access").classList.add("hidden");
        document.getElementById("contenido").classList.remove("hidden");
        generarMenus();
      } else {
        alert("Código incorrecto. Intenta nuevamente.");
      }
    }

    function generarMenus() {
      const titulos = [
        "💥 Inyección SQL en Portales Web",
        "📡 Escaneo de Redes Anónimas",
        "🔓 Clonación Avanzada de WhatsApp",
        "🧠 Hack AI - Respuestas Automáticas",
        "🛰️ Satélite Tracker OSINT",
        "🧬 Phishing Personalizado por Región",
        "⛓️ DDoS Controlador BerMat_F.A.M.A",
        "⚙️ Panel CiberAtaque Multitarget",
        "💻 Console Exploit Builder",
        "🔍 Análisis Deep Web Pro"
      ];

      const container = document.getElementById("menu-container");
      titulos.forEach(title => {
        const div = document.createElement("div");
        div.className = "menu";
        div.textContent = `> ${title}`;
        container.appendChild(div);
      });
    }
  </script></body>
</html>
