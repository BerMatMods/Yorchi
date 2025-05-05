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
        ["Hackeo de WhatsApp", "Acceso no autorizado a cuentas de WhatsApp mediante exploits y técnicas avanzadas."],
        ["Clonación Total de Redes", "Duplicación y control de redes sociales incluyendo perfiles, chats y más."],
        ["Sniffer WiFi Remoto", "Captura de tráfico de redes WiFi a distancia y monitoreo de dispositivos conectados."],
        ["Inyección SQL y Bypass", "Acceso a bases de datos vulnerables y omisión de autenticaciones."],
        ["Bloqueo/Desbloqueo Números", "Control sobre listas negras de operadoras y desbloqueo de líneas."],
        ["Keylogger Silencioso", "Captura de pulsaciones del teclado sin ser detectado."],
        ["Obtención de IP y Doxeo", "Recolección de datos personales y dirección IP de objetivos."],
        ["Hackeo de Telegram", "Infiltración en cuentas de Telegram y lectura de conversaciones cifradas."],
        ["Suplantación de Identidad", "Falsificación de identidad en múltiples plataformas sociales."],
        ["Control Total de Sistema", "Acceso root a sistemas operativos de forma remota."],
        ["Hack Ético Social", "Simulación de ataques para fortalecer ciberdefensas."],
        ["Desencriptación de Mensajes", "Lectura de mensajes cifrados mediante ingeniería inversa."],
        ["Simulador de Phishing", "Páginas falsas para recolección de credenciales."],
        ["Ataques DDOS", "Saturación de servidores hasta colapsarlos."],
        ["Cifrado de Archivos", "Cifrado extremo de archivos confidenciales."],
        ["Shell Reverse Netcat", "Apertura de shells remotas para control absoluto del dispositivo."],
        ["Escaneo de Puertos", "Análisis completo de puertos abiertos y vulnerables."],
        ["Troyano para Android", "Aplicación maliciosa que brinda acceso remoto completo."],
        ["Robo de Tokens", "Captura de tokens de sesión para tomar control de cuentas."],
        ["Phishing Web", "Páginas web idénticas para capturar accesos de usuarios."],
        ["Botnet Builder", "Creación de redes de bots para tareas automatizadas."],
        ["Panel F.A.M.A Pro", "Interfaz avanzada para gestionar herramientas cibernéticas."],
        ["Rastreo de Ubicación", "Seguimiento GPS en tiempo real de dispositivos."],
        ["Hack de Cámaras IP", "Acceso en vivo a cámaras de seguridad IP vulnerables."],
        ["Deep Web Scanner", "Exploración segura y avanzada en la web oscura."],
        ["Clonación Apps Bancarias", "Creación de apps falsas para estafas."],
        ["Interceptar Tráfico", "Espionaje del tráfico web de objetivos."],
        ["Explotación de Bugs", "Uso de errores para entrar a sistemas protegidos."],
        ["Bypass Antivirus", "Evasión de software antivirus para ejecutar payloads."],
        ["Hackeo de Gmail", "Toma de control de cuentas de Google."],
        ["Romper Contraseñas", "Ataques por diccionario y fuerza bruta a passwords."],
        ["Simulación Red Oscura", "Recreación de ambiente darkweb en sistema propio."],
        ["Keylogger de Voz", "Captura de audio para interpretar contraseñas habladas."],
        ["Hackeo Discord", "Toma de cuentas y servidores de Discord."],
        ["Fuerza Bruta Web", "Ataques repetitivos para forzar entrada a plataformas."],
        ["Backdoor Inyectado", "Puerta trasera permanente en sistemas vulnerables."],
        ["Hack GPS", "Intervención de señales de ubicación."],
        ["Manipular Sesiones", "Tomar control de sesiones activas de usuarios."],
        ["Hacker Visualizador", "Escaneo gráfico de movimientos en sistema objetivo."],
        ["BerMat Cloner v2.5", "Clonación total de perfiles digitales desde el panel BerMat."]
      ];document.write('<h1 style="font-family: Orbitron, sans-serif; text-align:center; color:#00f5ff;">⚔️ PANEL DE CIBERATAQUES BERMATMODZ ⚔️</h1>');
  document.write('<div style="max-width:1200px; margin:auto; display:grid; grid-template-columns:repeat(auto-fit, minmax(260px, 1fr)); gap:20px;">');

  menus.forEach(menu => {
    document.write(`
      <div style="background:#011627; border:2px solid #00ffee; padding:20px; border-radius:15px; text-align:left; box-shadow:0 0 15px #00ffee;">
        <h3 style='color:#00ffee; font-size:20px;'>${menu[0]}</h3>
        <p style='color:#b3ffff; font-size:14px;'>${menu[1]}</p>
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
