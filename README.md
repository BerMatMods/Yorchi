
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>BerMa_Mods</title>
  <link href="https://fonts.googleapis.com/css2?family=Dancing+Script&family=Pacifico&family=Great+Vibes&family=Raleway:wght@400;700&display=swap" rel="stylesheet">
  <style>
    /* Reset / base */
    * { box-sizing: border-box; }
    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(135deg, #fdf2f8, #f8e8fb, #f3d9f7);
      font-family: 'Raleway', sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      position: relative;
      min-height: 100vh;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      overflow-x: hidden;
    }

    /* Brillos decorativos (destellos animados) */
    .brillo {
      position: absolute;
      width: 6px;
      height: 6px;
      background: white;
      border-radius: 50%;
      box-shadow: 0 0 8px 2px rgba(255, 255, 255, 0.8);
      opacity: 0;
      pointer-events: none;
      z-index: 1;
    }

    /* Pantallas de acceso (overlay con brillo) */
    .pantalla {
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: linear-gradient(135deg, rgba(253,242,248,0.95), rgba(243,217,247,0.95));
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      z-index: 9999;
      padding: 20px;
      text-align: center;
      backdrop-filter: blur(10px);
      border: 2px solid rgba(219, 112, 147, 0.2);
    }

    .pantalla.hidden {
      display: none;
    }

    .pantalla h2 {
      font-size: 32px;
      color: #9c27b0;
      font-family: 'Pacifico', cursive;
      margin-bottom: 16px;
      text-shadow: 0 0 10px rgba(233, 30, 99, 0.3);
      position: relative;
      display: inline-block;
    }

    .pantalla h2::after {
      content: '';
      position: absolute;
      bottom: -5px;
      left: 10%;
      width: 80%;
      height: 2px;
      background: linear-gradient(90deg, transparent, #e91e63, transparent);
      box-shadow: 0 0 8px #e91e63;
    }

    /* Teclado y entrada con brillo */
    #claveInput {
      font-size: 24px;
      padding: 14px 18px;
      border: 3px solid #d19ad6;
      border-radius: 18px;
      text-align: center;
      width: 240px;
      margin-bottom: 16px;
      letter-spacing: 4px;
      color: #7b1fa2;
      background: rgba(255, 250, 255, 0.8);
      backdrop-filter: blur(4px);
      box-shadow: 0 0 15px rgba(213, 105, 186, 0.3);
      font-weight: 500;
    }

    #claveInput:focus {
      outline: none;
      box-shadow: 0 0 20px rgba(213, 105, 186, 0.6), 0 0 30px rgba(233, 30, 99, 0.3);
    }

    #teclado {
      display: grid;
      grid-template-columns: repeat(3, 75px);
      gap: 14px;
      margin-bottom: 16px;
    }

    .tecla {
      font-size: 22px;
      font-weight: bold;
      padding: 14px;
      background: linear-gradient(180deg, #f8e8fb, #eadcf8);
      border: 2px solid #d19ad6;
      border-radius: 16px;
      color: #7b1fa2;
      cursor: pointer;
      box-shadow: 0 6px 16px rgba(142, 36, 170, 0.15), inset 0 1px 0 rgba(255, 255, 255, 0.6);
      user-select: none;
      transition: all 0.2s ease;
      position: relative;
      overflow: hidden;
    }

    .tecla::before {
      content: '';
      position: absolute;
      top: -10px;
      left: -10px;
      width: 20px;
      height: 20px;
      background: rgba(255, 255, 255, 0.6);
      border-radius: 50%;
      opacity: 0;
      transition: opacity 0.3s;
    }

    .tecla:hover::before {
      opacity: 1;
    }

    .tecla:active {
      transform: translateY(3px);
      box-shadow: 0 2px 8px rgba(142, 36, 170, 0.2);
    }

    #accederBtn {
      padding: 12px 30px;
      font-size: 20px;
      background: linear-gradient(45deg, #e91e63, #9c27b0);
      color: white;
      border: none;
      border-radius: 30px;
      font-family: 'Pacifico', cursive;
      box-shadow: 0 8px 30px rgba(233, 30, 99, 0.3),
                  0 0 20px rgba(233, 30, 99, 0.2) inset;
      cursor: pointer;
      margin-top: 8px;
      transition: all 0.3s ease;
      position: relative;
      overflow: hidden;
    }

    #accederBtn::after {
      content: '';
      position: absolute;
      top: -10px;
      left: -10px;
      width: 20px;
      height: 20px;
      background: rgba(255, 255, 255, 0.7);
      border-radius: 50%;
      opacity: 0;
      transition: opacity 0.5s;
    }

    #accederBtn:hover::after {
      opacity: 1;
      animation: sparkle 0.8s ease forwards;
    }

    @keyframes sparkle {
      0% { transform: scale(0); opacity: 0.7; }
      50% { transform: scale(1.5); opacity: 1; }
      100% { transform: scale(2); opacity: 0; }
    }

    #accederBtn:hover {
      transform: scale(1.05);
      box-shadow: 0 10px 40px rgba(233, 30, 99, 0.4),
                  0 0 30px rgba(233, 30, 99, 0.25);
    }

    /* Stitch & credit con marco brillante */
    #stitch {
      border: 3px solid #d19ad6;
      border-radius: 20px;
      padding: 10px;
      background: rgba(255, 255, 255, 0.7);
      box-shadow: 0 0 25px rgba(213, 105, 186, 0.4);
      margin-top: 20px;
      display: inline-block;
      position: relative;
      overflow: hidden;
    }

    #stitch::before {
      content: '';
      position: absolute;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: linear-gradient(45deg, transparent, rgba(255,255,255,0.3), transparent);
      pointer-events: none;
      animation: slideShine 4s infinite;
    }

    @keyframes slideShine {
      0% { transform: translateX(-100%); opacity: 0; }
      50% { opacity: 0.6; }
      100% { transform: translateX(100%); opacity: 0; }
    }

    #stitch img {
      width: 180px;
      border-radius: 16px;
      border: 3px solid #e91e63;
      box-shadow: 0 0 20px rgba(233, 30, 99, 0.4);
    }

    #infoSeguridad {
      margin-top: 16px;
      color: #9c27b0;
      font-family: 'Pacifico', cursive;
      font-size: 16px;
      text-shadow: 0 0 8px rgba(233, 30, 99, 0.2);
    }

    /* Contenido principal con efectos brillantes */
    #contenidoPrincipal {
      display: none;
      width: 100%;
      padding: 40px 12px 80px;
      justify-content: center;
    }

    .container {
      text-align: center;
      margin-top: 60px;
      padding: 35px;
      border-radius: 30px;
      background: rgba(255, 255, 255, 0.9);
      box-shadow: 
        0 0 30px rgba(219, 112, 147, 0.4),
        0 0 50px rgba(233, 30, 99, 0.2) inset;
      width: 90%;
      max-width: 700px;
      z-index: 2;
      border: 2px solid rgba(213, 105, 186, 0.4);
      position: relative;
      overflow: hidden;
    }

    .container::before {
      content: '';
      position: absolute;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: linear-gradient(45deg, transparent, rgba(255,255,255,0.2), transparent);
      pointer-events: none;
      animation: slideShine 6s infinite;
      z-index: -1;
    }

    .titulo {
      font-family: 'Dancing Script', cursive;
      font-size: 54px;
      color: #9c27b0;
      text-shadow: 
        0 0 15px rgba(233, 30, 99, 0.4),
        0 0 25px rgba(213, 105, 186, 0.5);
      animation: parpadeo 2s infinite, glow 2.5s ease-in-out infinite alternate;
      position: relative;
      display: inline-block;
    }

    @keyframes glow {
      0% { text-shadow: 0 0 10px #e91e63; }
      100% { text-shadow: 0 0 25px #9c27b0, 0 0 35px #e91e63; }
    }

    .contador {
      font-size: 20px;
      color: #7b1fa2;
      font-weight: 700;
      margin-top: 20px;
      text-shadow: 0 0 5px rgba(213, 105, 186, 0.3);
    }

    .btn {
      margin: 30px auto 0;
      padding: 20px 40px;
      font-size: 24px;
      background: linear-gradient(45deg, #e91e63, #9c27b0);
      border: 3px solid #9c27b0;
      color: white;
      border-radius: 35px;
      cursor: pointer;
      box-shadow: 
        0 0 25px rgba(233, 30, 99, 0.3),
        0 0 15px rgba(213, 105, 186, 0.4) inset;
      font-family: 'Pacifico', cursive;
      transition: all 0.3s ease;
      user-select: none;
      display: inline-block;
      position: relative;
      overflow: hidden;
    }

    .btn::after {
      content: '';
      position: absolute;
      top: -10px;
      left: -20px;
      width: 30px;
      height: 30px;
      background: rgba(255, 255, 255, 0.6);
      border-radius: 50%;
      opacity: 0;
      transition: opacity 0.4s;
    }

    .btn:hover::after {
      opacity: 1;
      animation: sparkle 1s ease forwards;
    }

    .btn:hover {
      transform: scale(1.05);
      box-shadow: 
        0 0 35px rgba(233, 30, 99, 0.5),
        0 0 20px rgba(213, 105, 186, 0.6) inset;
    }

    .mensaje {
      margin-top: 30px;
      padding: 30px 25px;
      background: linear-gradient(to bottom, #fdf2f8, #f8e8fb);
      border-radius: 20px;
      font-size: 24px;
      color: #9c27b0;
      box-shadow: 0 0 30px rgba(219, 112, 147, 0.4);
      font-family: 'Great Vibes', cursive;
      text-shadow: 0 0 5px rgba(233, 30, 99, 0.2);
      display: none;
      animation: aparecer 1.8s ease-out forwards;
      border: 1px solid rgba(213, 105, 186, 0.3);
    }

    .imagen-extra {
      margin-top: 25px;
      display: none;
      animation: aparecer 1.8s ease-out forwards;
    }

    .imagen-extra img {
      max-width: 90%;
      border-radius: 25px;
      box-shadow: 0 0 40px rgba(233, 30, 99, 0.4);
      border: 5px solid #e91e63;
      user-select: none;
      animation: brilloBorde 3s infinite alternate;
    }

    @keyframes brilloBorde {
      0% { border-color: #e91e63; box-shadow: 0 0 30px rgba(233, 30, 99, 0.3); }
      100% { border-color: #9c27b0; box-shadow: 0 0 40px rgba(142, 36, 170, 0.5); }
    }

    .muñequitos {
      position: fixed;
      bottom: 0;
      left: 0;
      width: 100%;
      text-align: center;
      padding: 15px 0;
      background: rgba(255, 242, 248, 0.8);
      backdrop-filter: blur(8px);
      font-size: 40px;
      z-index: 1;
      border-top: 2px solid rgba(213, 105, 186, 0.3);
    }

    .muñequitos .cuadro {
      display: inline-block;
      background: rgba(255, 255, 255, 0.7);
      border: 3px solid #d19ad6;
      border-radius: 20px;
      padding: 15px;
      margin: 0 15px;
      box-shadow: 0 0 20px rgba(213, 105, 186, 0.4);
      position: relative;
      overflow: hidden;
    }

    .muñequitos .cuadro::before {
      content: '';
      position: absolute;
      top: -5px; left: -5px;
      width: 20px; height: 20px;
      background: white;
      border-radius: 50%;
      opacity: 0;
      animation: chispazo 2s infinite;
    }

    @keyframes chispazo {
      0%, 100% { opacity: 0; transform: scale(0.5); }
      50% { opacity: 1; transform: scale(1); }
    }

    .muñequitos img {
      width: 85px;
      height: 85px;
      animation: muñequito-bailando 2.5s infinite;
      user-select: none;
      border-radius: 12px;
    }

    @keyframes rebote { 0%,100%{transform:translateY(0)}50%{transform:translateY(-15px)} }
    @keyframes muñequito-bailando { 0%{transform:translateY(0)}50%{transform:translateY(-15px)}100%{transform:translateY(0)} }

    #btnGaleria {
      margin-top: 20px;
      background: linear-gradient(45deg, #ba68c8, #9c27b0);
      border: 3px solid #8e24aa;
      color: white;
      border-radius: 30px;
      padding: 15px 30px;
      font-size: 20px;
      font-family: 'Pacifico', cursive;
      cursor: pointer;
      box-shadow: 0 0 20px rgba(186, 104, 200, 0.4);
      transition: transform 0.3s ease;
      position: relative;
      overflow: hidden;
    }

    #btnGaleria::after {
      content: '✨';
      position: absolute;
      top: 5px; right: 10px;
      font-size: 18px;
      opacity: 0;
      transition: opacity 0.5s;
    }

    #btnGaleria:hover::after {
      opacity: 1;
    }

    #btnGaleria:hover {
      transform: scale(1.08);
      box-shadow: 0 0 30px rgba(142, 36, 170, 0.6);
    }

    #galeria {
      display: none;
      margin-top: 25px;
      max-width: 700px;
      text-align: center;
    }

    #galeria .cuadro-foto {
      display: inline-block;
      margin: 12px;
      border: 3px solid #d19ad6;
      border-radius: 18px;
      overflow: hidden;
      box-shadow: 0 0 20px rgba(213, 105, 186, 0.4);
      background: white;
      transition: all 0.4s ease;
      cursor: pointer;
      width: 150px;
      height: 150px;
      position: relative;
    }

    #galeria .cuadro-foto::before {
      content: '💖';
      position: absolute;
      top: 50%; left: 50%;
      transform: translate(-50%, -50%) scale(0);
      opacity: 0;
      font-size: 30px;
      transition: all 0.4s ease;
      pointer-events: none;
    }

    #galeria .cuadro-foto:hover::before {
      transform: translate(-50%, -50%) scale(1.2);
      opacity: 0.8;
    }

    #galeria .cuadro-foto:hover {
      transform: scale(1.08) rotate(3deg);
      box-shadow: 0 0 30px rgba(233, 30, 99, 0.5);
    }

    #galeria img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      border-radius: 15px;
    }

    .cursor {
      display: inline-block;
      width: 8px;
      background-color: #e91e63;
      margin-left: 3px;
      animation: blink 0.8s infinite;
      border-radius: 4px;
    }

    @keyframes blink {
      0%,50%{opacity:1}
      51%,100%{opacity:0}
    }

    @keyframes aparecer {
      0%{opacity:0;transform:translateY(25px)}
      100%{opacity:1;transform:translateY(0)}
    }
  </style>
