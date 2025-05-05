<!DOCTYPE html><html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>BerMatModZ - Sistema Hacker</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700&family=Share+Tech+Mono&display=swap');body {
  margin: 0;
  font-family: 'Orbitron', sans-serif;
  background: #0a0a0a;
  color: #00ffcc;
  animation: backgroundAnimation 10s infinite alternate;
}

@keyframes backgroundAnimation {
  0% { background-color: #0a0a0a; }
  50% { background-color: #111111; }
  100% { background-color: #0a0a0a; }
}

.login-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  padding: 20px;
}

.login-box {
  background: rgba(0, 0, 0, 0.85);
  padding: 30px;
  border-radius: 12px;
  box-shadow: 0 0 25px #00ffcc;
  max-width: 600px;
  width: 90%;
  text-align: center;
}

.login-box input[type="password"], .login-box input[type="checkbox"] {
  padding: 12px;
  margin-top: 10px;
  width: 100%;
  border-radius: 8px;
  border: none;
  font-size: 20px;
  background-color: #111;
  color: #00ffcc;
  font-family: 'Share Tech Mono', monospace;
}

.login-box button {
  margin-top: 15px;
  padding: 12px;
  font-size: 20px;
  background-color: #00ffcc;
  color: #000;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: transform 0.2s;
  font-weight: bold;
}

.login-box button:hover {
  transform: scale(1.05);
  background-color: #00e6b8;
}

.banner {
  font-size: 36px;
  background: linear-gradient(to right, #00ffcc, #005f5f);
  padding: 20px;
  border-radius: 12px;
  margin: 10px 0;
  box-shadow: 0 0 15px #00ffcc;
  animation: bannerAnimation 2s infinite;
  text-align: center;
  font-family: 'Orbitron', sans-serif;
}

@keyframes bannerAnimation {
  0% { color: #00ffcc; }
  50% { color: #00b3b3; }
  100% { color: #00ffcc; }
}

.login-box img {
  width: 100%;
  height: auto;
  border-radius: 12px;
  margin-top: 20px;
  animation: imageAnimation 3s infinite;
}

@keyframes imageAnimation {
  0% { transform: scale(1); opacity: 1; }
  50% { transform: scale(1.1); opacity: 0.85; }
  100% { transform: scale(1); opacity: 1; }
}

.menu-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  width: 100%;
}

.menu-item {
  background: #111111;
  border: 2px solid #00ffcc;
  padding: 20px;
  border-radius: 10px;
  text-align: center;
  transition: transform 0.2s;
  box-shadow: 0 0 10px #00ffcc;
  font-family: 'Share Tech Mono', monospace;
}

.menu-item:hover {
  transform: scale(1.05);
  background-color: #1a1a1a;
}

.info-box {
  text-align: center;
  margin-bottom: 20px;
  background: #111;
  padding: 15px;
  border-radius: 10px;
  box-shadow: 0 0 15px #00ffcc;
}

.contact-box {
  display: flex;
  justify-content: space-evenly;
  flex-wrap: wrap;
  margin-top: 30px;
  background: #111;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 0 10px #00ffcc;
}

.contact-box a {
  text-align: center;
  color: #00ffcc;
  text-decoration: none;
  margin: 10px;
}

.contact-box img {
  width: 50px;
  height: 50px;
  border-radius: 50%;
}

  </style>
</head>
<body>
  <div class="login-container" id="login">
    <div class="login-box">
      <h1>Verificación BerMatModZ</h1>
      <p>Introduce el código de seguridad para continuar:</p>
      <input type="password" id="code" placeholder="Código: BerMat123">
      <label><input type="checkbox" onclick="toggleVisibility()"> Mostrar código</label>
      <button onclick="verifyCode()">Entrar</button>
      <img src="https://i.postimg.cc/Y9xCpGMC/Mag-Pic-20250501-185936660-3.jpg" alt="Verificación" />
    </div>
  </div>  <div class="main-container" id="main" style="display:none">
    <div class="banner">⚡ Bienvenido al sistema BerMatModZ ⚡</div><div class="info-box">
  <h2>Información del Creador</h2>
  <p><strong>Alias:</strong> BerMatModZ</p>
  <p><strong>Nombre:</strong> Anth'Zz Berrocal</p>
  <p><strong>Ubicación:</strong> Andahuaylas</p>
  <p><strong>Proyectos:</strong> ⚡BerMat-Bot MD🔥, BerMat_Mods, Web Hacker Pro</p>
  <p><strong>Especialidades:</strong> Ciberseguridad, Bots IA, Simulaciones Hacker</p>
</div>

<div class="menu-grid">
  <div class="menu-item"><h3>Hackeo de WhatsApp</h3></div>
  <div class="menu-item"><h3>Clonación de WhatsApp</h3></div>
  <div class="menu-item"><h3>Doxeo Profesional</h3></div>
  <div class="menu-item"><h3>IP Tracker</h3></div>
  <div class="menu-item"><h3>Escáner de Puertos</h3></div>
  <div class="menu-item"><h3>Fuerza Bruta de Gmail</h3></div>
  <div class="menu-item"><h3>Herramienta de Phishing</h3></div>
  <div class="menu-item"><h3>Keylogger Remoto</h3></div>
  <div class="menu-item"><h3>Secuestro de Sesiones</h3></div>
  <div class="menu-item"><h3>Sniffer de Red</h3></div>
  <div class="menu-item"><h3>Generador de Hash</h3></div>
  <div class="menu-item"><h3>Decodificador Base64</h3></div>
  <div class="menu-item"><h3>Analizador de Malware</h3></div>
  <div class="menu-item"><h3>Simulador de Terminal</h3></div>
  <div class="menu-item"><h3>Control Remoto de PC</h3></div>
  <div class="menu-item"><h3>Auto-Spam de Correos</h3></div>
  <div class="menu-item"><h3>Simulador de Ataques DDoS</h3></div>
  <div class="menu-item"><h3>Acceso Root Remoto</h3></div>
  <div class="menu-item"><h3>Explorador de Archivos</h3></div>
  <div class="menu-item"><h3>Bot de Inteligencia Artificial</h3></div>
</div>

<div class="contact-box">
  <a href="https://wa.me/937556459" target="_blank">
    <img src="https://upload.wikimedia.org/wikipedia/commons/6/64/WhatsApp.svg" alt="WhatsApp">
    <p>WhatsApp</p>
  </a>
  <a href="https://github.com/AnthZzBerrocal" target="_blank">
    <img src="https://upload.wikimedia.org/wikipedia/commons/9/91/Octicons-mark-github.svg" alt="GitHub">
    <p>GitHub</p>
  </a>
</div>

  </div>  <script>
    function toggleVisibility() {
      var codeInput = document.getElementById('code');
      codeInput.type = (codeInput.type === 'password') ? 'text' : 'password';
    }

    function verifyCode() {
      var inputCode = document.getElementById('code').value;
      if (inputCode === "BerMat123") {
        document.getElementById('login').style.display = 'none';
        document.getElementById('main').style.display = 'block';
      } else {
        alert('Código incorrecto. Intenta de nuevo.');
      }
    }
  </script></body>
</html>
