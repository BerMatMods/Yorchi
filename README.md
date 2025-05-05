<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>⚡BerMatModZ Access⚡</title>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@600&family=Share+Tech+Mono&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0; padding: 0; box-sizing: border-box;
      font-family: 'Share Tech Mono', monospace;
    }
    body {
      background: radial-gradient(ellipse at center, #000428 0%, #004e92 100%);
      color: #00ffcc;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 20px;
    }
    .container {
      width: 100%;
      max-width: 600px;
      background: #111;
      padding: 30px;
      border-radius: 20px;
      box-shadow: 0 0 20px #00ffff;
      text-align: center;
    }
    .container img {
      width: 200px;
      border-radius: 20px;
      animation: vibrar 2s infinite alternate;
    }
    @keyframes vibrar {
      0% { transform: scale(1); }
      100% { transform: scale(1.03); }
    }
    .input-group {
      margin-top: 20px;
    }
    input[type="password"] {
      padding: 10px;
      width: 70%;
      border: none;
      border-radius: 10px;
      background: #222;
      color: #00ffcc;
      font-size: 16px;
      text-align: center;
    }
    .show-pass {
      margin-top: 10px;
      font-size: 14px;
      color: #ccc;
    }
    button {
      margin-top: 20px;
      padding: 10px 20px;
      background: #00ffcc;
      border: none;
      color: #000;
      font-size: 16px;
      border-radius: 10px;
      cursor: pointer;
    }
    .hidden { display: none; }

    /* Segunda pantalla */
    #main-content {
      text-align: left;
    }
    .banner {
      text-align: center;
      font-size: 24px;
      color: #0ff;
      margin-bottom: 15px;
      font-family: 'Orbitron', sans-serif;
    }
    .info-box {
      background: #111;
      border: 2px solid #00ffff;
      padding: 15px;
      margin-bottom: 20px;
      border-radius: 15px;
      color: #fff;
    }
    .menus {
      display: flex;
      flex-wrap: wrap;
      gap: 15px;
    }
    .menu-item {
      flex: 1 1 calc(50% - 20px);
      background: #222;
      padding: 15px;
      border: 2px solid #0ff;
      border-radius: 15px;
      font-size: 14px;
      color: #fff;
      transition: 0.3s;
    }
    .menu-item:hover {
      transform: scale(1.05);
      background: #0ff;
      color: #000;
    }
    @media screen and (max-width: 600px) {
      .menu-item {
        flex: 1 1 100%;
      }
    }
  </style>
</head>
<body>
  <div class="container" id="login">
    <img src="https://i.postimg.cc/Y9xCpGMC/Mag-Pic-20250501-185936660-3.jpg" alt="BerMat Image" />
    <h2 style="margin-top: 20px;">INGRESA CÓDIGO DE VERIFICACIÓN</h2>
    <div class="input-group">
      <input type="password" id="codeInput" placeholder="Código secreto" />
    </div>
    <div class="show-pass">
      <input type="checkbox" onclick="togglePassword()"> Mostrar código
    </div>
    <button onclick="verifyCode()">Ingresar</button>
  </div>

  <div class="container hidden" id="main-content">
    <div class="banner">⚡BIENVENIDO A BERMATMODZ - ZONA PRIVADA DE CIBERATAQUE⚡</div>
    <div class="info-box">
      <strong>Creador:</strong> Anth'Zz Berrocal<br>
      <strong>Alias:</strong> BerMatModZ<br>
      <strong>Ubicación:</strong> Andahuaylas<br>
      <strong>Especialidad:</strong> Ciberseguridad & Programación<br>
      <strong>Contacto:</strong> <br>
      WhatsApp: 937556459<br>
      Proyecto: ⚡BerMat-Bot MD🔥<br>
    </div>

    <div class="menus">
      <!-- 20 menús de hacking -->
      <div class="menu-item">Hackeo de WhatsApp</div>
      <div class="menu-item">Clonación de WhatsApp</div>
      <div class="menu-item">Bloqueo remoto de números</div>
      <div class="menu-item">DoS a servidores débiles</div>
      <div class="menu-item">Rastreo de IP geolocalizada</div>
      <div class="menu-item">Bypass de autenticación</div>
      <div class="menu-item">Ataque de fuerza bruta</div>
      <div class="menu-item">Escáner de puertos avanzados</div>
      <div class="menu-item">Keylogger remoto</div>
      <div class="menu-item">Sniffer de red</div>
      <div class="menu-item">Suplantación de identidad</div>
      <div class="menu-item">Hacking de Instagram</div>
      <div class="menu-item">Phishing avanzado</div>
      <div class="menu-item">Troyano personalizado</div>
      <div class="menu-item">Rooting y exploits</div>
      <div class="menu-item">Cifrados invisibles</div>
      <div class="menu-item">Control de cámaras</div>
      <div class="menu-item">DoXing completo</div>
      <div class="menu-item">Análisis de vulnerabilidades</div>
      <div class="menu-item">Despliegue de payloads</div>
    </div>
  </div>

  <script>
    function togglePassword() {
      const input = document.getElementById("codeInput");
      input.type = input.type === "password" ? "text" : "password";
    }
    function verifyCode() {
      const input = document.getElementById("codeInput").value;
      if (input === "BerMat123") {
        document.getElementById("login").classList.add("hidden");
        document.getElementById("main-content").classList.remove("hidden");
      } else {
        alert("Código incorrecto. Intenta de nuevo.");
      }
    }
  </script>
</body>
</html>
