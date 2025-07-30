<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>BerMatMods FacePro</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;600&display=swap" rel="stylesheet">
  <style>
    * {
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }

    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(to right, #e7ebf0, #cfd8e4);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
    }

    .banner {
      background-color: #1877f2;
      color: white;
      width: 100%;
      padding: 10px 0;
      text-align: center;
      font-size: 1.4em;
      font-weight: bold;
      animation: slideTop 1s ease-out;
    }

    @keyframes slideTop {
      from { transform: translateY(-100px); opacity: 0; }
      to { transform: translateY(0); opacity: 1; }
    }

    .login-box {
      background: white;
      border-radius: 10px;
      box-shadow: 0 8px 20px rgba(0,0,0,0.2);
      padding: 25px;
      width: 90%;
      max-width: 360px;
      text-align: center;
      animation: fadeIn 1.2s ease-in-out;
      margin-top: 20px;
    }

    @keyframes fadeIn {
      0% { opacity: 0; transform: scale(0.95); }
      100% { opacity: 1; transform: scale(1); }
    }

    .login-box h2 {
      color: #1877f2;
      font-size: 1.3em;
      margin-bottom: 20px;
    }

    input[type="text"], input[type="password"] {
      width: 100%;
      padding: 10px;
      margin: 8px 0;
      border: 1px solid #ccc;
      border-radius: 6px;
      font-size: 1em;
    }

    button {
      width: 100%;
      background-color: #1877f2;
      color: white;
      padding: 10px;
      font-size: 1em;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    button:hover {
      background-color: #155db2;
    }

    .footer {
      margin-top: 12px;
      font-size: 0.85em;
      color: #555;
    }

    .developer-box {
      margin-top: 30px;
      text-align: center;
      padding: 10px;
      border: 1.5px dashed #1877f2;
      border-radius: 10px;
      background: #f3f9ff;
      font-size: 0.75em;
      animation: glow 2s infinite;
      width: 90%;
      max-width: 500px;
    }

    @keyframes glow {
      0%, 100% { box-shadow: 0 0 5px #1877f2; }
      50% { box-shadow: 0 0 15px #1877f2; }
    }

    .developer-box h3 {
      font-size: 1em;
      margin-bottom: 5px;
    }

    .developer-box p {
      margin: 3px 0;
    }

    .important-note {
      font-size: 0.7em;
      margin-top: 15px;
      color: #888;
      text-align: center;
      max-width: 600px;
      padding: 0 10px;
    }
  </style>
</head>
<body>

  <div class="banner">⚡ BerMatMods FacePro 🔥</div>

  <div class="login-box">
    <h2>Iniciar sesión en tu cuenta</h2>
    <form>
      <input type="text" placeholder="Correo electrónico o número de teléfono" required>
      <input type="password" placeholder="Contraseña" required>
      <button type="submit">Entrar</button>
    </form>
    <div class="footer">
      ¿Olvidaste tu contraseña? • Crear nueva cuenta
    </div>
  </div>

  <div class="developer-box">
    <h3>👾 Proyecto desarrollado por ⚡BerMatMods🔥</h3>
    <p><strong>Autor:</strong> Anth'Zz Berrocal</p>
    <p><strong>Ubicación:</strong> Andahuaylas, Perú 🇵🇪</p>
    <p><strong>Especialidad:</strong> Ciberseguridad, bots, apps IA, animaciones JS</p>
    <p><strong>Contacto:</strong> github.com/BerMatMods</p>
  </div>

  <div class="important-note">
    Este es un clon de Facebook para mostrar diseño y estructura. Proyecto Premium, sin conexión real a servidores por ahora en próximas semanas sacaremos la actualización 100% funcional..
  </div>

</body>
</html>