</head>
<body>

  <!-- === AUDIO DE FONDO (música desde Google Drive) === -->
  <audio id="audioFondo" loop>
    <source src="https://drive.google.com/uc?export=download&id=1090PcBCJcNHMnH3jfP48IulVZk3KHG87" type="audio/mpeg">
    Tu navegador no soporta audio.
  </audio>

  <!-- PANTALLA DE CLAVE -->
  <div id="pantallaClave" class="pantalla">
    <h2>🔒 Código para acceder</h2>
    <input type="text" id="claveInput" placeholder="10/11/23" maxlength="8">
    <div id="teclado"></div>
    <button id="accederBtn">Acceder</button>

    <div id="stitch">
      <img src=" https://media1.giphy.com/media/v1.Y2lkPTZjMDliOTUyaHpuZHJjNzNiaGVmdGptNDdmcWc4OTBybzdpNXQ2NWZhbnkxYmZ2biZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/11TyfGbDbBv4be/giphy.gif" alt="Stitch Amoroso">
    </div>

    <div id="infoSeguridad">
      By: <b>Anth'Zz Berrocal</b><br>👽  <strong>BerMat Proyects</strong> 👽
    </div>
  </div>

  <!-- CONTENIDO PRINCIPAL -->
  <div id="contenidoPrincipal">
    <div class="container">
      <div class="titulo">💖 Feliz Aniversario Mi Amorcita hermosa 💖</div>
      <div class="contador" id="contador">Calculando el tiempo... ⏳</div>

      <button class="btn" id="btnSorpresa">TOCA AQUÍ MI REINA</button>

      <div class="mensaje" id="mensaje"></div>
      <span class="cursor" id="cursor"></span>

      <div class="imagen-extra" id="imagenExtra">
        <img src="https://i.postimg.cc/j5HdGJKJ/Screenshot-20250810-134752.jpg " alt="Foto de nosotros" />
      </div> 

      <button id="btnGaleria">Ver nuestra galería 📸</button>

      <div id="galeria">
        <div class="cuadro-foto"><img src="https://i.postimg.cc/HkxS5Yjs/1742316301125-2.jpg " alt=""></div>
        <div class="cuadro-foto"><img src="https://i.postimg.cc/8PkwQpRB/Screenshot-20250427-213138.jpg " alt=""></div>
        <div class="cuadro-foto"><img src="https://i.postimg.cc/VNsb5vND/received-1162848851410899.jpg " alt=""></div>
        <div class="cuadro-foto"><img src="https://i.postimg.cc/RVRShRnx/PSX-20250530-060357.jpg " alt=""></div>
        <div class="cuadro-foto"><img src="https://i.postimg.cc/59KpJcnh/IMG-20241228-231305-817-3.jpg " alt=""></div>
      </div>
    </div>

    <div class="muñequitos" aria-hidden="true">
      <div class="cuadro"><img src="https://media0.giphy.com/media/yN5xPFm8klwMddZVKi/giphy.gif " alt=""></div>
      <div class="cuadro"><img src="https://media2.giphy.com/media/v1.Y2lkPTZjMDliOTUyaDR2a25oNTZva251ZjNya3UwYjR5eWljZGJrZHY3NHF6YWo1NDE3bSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/ruw1bRYN0IXNS/giphy.gif " alt=""></div>
      <div class="cuadro"><img src="https://media0.giphy.com/media/yN5xPFm8klwMddZVKi/giphy.gif " alt=""></div>
    </div>
  </div>

  <!-- Brillos flotantes (script los genera) -->
  <script>
    // Generar brillos aleatorios en fondo
    function crearBrillos() {
      for (let i = 0; i < 20; i++) {
        const brillo = document.createElement('div');
        brillo.classList.add('brillo');
        brillo.style.left = Math.random() * 100 + 'vw';
        brillo.style.top = Math.random() * 100 + 'vh';
        document.body.appendChild(brillo);
        animarBrillo(brillo);
      }
    }

    function animarBrillo(el) {
      const delay = Math.random() * 5;
      const duration = 1.5 + Math.random() * 2;
      el.style.animation = `fadeInOut ${duration}s ease-in-out ${delay}s infinite`;

      // Keyframes dinámicas
      const style = document.createElement('style');
      style.innerHTML = `
        @keyframes fadeInOut {
          0%, 100% { opacity: 0; transform: scale(0); }
          50% { opacity: 0.8; transform: scale(1); }
        }
      `;
      document.head.appendChild(style);
    }

    crearBrillos();

    /* -------- TECLADO Y VALIDACIÓN DE CLAVE -------- */
    const input = document.getElementById('claveInput');
    const teclado = document.getElementById('teclado');
    const accederBtn = document.getElementById('accederBtn');
    const claveCorrecta = '10/11/23';

    const numeros = ['1','2','3','4','5','6','7','8','9','0','B','/'];
    numeros.forEach(n => {
      const tecla = document.createElement('div');
      tecla.className = 'tecla';
      tecla.textContent = n;
      tecla.onclick = () => {
        if (n === 'B') input.value = input.value.slice(0, -1);
        else if (input.value.length < 8) input.value += n;
      };
      teclado.appendChild(tecla);
    });

    accederBtn.addEventListener('click', () => {
      if (input.value === claveCorrecta) {
        document.getElementById('pantallaClave').classList.add('hidden');
        document.getElementById('contenidoPrincipal').style.display = 'flex';
        iniciarTodo();
      } else {
        alert('Código incorrecto ❌');
      }
    });

    /* -------- CONTADOR -------- */
    const inicio = new Date("2023-11-10T00:00:00");
    const contador = document.getElementById("contador");

    function actualizarContador() {
      const ahora = new Date();
      let anos = ahora.getFullYear() - inicio.getFullYear();
      let meses = ahora.getMonth() - inicio.getMonth();
      let dias = ahora.getDate() - inicio.getDate();
      let horas = ahora.getHours() - inicio.getHours();
      let minutos = ahora.getMinutes() - inicio.getMinutes();
      let segundos = ahora.getSeconds() - inicio.getSeconds();

      if (segundos < 0) { segundos += 60; minutos--; }
      if (minutos < 0) { minutos += 60; horas--; }
      if (horas < 0) { horas += 24; dias--; }
      if (dias < 0) {
        meses--;
        const mesAnterior = new Date(ahora.getFullYear(), ahora.getMonth(), 0);
        dias += mesAnterior.getDate();
      }
      if (meses < 0) { meses += 12; anos--; }

      contador.innerHTML = `💞 𝐘𝐀 𝐕𝐀𝐌𝐎𝐒: ${anos} AÑOS, ${meses} MESES, ${dias} DÍAS, ${horas}h ${minutos}m ${segundos}s 💞`;
    }

    let intervaloContador = null;

    /* -------- MENSAJE TIPO MÁQUINA DE ESCRIBIR -------- */
    const btnSorpresa = document.getElementById("btnSorpresa");
    const mensaje = document.getElementById("mensaje");
    const imagenExtra = document.getElementById("imagenExtra");
    const btnGaleria = document.getElementById("btnGaleria");
    const galeria = document.getElementById("galeria");
    const cursor = document.getElementById("cursor");

    const texto = `🎉💖 ¡Feliz 1 año y 9 meses, mi reina Briyidth! 💖🎉
Hoy celebramos otro mes más juntos, y mi corazón late más fuerte por ti cada día. 💕
Gracias por llegar a mi vida, por llenar mis días de risas, abrazos y momentos que nunca olvidaré. 🌹
Eres mi razón de sonreír, mi inspiración, mi fuerza y mi paz. 💌
Quiero que sepas que no importa lo que pase, siempre estaré a tu lado para cuidarte, apoyarte y amarte. 💍
Tu amor me ha hecho mejor persona, y no hay un solo segundo en el que no agradezca tenerte. ✨
Te prometo seguir luchando por nosotros, cumplir nuestros sueños y escribir juntos una historia que dure para siempre. 🌈
Cada beso tuyo me recuerda que el verdadero paraíso es tenerte cerca. 🌅
Eres mi todo, mi hogar, mi destino y mi vida entera. 💘
No hay distancia, tiempo o dificultad que pueda separarnos, porque nuestro amor es más fuerte que todo. 💞
Te amo con la intensidad de mil soles, con la ternura de mil lunas y con la eternidad de mil vidas. 🌠
💞 Mi reina hermosa, eres lo más valioso que tengo y siempre lo serás. 💞`;

    let i = 0;
    let escribirInterval = null;

    function iniciarEscritura() {
      mensaje.textContent = '';
      i = 0;
      mensaje.style.display = 'block';
      cursor.style.display = 'inline-block';
      escribirInterval = setInterval(() => {
        if (i < texto.length) {
          mensaje.textContent += texto.charAt(i);
          i++;
        } else {
          clearInterval(escribirInterval);
          cursor.style.display = 'none';
        }
      }, 45);
    }

    btnSorpresa.addEventListener('click', () => {
      iniciarEscritura();
      imagenExtra.style.display = 'block';
      btnSorpresa.disabled = true;
      btnSorpresa.style.cursor = 'not-allowed';
    });

    btnGaleria.addEventListener('click', () => {
      if (galeria.style.display === 'none' || galeria.style.display === '') {
        galeria.style.display = 'block';
        btnGaleria.textContent = "Ocultar galería 📸";
      } else {
        galeria.style.display = 'none';
        btnGaleria.textContent = "Ver nuestra galería 📸";
      }
    });

    function iniciarTodo() {
      if (intervaloContador) clearInterval(intervaloContador);
      actualizarContador();
      intervaloContador = setInterval(actualizarContador, 1000);
      cursor.style.display = 'none';

      // ▶️ Reproducir música al acceder
      const audio = document.getElementById('audioFondo');
      audio.play().catch(e => {
        console.log("Reproducción automática bloqueada. Necesita interacción del usuario.", e);
      });
    }

    // ▶️ Intentar reproducir al hacer clic en cualquier parte (por políticas de navegador)
    document.addEventListener('click', function() {
      const audio = document.getElementById('audioFondo');
      audio.play().catch(() => {
        console.log("Autoplay fue bloqueado. Se necesita un clic.");
      });
    }, { once: true });

    document.addEventListener('touchstart', function() {
      const audio = document.getElementById('audioFondo');
      audio.play().catch(() => {
        console.log("Touch autoplay bloqueado.");
      });
    }, { once: true });
  </script>
</body>
</html>
