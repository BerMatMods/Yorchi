
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>BerMatMods | Red Social</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #1877f2, #f0f2f5);
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      color: #1c1e21;
    }

    .container {
      background: white;
      padding: 40px;
      border-radius: 12px;
      box-shadow: 0 0 30px rgba(0, 0, 0, 0.2);
      width: 100%;
      max-width: 400px;
      text-align: center;
      animation: fadeIn 1s ease;
    }

    .container h1 {
      color: #1877f2;
      margin-bottom: 20px;
      font-size: 2.5em;
    }

    .input-field {
      margin: 15px 0;
      text-align: left;
    }

    .input-field label {
      display: block;
      font-weight: bold;
      margin-bottom: 5px;
    }

    .input-field input {
      width: 100%;
      padding: 12px;
      border-radius: 8px;
      border: 1px solid #ccc;
      outline: none;
      transition: all 0.3s;
    }

    .input-field input:focus {
      border-color: #1877f2;
      box-shadow: 0 0 8px rgba(24, 119, 242, 0.2);
    }

    button {
      width: 100%;
      padding: 14px;
      background-color: #1877f2;
      color: white;
      border: none;
      border-radius: 8px;
      font-size: 1em;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    button:hover {
      background-color: #155dc1;
    }

    .footer {
      margin-top: 30px;
      font-size: 0.9em;
      color: #f0f0f0;
      text-align: center;
      animation: fadeIn 2s ease-in-out;
    }

    .footer strong {
      color: yellow;
    }

    @keyframes fadeIn {
      from {opacity: 0; transform: scale(0.9);}
      to {opacity: 1; transform: scale(1);}
    }

    .banner {
      position: absolute;
      top: 15px;
      background: #1c1e21;
      color: #00ffea;
      padding: 10px 25px;
      border-radius: 0 0 12px 12px;
      font-size: 1.2em;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
    }
  </style>
</head>
<body>

  <div class="banner">
    🔷 Proyecto Red BerMatMods 🔷
  </div>

  <div class="container">
    <h1>Facebook</h1>
    <div class="input-field">
      <label for="email">Correo electrónico o número de teléfono</label>
      <input type="text" id="email" placeholder="ejemplo@correo.com">
    </div>
    <div class="input-field">
      <label for="password">Contraseña</label>
      <input type="password" id="password" placeholder="**********">
    </div>
    <button onclick="iniciarSesion()">Iniciar sesión</button>
  </div>

  <div class="footer">
    ⚡ Proyecto visual educativo colaborativo con <strong>BerMatMods</strong> <br>
    © 2025 AnthzZ Berrocal | Inspirado en el diseño de Meta™
  </div>

  <script>
    function iniciarSesion() {
      alert("🚀 Esto es un proyecto visual. No se recopila información.");
    }
  </script>

</body>
</html>
