<!DOCTYPE html><html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>BerMatModZ - Sistema Hacker</title>
  <style>
    body {
      margin: 0;
      font-family: 'Orbitron', sans-serif;
      background: linear-gradient(135deg, #1f2c36, #204052, #283f53);
      color: #00ffff;
    }@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@500&display=swap');

.login-container, .main-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  padding: 20px;
}

.login-box, .info-box, .menu-box {
  background: rgba(0, 0, 0, 0.7);
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 0 20px #00ffff;
  max-width: 600px;
  width: 90%;
  margin: 10px 0;
}

.login-box input[type="password"], .login-box input[type="checkbox"] {
  padding: 10px;
  margin-top: 10px;
  width: 100%;
  border-radius: 5px;
  border: none;
  font-size: 18px;
}

.login-box button {
  margin-top: 10px;
  padding: 10px;
  font-size: 18px;
  background-color: #00ffff;
  color: #000;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

h1, h2, h3 {
  text-align: center;
  color: #00ffff;
}

.banner {
  font-size: 28px;
  background: linear-gradient(to right, #00ffff, #005f73);
  padding: 15px;
  border-radius: 12px;
  margin: 10px 0;
  box-shadow: 0 0 10px #00ffff;
  text-align: center;
}

.login-box img {
  width: 100%;
  height: auto;
  border-radius: 12px;
  margin-top: 15px;
}

.menu-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 15px;
  width: 100%;
}

.menu-item {
  background: #0a0a0a;
  border: 2px solid #00ffff;
  padding: 15px;
  border-radius: 10px;
  text-align: center;
  transition: transform 0.2s ease-in-out;
}

.menu-item:hover {
  transform: scale(1.05);
  background-color: #111;
}

.info-box {
  text-align: center;
  margin-bottom: 20px;
  background: #1b2a33;
  box-shadow: 0 0 10px #00ffff;
}

.menu-box {
  background: #1b2a33;
}

  </style>
</head>
<body>
  <div class="login-container" id="login">
    <div class="login-box">
      <h1>Verificación de Acceso</h1>
      <p>Introduce el código para acceder al sistema:</p>
      <input type="password" id="code" placeholder="Código de acceso">
      <label><input type="checkbox" onclick="toggleVisibility()"> Mostrar código</label>
      <button onclick="verifyCode()">Ingresar</button>
      <img src="https://i.postimg.cc/Y9xCpGMC/Mag-Pic-20250501-185936660-3.jpg" alt="Imagen de verificación" />
    </div>
  </div>  <div class="main-container" id="main" style="display:none">
    <div class="banner">⚡ Bienvenido al sistema BerMatModZ ⚡</div>
    <div class="info-box">
      <h2>Información del Creador</h2>
      <p><strong>Alias:</strong> BerMatModZ</p>
      <p><strong>Nombre:</strong> Anth'Zz Berrocal</p>
      <p><strong>Ubicación:</strong> Andahuaylas</p>
      <p><strong>Proyectos:</strong> ⚡BerMat-Bot MD🔥, BerMat_Mods, Simulador Anonymous, Web Hacker Pro</p>
      <p><strong>Especialidades:</strong> Bots de WhatsApp, Ciberseguridad, Automatización, Estética Hacker</p>
    </div><div class="menu-box">
  <h2>Menús de Ciberataques</h2>
  <div class="menu-grid" id="menu-list">
    <div class="menu-item">
      <h3>Hackeo de WhatsApp</h3>
      <p>Herramienta especializada para hackear cuentas de WhatsApp usando técnicas avanzadas.</p>
    </div>
    <div class="menu-item">
      <h3>Clonación de WhatsApp</h3>
      <p>Clonación de cuentas de WhatsApp, con acceso a conversaciones y archivos multimedia.</p>
    </div>
    <div class="menu-item">
      <h3>Doxeo de objetivo</h3>
      <p>Obtención y filtrado de información personal de un objetivo.</p>
    </div>
    <div class="menu-item">
      <h3>Ataque DDoS</h3>
      <p>Denegación de servicio distribuido para sobrecargar servidores.</p>
    </div>
    <div class="menu-item">
      <h3>Bloqueo de números</h3>
      <p>Bloqueo de números telefónicos mediante diferentes técnicas.</p>
    </div>
    <div class="menu-item">
      <h3>Bypass de Seguridad</h3>
      <p>Evasión de mecanismos de seguridad en plataformas digitales.</p>
    </div>
    <div class="menu-item">
      <h3>Exploración de puertos</h3>
      <p>Exploración y escaneo de puertos en redes para identificar vulnerabilidades.</p>
    </div>
    <div class="menu-item">
      <h3>Sniffing de redes</h3>
      <p>Intercepción de tráfico de red para capturar paquetes sensibles.</p>
    </div>
    <div class="menu-item">
      <h3>Interceptación de tráfico</h3>
      <p>Captura de datos entre un usuario y servidor para obtener credenciales.</p>
    </div>
    <div class="menu-item">
      <h3>Phishing avanzado</h3>
      <p>Creación de sitios web falsos para robar información sensible.</p>
    </div>
  </div>
</div>

  </div>  <script>
    const validCode = "BERMAT123";
    const loginDiv = document.getElementById("login");
    const mainDiv = document.getElementById("main");

    function verifyCode() {
      const code = document.getElementById("code").value;
      if (code === validCode) {
        loginDiv.style.display = "none";
        mainDiv.style.display = "flex";
      } else {
        alert("Código incorrecto. Intenta nuevamente.");
      }
    }

    function toggleVisibility() {
      const input = document.getElementById("code");
      input.type = input.type === "password" ? "text" : "password";
    }
  </script></body>
</html>
