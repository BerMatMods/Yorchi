<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>BerMatModZ - Sistema Hacker</title>
  <style>
    body {
      margin: 0;
      font-family: 'Courier New', Courier, monospace;
      background: #111111;
      color: #00ff00;
      animation: backgroundAnimation 10s infinite alternate;
    }

    @keyframes backgroundAnimation {
      0% { background-color: #111111; }
      50% { background-color: #222222; }
      100% { background-color: #111111; }
    }

    @import url('https://fonts.googleapis.com/css2?family=Courier+Prime:wght@700&display=swap');

    .login-container {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      padding: 20px;
    }

    .login-box {
      background: rgba(0, 0, 0, 0.8);
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 0 20px #ff0000;
      max-width: 600px;
      width: 90%;
      margin: 10px 0;
      text-align: center;
    }

    .login-box input[type="password"], .login-box input[type="checkbox"] {
      padding: 12px;
      margin-top: 10px;
      width: 100%;
      border-radius: 8px;
      border: none;
      font-size: 20px;
      background-color: #222;
      color: #00ff00;
    }

    .login-box button {
      margin-top: 15px;
      padding: 12px;
      font-size: 20px;
      background-color: #ff0000;
      color: #fff;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: transform 0.2s;
    }

    .login-box button:hover {
      transform: scale(1.05);
    }

    .banner {
      font-size: 32px;
      background: linear-gradient(to right, #ff0000, #8b0000);
      padding: 15px;
      border-radius: 12px;
      margin: 10px 0;
      box-shadow: 0 0 10px #ff0000;
      animation: bannerAnimation 2s infinite;
    }

    @keyframes bannerAnimation {
      0% { color: #ff0000; }
      50% { color: #ff8000; }
      100% { color: #ff0000; }
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
      50% { transform: scale(1.1); opacity: 0.8; }
      100% { transform: scale(1); opacity: 1; }
    }

    .menu-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 15px;
      width: 100%;
    }

    .menu-item {
      background: #222222;
      border: 2px solid #ff0000;
      padding: 15px;
      border-radius: 10px;
      text-align: center;
      transition: transform 0.2s ease-in-out;
      box-shadow: 0 0 10px #ff0000;
    }

    .menu-item:hover {
      transform: scale(1.05);
      background-color: #333333;
    }

    .info-box {
      text-align: center;
      margin-bottom: 20px;
      background: #222;
      box-shadow: 0 0 10px #ff0000;
    }

    .menu-box {
      background: #222;
    }

    .contact-box {
      display: flex;
      justify-content: space-evenly;
      margin-top: 30px;
      background: #333333;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 0 10px #ff0000;
    }

    .contact-box a {
      display: block;
      text-align: center;
      color: #ff0000;
      text-decoration: none;
    }

    .contact-box img {
      width: 50px;
      height: 50px;
      margin: 10px 0;
      border-radius: 50%;
    }
  </style>
</head>
<body>
  <div class="login-container" id="login">
    <div class="login-box">
      <h1>Acceso BerMatModZ</h1>
      <p>Por favor ingresa el código de acceso para continuar con el sistema:</p>
      <input type="password" id="code" placeholder="Código de acceso">
      <label><input type="checkbox" onclick="toggleVisibility()"> Mostrar código</label>
      <button onclick="verifyCode()">Ingresar</button>
      <img src="https://i.postimg.cc/Y9xCpGMC/Mag-Pic-20250501-185936660-3.jpg" alt="Imagen de verificación" />
    </div>
  </div>

  <div class="main-container" id="main" style="display:none">
    <div class="banner">⚡ Bienvenido al sistema BerMatModZ ⚡</div>
    <div class="info-box">
      <h2>Información del Creador</h2>
      <p><strong>Alias:</strong> BerMatModZ</p>
      <p><strong>Nombre:</strong> Anth'Zz Berrocal</p>
      <p><strong>Ubicación:</strong> Andahuaylas</p>
      <p><strong>Proyectos:</strong> ⚡BerMat-Bot MD🔥, BerMat_Mods, Simulador Anonymous, Web Hacker Pro</p>
      <p><strong>Especialidades:</strong> Bots de WhatsApp, Ciberseguridad, Automatización, Estética Hacker</p>
    </div>

    <div class="menu-box">
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
        <!-- Añadir más menús aquí si lo deseas -->
      </div>
    </div>

    <div class="contact-box">
      <a href="https://wa.me/937556459" target="_blank">
        <img src="https://upload.wikimedia.org/wikipedia/commons/6/64/WhatsApp.svg" alt="WhatsApp">
        <p>Contáctame por WhatsApp</p>
      </a>
      <a href="https://github.com/AnthZzBerrocal" target="_blank">
        <img src="https://upload.wikimedia.org/wikipedia/commons/9/91/Octicons-mark-github.svg" alt="GitHub">
        <p>Visita mi GitHub</p>
      </a>
    </div>
  </div>

  <script>
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
  </script>
</body>
</html>
