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
    }

    @import url('https://fonts.googleapis.com/css2?family=Courier+Prime:wght@700&display=swap');

    .login-container, .main-container {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      padding: 20px;
    }

    .login-box, .info-box, .menu-box {
      background: rgba(0, 0, 0, 0.8);
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 0 20px #ff0000;
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
      background-color: #222;
      color: #00ff00;
    }

    .login-box button {
      margin-top: 10px;
      padding: 10px;
      font-size: 18px;
      background-color: #ff0000;
      color: #fff;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    h1, h2, h3 {
      text-align: center;
      color: #ff0000;
    }

    .banner {
      font-size: 32px;
      background: linear-gradient(to right, #ff0000, #8b0000);
      padding: 15px;
      border-radius: 12px;
      margin: 10px 0;
      box-shadow: 0 0 10px #ff0000;
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

    .menu-item h3 {
      font-size: 24px;
      color: #ff0000;
      font-weight: bold;
    }

    .menu-item p {
      font-size: 16px;
      color: #ffffff;
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
      <h1>Verificación de Acceso</h1>
      <p>Introduce el código para acceder al sistema:</p>
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
        <div class="menu-item">
          <h3>Hackeo de redes sociales</h3>
          <p>Acceso no autorizado a plataformas sociales como Facebook, Instagram, Twitter, etc.</p>
        </div>
        <div class="menu-item">
          <h3>Manipulación de base de datos</h3>
          <p>Extracción o modificación de datos en bases de datos sin autorización.</p>
        </div>
        <div class="menu-item">
          <h3>Inyección SQL</h3>
          <p>Exploit de vulnerabilidades en bases de datos usando inyecciones SQL.</p>
        </div>
        <div class="menu-item">
          <h3>Hackeo de correos electrónicos</h3>
          <p>Acceso a cuentas de correo mediante técnicas de hacking específicas.</p>
        </div>
        <div class="menu-item">
          <h3>Hackeo de contraseñas</h3>
          <p>Cracking de contraseñas de usuarios mediante
