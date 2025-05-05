<!DOCTYPE html><html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Verificación BerMatModZ</title>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Orbitron', sans-serif;
    }
    body {
      background: linear-gradient(135deg, #050505, #0a0a23);
      color: #00ffee;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
    }
    .verificacion-container {
      background: rgba(10, 10, 30, 0.9);
      padding: 30px;
      border-radius: 15px;
      box-shadow: 0 0 20px #00ffee;
      text-align: center;
      position: relative;
    }
    .verificacion-container img {
      width: 200px;
      margin-bottom: 15px;
      border-radius: 10px;
      animation: vibrar 2s infinite;
    }
    @keyframes vibrar {
      0% { transform: rotate(0deg); }
      50% { transform: rotate(1deg); }
      100% { transform: rotate(0deg); }
    }
    input[type="password"] {
      padding: 10px;
      border: none;
      border-radius: 10px;
      margin-top: 15px;
      width: 100%;
      background: #111;
      color: #0ff;
      font-size: 16px;
      text-align: center;
    }
    .toggle-password {
      margin-top: 5px;
      cursor: pointer;
      color: #aaa;
    }
    button {
      margin-top: 15px;
      padding: 10px 25px;
      border: none;
      background: #0ff;
      color: #000;
      font-weight: bold;
      border-radius: 10px;
      cursor: pointer;
    }
    .social-icons {
      margin-top: 20px;
    }
    .social-icons a {
      margin: 0 10px;
      color: #0ff;
      font-size: 24px;
    }
    .contenedor-principal {
      display: none;
      flex-direction: column;
      align-items: center;
      padding: 30px;
    }
    .banner {
      font-size: 24px;
      color: #0ff;
      text-shadow: 0 0 5px #0ff;
      margin-bottom: 20px;
    }
    .info {
      background: #111;
      color: #0ff;
      padding: 15px;
      border-radius: 10px;
      margin-bottom: 20px;
      width: 90%;
      max-width: 600px;
      text-align: center;
      box-shadow: 0 0 15px #0ff;
    }
    .menu-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 20px;
      width: 100%;
      max-width: 900px;
    }
    .menu-item {
      background: #111;
      border: 2px solid #0ff;
      border-radius: 10px;
      padding: 20px;
      text-align: center;
      box-shadow: 0 0 10px #0ff;
    }
  </style>
</head>
<body>
  <div class="verificacion-container" id="verificacion">
    <img src="https://i.postimg.cc/Y9xCpGMC/Mag-Pic-20250501-185936660-3.jpg" alt="BerMat Image">
    <h2>Ingrese Código de Verificación</h2>
    <input type="password" id="codigo" placeholder="Código">
    <div class="toggle-password" onclick="togglePassword()">Mostrar código</div>
    <button onclick="verificarCodigo()">Verificar</button>
    <div class="social-icons">
      <a href="https://wa.me/51937556459" target="_blank"><i class="fab fa-whatsapp"></i></a>
      <a href="https://www.facebook.com/anthzberrocal" target="_blank"><i class="fab fa-facebook"></i></a>
      <a href="https://instagram.com/anthzberrocal" target="_blank"><i class="fab fa-instagram"></i></a>
      <a href="https://github.com/anthzberrocal" target="_blank"><i class="fab fa-github"></i></a>
    </div>
  </div>  <div class="contenedor-principal" id="contenido">
    <div class="banner">⚡Bienvenido a BerMatModZ - Mundo Hacker⚡</div>
    <div class="info">
      <strong>Nombre:</strong> Anth'Zz Berrocal<br>
      <strong>Alias:</strong> BerMatModZ<br>
      <strong>Ubicación:</strong> Andahuaylas, Perú<br>
      <strong>Especialidad:</strong> Bots, Ciberseguridad, Inteligencia Artificial<br>
      <strong>Proyectos:</strong> ⚡BerMat-Bot MD🔥, BerMat_Mods, FAMA<br>
      <strong>Meta:</strong> Ser el hacker más temido del mundo
    </div>
    <div class="menu-grid">
      <div class="menu-item">Hackear WhatsApp</div>
      <div class="menu-item">Clonación de WhatsApp</div>
      <div class="menu-item">Hackear Facebook</div>
      <div class="menu-item">Hackear Instagram</div>
      <div class="menu-item">Bloqueo Remoto de Números</div>
      <div class="menu-item">Control de Cámara Web</div>
      <div class="menu-item">Rastreo de Ubicación IP</div>
      <div class="menu-item">DoS/DDoS Simulado</div>
      <div class="menu-item">Sniffing de Red Local</div>
      <div class="menu-item">Explorador de Puertos</div>
      <div class="menu-item">Bypass de Login</div>
      <div class="menu-item">Keylogger Simulado</div>
      <div class="menu-item">Inyección SQL</div>
      <div class="menu-item">Ataque XSS</div>
      <div class="menu-item">Hackear Gmail (Fake)</div>
      <div class="menu-item">Doxeo Automático</div>
      <div class="menu-item">Phishing Generator</div>
      <div class="menu-item">WebShell Installer</div>
      <div class="menu-item">Interceptar Mensajes SMS</div>
      <div class="menu-item">Hackear Telegram (Fake)</div>
    </div>
  </div>  <script>
    function verificarCodigo() {
      const codigo = document.getElementById("codigo").value;
      if (codigo === "BerMat123") {
        document.getElementById("verificacion").style.display = "none";
        document.getElementById("contenido").style.display = "flex";
      } else {
        alert("Código incorrecto. Intenta nuevamente.");
      }
    }
    function togglePassword() {
      const input = document.getElementById("codigo");
      input.type = input.type === "password" ? "text" : "password";
    }
  </script></body>
</html>
