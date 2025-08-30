
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
      background: linear-gradient(135deg, #fce4ec, #f8bbd0);
      font-family: 'Raleway', sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      position: relative;
      min-height: 100vh;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
    }

    /* Pantallas de acceso (overlay) */
    .pantalla {
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: linear-gradient(135deg, rgba(252,228,236,0.98), rgba(248,187,208,0.98));
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      z-index: 9999;
      padding: 20px;
      text-align: center;
      transition: opacity 0.25s ease;
    }

    .pantalla.hidden { display: none; }

    .pantalla h2 {
      font-size: 30px;
      color: #ad1457;
      font-family: 'Pacifico', cursive;
      margin-bottom: 12px;
      text-shadow: 0 0 5px #ec407a;
    }

    /* Teclado y entrada */
    #claveInput {
      font-size: 24px;
      padding: 12px 18px;
      border: 3px solid #ec407a;
      border-radius: 15px;
      text-align: center;
      width: 220px;
      margin-bottom: 12px;
      letter-spacing: 4px;
      color: #880e4f;
      background: #fff7fb;
    }

    #teclado {
      display: grid;
      grid-template-columns: repeat(3, 70px);
      gap: 12px;
      margin-bottom: 14px;
    }

    .tecla {
      font-size: 22px;
      padding: 12px;
      background: linear-gradient(180deg,#f8bbd0,#f48fb1);
      border: 2px solid #ec407a;
      border-radius: 12px;
      color: #880e4f;
      cursor: pointer;
      box-shadow: 0 6px 14px rgba(244,143,177,0.25);
      user-select: none;
      text-align:center;
    }

    .tecla:active { transform: translateY(2px); }

    #accederBtn {
      padding: 10px 26px;
      font-size: 20px;
      background: linear-gradient(45deg, #f06292, #ec407a);
      color: white;
      border: none;
      border-radius: 30px;
      font-family: 'Pacifico', cursive;
      box-shadow: 0 8px 30px rgba(236,64,122,0.25);
      cursor: pointer;
      margin-top: 6px;
    }

    /* Stitch & credit */
    #stitch {
      border: 5px dashed #f06292;
      border-radius: 18px;
      padding: 12px;
      background: #fff0f6;
      box-shadow: 0 0 20px #f8bbd0;
      margin-top: 18px;
      display: inline-block;
    }
    #stitch img { width: 180px; border-radius: 14px; }

    #infoSeguridad {
      margin-top: 14px;
      color: #ad1457;
      font-family: 'Pacifico', cursive;
      font-size: 16px;
      text-shadow: 0 0 5px #ec407a;
    }

    /* Pregunta (segunda pantalla) */
    .pregunta-contenedor {
      text-align: center;
    }
    .opciones {
      display: flex;
      flex-direction: column;
      gap: 12px;
      margin-top: 10px;
    }
    .opciones button {
      padding: 12px 18px;
      font-size: 18px;
      border-radius: 14px;
      background: linear-gradient(180deg,#fff1f6,#f8bbd0);
      border: 2px solid #ec407a;
      color: #880e4f;
      cursor: pointer;
      transition: transform 0.12s ease, box-shadow 0.12s ease;
      font-weight: 700;
      max-width: 320px;
      margin: 0 auto;
    }
    .opciones button:hover { transform: translateY(-3px); box-shadow: 0 8px 24px rgba(244,143,177,0.18); }
    .opciones button.correct { background: linear-gradient(45deg,#ffd54f,#ffb300); color:#5d3400; border-color:#ffb300; }

    /* Modal pequeño de error decorado */
    #modalError {
      position: fixed;
      left: 50%;
      top: 18%;
      transform: translateX(-50%);
      min-width: 260px;
      max-width: 90%;
      background: linear-gradient(180deg,#fff0f6,#ffd9e8);
      border: 3px solid #ff80ab;
      border-radius: 18px;
      padding: 16px;
      box-shadow: 0 8px 40px rgba(240,128,171,0.25);
      z-index: 10050;
      display: none;
      text-align: center;
      animation: popup 0.28s ease;
    }
    #modalError h3 {
      margin: 6px 0 8px;
      color: #c2185b;
      font-family: 'Pacifico', cursive;
      font-size: 20px;
      text-shadow: 0 0 6px rgba(236,64,122,0.3);
    }
    #modalError p {
      margin: 0 0 10px;
      color: #880e4f;
      font-weight: 700;
    }
    #modalError button {
      padding: 8px 18px;
      border-radius: 12px;
      background: linear-gradient(45deg,#f06292,#ec407a);
      color: white;
      border: none;
      cursor: pointer;
      font-weight: 700;
    }
    @keyframes popup {
      from { transform: translate(-50%, -8px) scale(0.96); opacity: 0; }
      to { transform: translate(-50%, 0) scale(1); opacity: 1; }
    }

    /* Contenido principal (se mantiene tal como en el original) */
    #contenidoPrincipal {
      display: none;
      width: 100%;
      padding: 40px 12px 80px;
      display: flex;
      justify-content: center;
    }

    .container {
      text-align: center;
      margin-top: 60px;
      padding: 30px;
      border-radius: 25px;
      background: rgba(255, 255, 255, 0.95);
      box-shadow: 0 0 40px rgba(219, 112, 147, 0.7);
      width: 90%;
      max-width: 700px;
      z-index: 2;
    }

    .titulo {
      font-family: 'Dancing Script', cursive;
      font-size: 50px;
      color: #ad1457;
      text-shadow: 0 0 15px #f48fb1, 0 0 10px #ec407a;
      animation: parpadeo 2s infinite;
    }
    @keyframes parpadeo { 0%,100%{opacity:1} 50%{opacity:0.6} }

    .contador {
      font-size: 20px;
      color: #880e4f;
      font-weight: 700;
      margin-top: 20px;
    }

    .btn {
      margin: 30px auto 0;
      padding: 20px 40px;
      font-size: 24px;
      background: linear-gradient(45deg, #f06292, #ec407a);
      border: 3px solid #ad1457;
      color: white;
      border-radius: 35px;
      cursor: pointer;
      box-shadow: 0 0 25px #f48fb1;
      font-family: 'Pacifico', cursive;
      transition: transform 0.3s ease;
      user-select: none;
      display: inline-block;
    }
    .btn:hover { transform: scale(1.03); }

    .mensaje {
      margin-top: 30px;
      padding: 30px 25px;
      background-color: #fce4ec;
      border-radius: 20px;
      font-size: 24px;
      color: #ad1457;
      box-shadow: 0 0 30px #f48fb1;
      font-family: 'Great Vibes', cursive;
      text-shadow: 0 0 5px #ec407a;
      display: none;
      animation: aparecer 1.8s ease-out forwards;
    }
    .imagen-extra { margin-top: 25px; display: none; animation: aparecer 1.8s ease-out forwards; }
    .imagen-extra img { max-width: 90%; border-radius: 25px; box-shadow: 0 0 35px #f48fb1; border: 5px solid #ec407a; user-select:none; }

    @keyframes aparecer { 0%{opacity:0;transform:translateY(25px)}100%{opacity:1;transform:translateY(0)} }

    .muñequitos {
      position: fixed;
      bottom: 0;
      left: 0;
      width: 100%;
      text-align: center;
      padding: 15px 0;
      background: rgba(255, 228, 241, 0.7);
      font-size: 40px;
      animation: rebote 2.5s infinite ease-in-out;
      z-index: 1;
    }
    .muñequitos .cuadro {
      display: inline-block;
      background: #fff0f6;
      border: 3px solid #f48fb1;
      border-radius: 20px;
      padding: 15px;
      margin: 0 15px;
      box-shadow: 0 0 15px #f8bbd0;
    }
    .muñequitos img { width: 85px; height: 85px; animation: muñequito-bailando 2.5s infinite; user-select:none; }
    @keyframes rebote { 0%,100%{transform:translateY(0)}50%{transform:translateY(-15px)} }
    @keyframes muñequito-bailando { 0%{transform:translateY(0)}50%{transform:translateY(-15px)}100%{transform:translateY(0)} }

    #btnGaleria { margin-top: 20px; background: linear-gradient(45deg, #ba68c8, #ab47bc); border: 3px solid #8e24aa; color: white; border-radius: 30px; padding: 15px 30px; font-size: 20px; font-family: 'Pacifico', cursive; cursor: pointer; box-shadow: 0 0 20px #ce93d8; transition: transform 0.3s ease; }
    #btnGaleria:hover { transform: scale(1.05); box-shadow: 0 0 30px #9c27b0; }

    #galeria { display: none; margin-top: 25px; max-width: 700px; text-align: center; }
    #galeria .cuadro-foto { display: inline-block; margin: 10px; border: 3px solid #ce93d8; border-radius: 15px; overflow: hidden; box-shadow: 0 0 15px #ba68c8; background: white; transition: transform 0.3s ease; cursor: pointer; width: 150px; height: 150px; }
    #galeria img { width: 100%; height: 100%; object-fit: cover; }

    /* mensaje tip cursor estilo */
    .cursor {
      display: inline-block;
      width: 8px;
      background-color: #ff69b4;
      margin-left: 3px;
      animation: blink 0.8s infinite;
    }
    @keyframes blink { 0%,50%{opacity:1}51%,100%{opacity:0} }
  </style>
</head>
<body>
  <!-- PANTALLA 1: ingreso de clave -->
  <div id="pantallaClave" class="pantalla">
    <h2>🔒 Código para acceder</h2>
    <input type="text" id="claveInput" placeholder="10/11/23" maxlength="8" readonly>
    <div id="teclado"></div>
    <button id="accederBtn">Acceder</button>

    <div id="stitch">
      <img src="https://media0.giphy.com/media/v1.Y2lkPTZjMDliOTUydXRucTZibGt3cDRhdTA1NXQzOG04ejZ6NGVtbXNzMjAxemp3ZnZjOSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/huXuyCODzzCQLy3T05/giphy.gif" alt="Stitch Amoroso">
    </div>

    <div id="infoSeguridad">
      By: <b>Anth'Zz Berrocal</b><br>👽  <strong>BerMat Proyects</strong> 👽
    </div>
  </div>

  <!-- PANTALLA 2: pregunta "¿Qué tan golosa eres...?" -->
  <div id="pantallaPregunta" class="pantalla hidden">
    <div class="pregunta-contenedor">
      <h2>❓ ¿Qué tan golosa eres…?</h2>
      <div class="opciones">
        <button data-resp="1">No soy Goloza</button>
        <button data-resp="2">Soy poco Goloza</button>
        <button data-resp="3" class="correct">Soy muy Goloza 🔥</button>
      </div>
    </div>
  </div>

  <!-- MODAL PEQUEÑO DE ERROR (para opción 1 y 2) -->
  <div id="modalError" role="alert" aria-hidden="true">
    <h3>❌ Respuesta incorrecta</h3>
    <p>Estás mintiendo Mamaguevo... 😢💕</p>
    <button id="cerrarModal">Volver a intentar</button>
  </div>

  <!-- CONTENIDO PRINCIPAL (todo tu contenido romántico original) -->
  <div id="contenidoPrincipal">
    <div class="container">
      <div class="titulo">💖 Feliz Aniversario Mi Amorcita hermosa 💖</div>
      <div class="contador" id="contador">Calculando el tiempo... ⏳</div>

      <button class="btn" id="btnSorpresa">TOCA AQUÍ MI REINA</button>

      <div class="mensaje" id="mensaje"></div>
      <span class="cursor" id="cursor"></span>

      <div class="imagen-extra" id="imagenExtra">
        <img src="https://i.postimg.cc/j5HdGJKJ/Screenshot-20250810-134752.jpg" alt="Foto de nosotros" />
      </div> 

      <button id="btnGaleria">Ver nuestra galería 📸</button>

      <div id="galeria">
        <div class="cuadro-foto"><img src="https://i.postimg.cc/HkxS5Yjs/1742316301125-2.jpg" alt=""></div>
        <div class="cuadro-foto"><img src="https://i.postimg.cc/8PkwQpRB/Screenshot-20250427-213138.jpg" alt=""></div>
        <div class="cuadro-foto"><img src="https://i.postimg.cc/VNsb5vND/received-1162848851410899.jpg" alt=""></div>
        <div class="cuadro-foto"><img src="https://i.postimg.cc/RVRShRnx/PSX-20250530-060357.jpg" alt=""></div>
        <div class="cuadro-foto"><img src="https://i.postimg.cc/59KpJcnh/IMG-20241228-231305-817-3.jpg" alt=""></div>
      </div>
    </div>

    <div class="muñequitos" aria-hidden="true">
      <div class="cuadro"><img src="https://media0.giphy.com/media/yN5xPFm8klwMddZVKi/giphy.gif" alt=""></div>
      <div class="cuadro"><img src="https://media2.giphy.com/media/5dkb3UXNiRU5qwNrzL/giphy.gif" alt=""></div>
      <div class="cuadro"><img src="https://media0.giphy.com/media/yN5xPFm8klwMddZVKi/giphy.gif" alt=""></div>
    </div>
  </div>

  <script>
    /* -------- TECLADO Y VALIDACIÓN PRIMER CÓDIGO -------- */
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
        // ocultar primera pantalla y mostrar la pregunta
        document.getElementById('pantallaClave').classList.add('hidden');
        document.getElementById('pantallaPregunta').classList.remove('hidden');
      } else {
        alert('Código incorrecto ❌');
      }
    });

    /* -------- PREGUNTA: manejo de opciones -------- */
    const botonesPregunta = document.querySelectorAll('#pantallaPregunta .opciones button');
    const modalError = document.getElementById('modalError');
    const cerrarModal = document.getElementById('cerrarModal');

    botonesPregunta.forEach(btn => {
      btn.addEventListener('click', () => {
        const resp = btn.dataset.resp;
        if (resp === '3') {
          // correcto -> mostrar contenido principal
          document.getElementById('pantallaPregunta').classList.add('hidden');
          document.getElementById('contenidoPrincipal').style.display = 'flex';
          // inicializar contador y otras cosas
          iniciarTodo();
        } else {
          // incorrecto -> mostrar modal pequeño adornado
          modalError.style.display = 'block';
          modalError.setAttribute('aria-hidden','false');
        }
      });
    });

    cerrarModal.addEventListener('click', () => {
      modalError.style.display = 'none';
      modalError.setAttribute('aria-hidden','true');
      // volver a la pregunta (ya está visible)
    });

    /* -------- CONTADOR (desde 2023-11-10) -------- */
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

    /* -------- MENSAJE TIPO MÁQUINA DE ESCRIBIR y GALERÍA -------- */
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
      }, 45); // velocidad de escritura
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

    /* -------- INICIALIZAR TODO CUANDO SE ACCEDE CORRECTAMENTE -------- */
    function iniciarTodo() {
      // inicio contador
      if (intervaloContador) clearInterval(intervaloContador);
      actualizarContador();
      intervaloContador = setInterval(actualizarContador, 1000);

      // dejar cursor oculto hasta que pulse sorpresa
      cursor.style.display = 'none';
    }

    /* -------- seguridad: reset si cierran/recargan (opcional) -------- */
    // Si quieres que al recargar vuelva a pedir clave, no hagas nada.
    // Si quieres auto-entrar, podríamos añadir lógica, pero lo dejamos como está.

  </script>
</body>
</html>
