<!DOCTYPE html><html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>⚡BerMatModZ - Access Terminal</title>
  <link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@600&family=Share+Tech+Mono&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      font-family: 'Rajdhani', sans-serif;
      background: linear-gradient(145deg, #070011, #1a0028);
      color: #00ffe1;
      overflow-x: hidden;
    }.banner {
  font-size: 36px;
  text-align: center;
  padding: 30px 10px;
  color: #ff00ff;
  background: linear-gradient(90deg, #0a0010, #1a0033);
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
  font-family: 'Share Tech Mono', monospace;
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
  font-family: 'Rajdhani', sans-serif;
}

.menu {
  background: linear-gradient(145deg, #1f002f, #001122);
  border-left: 5px solid #ff0055;
  border-right: 5px solid #00ffcc;
  color: #f0f0f0;
  font-size: 18px;
  margin-bottom: 20px;
  position: relative;
  padding-left: 100px;
}

.menu img {
  position: absolute;
  left: 10px;
  top: 10px;
  width: 70px;
  height: auto;
  border-radius: 10px;
  border: 1px solid #00ffc3;
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
  <div class="banner">⚡ 𝑩𝑬𝑹𝑴𝑨𝑻𝑴𝑶𝑫𝒁 𝑨𝑪𝑪𝑬𝑺𝑺 (HACK) 𝑺𝒀𝑺𝑻𝑬𝑴 ⚡<br>✦ Bienvenido al dominio de la ciberinteligencia ✦</div>  <div class="center" id="access">
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
        "💣 Hackeo Avanzado de WhatsApp",
        "📸 Control Total de Instagram",
        "📘 Infiltración Facebook Pro",
        "✉️ Espionaje Gmail/Outlook",
        "🔐 Clonación Profesional de WhatsApp",
        "📴 Bloqueo Remoto de Números",
        "🧠 IA Ciberespía (AutoResponder Hack)",
        "🕵️ Hack TikTok Inteligente",
        "🌐 Hackeo de Cuentas VPN",
        "🔍 Escaneo Profundo de Redes Sociales",
        "🌌 Ataque DDoS Personalizado",
        "🔎 Localización por IP y GPS",
        "📦 Intercepción de Paquetes (MITM)",
        "📂 Doxing Automático (Info Target)",
        "🛠️ Generador de Exploits Automático",
        "🧨 Phishing Multiplataforma",
        "⚙️ Clonador de Cuentas Simulado",
        "🔒 ByPass de 2FA / OTP",
        "📱 Suplantación de Identidad",
        "🧬 Análisis Forense Digital"
      ];

      const container = document.getElementById("menu-container");
      titulos.forEach(title => {
        const div = document.createElement("div");
        div.className = "menu";

        const img = document.createElement("img");
        img.src = "https://i.postimg.cc/Y9xCpGMC/Mag-Pic-20250501-185936660-3.jpg";

        div.appendChild(img);
        div.appendChild(document.createTextNode(`> ${title} // by BerMatModZ`));
        container.appendChild(div);
      });
    }
  </script></body>
</html>
