<!DOCTYPE html><html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>⚡ BerMatModZ - Acceso Secreto</title>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron&family=Share+Tech+Mono&display=swap" rel="stylesheet">
  <style>
    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: 'Share Tech Mono', monospace;
      background: linear-gradient(to bottom right, #000428, #004e92);
      color: #00ffee;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      padding: 20px;
    }
    #authBox {
      background: #011627;
      padding: 30px;
      border-radius: 15px;
      border: 3px solid #00ffee;
      text-align: center;
      box-shadow: 0 0 15px #00ffff;
    }
    input[type="password"] {
      padding: 10px;
      border-radius: 10px;
      border: 1px solid #00ffee;
      width: 250px;
      font-size: 16px;
      margin-top: 10px;
      font-family: 'Share Tech Mono';
    }
    .toggle {
      margin-top: 10px;
      color: #00ffee;
      font-size: 14px;
    }
    button {
      margin-top: 15px;
      padding: 10px 20px;
      border: none;
      background: #00ffee;
      color: #000;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
      border-radius: 10px;
    }
    img {
      max-width: 200px;
      border-radius: 10px;
      margin-bottom: 20px;
      border: 2px solid #00ffee;
    }
    #mainContent { display: none; }
  </style>
</head>
<body>
  <div id="authBox">
    <img src="https://i.postimg.cc/Y9xCpGMC/Mag-Pic-20250501-185936660-3.jpg" alt="BERMATMODZ">
    <h2>Ingresa tu código de verificación</h2>
    <input type="password" id="codigo" placeholder="Código Secreto">
    <div class="toggle">
      <input type="checkbox" onclick="mostrarClave()"> Mostrar código
    </div>
    <button onclick="verificarCodigo()">Ingresar</button>
  </div>  <div id="mainContent">
    <script>
      const menus = [
        "Hackeo de WhatsApp", "Clonación Total de Redes", "Sniffer WiFi Remoto", "Inyección SQL y Bypass",
        "Bloqueo/Desbloqueo Números", "Keylogger Silencioso", "Obtención de IP y Doxeo", "Hackeo de Telegram",
        "Suplantación de Identidad", "Control Total de Sistema", "Hack Ético Social", "Desencriptación de Mensajes",
        "Simulador de Phishing", "Ataques DDOS", "Cifrado de Archivos", "Shell Reverse Netcat",
        "Escaneo de Puertos", "Troyano para Android", "Robo de Tokens", "Phishing Web",
        "Botnet Builder", "Panel F.A.M.A Pro", "Rastreo de Ubicación", "Hack de Cámaras IP",
        "Deep Web Scanner", "Clonación Apps Bancarias", "Interceptar Tráfico", "Explotación de Bugs",
        "Bypass Antivirus", "Hackeo de Gmail", "Romper Contraseñas", "Simulación Red Oscura",
        "Keylogger de Voz", "Hackeo Discord", "Fuerza Bruta Web", "Backdoor Inyectado",
        "Hack GPS", "Manipular Sesiones", "Hacker Visualizador", "BerMat Cloner v2.5"
      ];document.write('<h1 style="font-family: Orbitron, sans-serif; text-align:center; color:#00f5ff;">⚔️ PANEL DE CIBERATAQUES BERMATMODZ ⚔️</h1>');
  document.write('<div style="max-width:1200px; margin:auto; display:grid; grid-template-columns:repeat(auto-fit, minmax(260px, 1fr)); gap:20px;">');

  menus.forEach(menu => {
    document.write(`
      <div style="background:#011627; border:2px solid #00ffee; padding:20px; border-radius:15px; text-align:center; box-shadow:0 0 15px #00ffee;">
        <img src='https://i.postimg.cc/Y9xCpGMC/Mag-Pic-20250501-185936660-3.jpg'>
        <h3 style='color:#00ffee;'>${menu}</h3>
      </div>
    `);
  });

  document.write('</div>');
</script>

  </div>  <script>
    function verificarCodigo() {
      const codigo = document.getElementById("codigo").value;
      if (codigo === "BERMAT123") {
        document.getElementById("authBox").style.display = "none";
        document.getElementById("mainContent").style.display = "block";
      } else {
        alert("Código incorrecto. Intenta de nuevo.");
      }
    }
    function mostrarClave() {
      const input = document.getElementById("codigo");
      input.type = input.type === "password" ? "text" : "password";
    }
  </script></body>
</html>
