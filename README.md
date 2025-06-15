<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>🌊 𝓟𝓪𝓻𝓪𝓲𝓼𝓸 𝓶𝓪𝓰𝓰 🩵</title>
  <style>
    /* Reset básico */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body, html {
      height: 100%;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: #b3e5fc; /* azul claro */
      color: #003c71; /* azul oscuro */
      overflow-x: hidden;
    }

    /* VIDEO DE FONDO */
    #video-fondo {
      position: fixed;
      top: 0; left: 0;
      width: 100vw;
      height: 100vh;
      object-fit: cover;
      z-index: -1;
      opacity: 0.4;
      filter: brightness(0.7);
    }

    /* ENCABEZADO */
    header {
      background: #0277bd; /* azul brillante */
      color: white;
      padding: 30px 20px;
      text-align: center;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
      position: relative;
      z-index: 10;
    }
    header h1 {
      font-size: 2.5rem;
      margin-bottom: 5px;
    }
    header p {
      font-size: 1.2rem;
      font-weight: 300;
    }

    /* MENÚ */
    nav {
      background: #0288d1;
      box-shadow: 0 2px 5px rgba(0,0,0,0.15);
      position: sticky;
      top: 0;
      z-index: 15;
    }
    nav ul {
      list-style: none;
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
    }
    nav ul li {
      position: relative;
    }
    nav ul li a {
      display: block;
      padding: 14px 25px;
      color: white;
      text-decoration: none;
      font-weight: 600;
      transition: background 0.3s ease;
      cursor: pointer;
    }
    nav ul li:hover > a {
      background: #01579b;
    }

    /* Submenú */
    nav ul li ul {
      display: none;
      position: absolute;
      top: 100%;
      left: 0;
      background: #03a9f4;
      border-radius: 0 0 6px 6px;
      min-width: 160px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      z-index: 20;
    }
    nav ul li:hover ul {
      display: block;
    }
    nav ul li ul li a {
      padding: 10px 15px;
      font-weight: 500;
      color: #003c71;
      background: #b3e5fc;
    }
    nav ul li ul li a:hover {
      background: #81d4fa;
      color: #000;
    }

    /* CONTENIDO PRINCIPAL */
    main {
      max-width: 1000px;
      margin: 40px auto 60px;
      background: rgba(255, 255, 255, 0.85);
      border-radius: 15px;
      padding: 30px;
      box-shadow: 0 8px 20px rgba(0,0,0,0.1);
      position: relative;
      z-index: 10;
    }
    main h2 {
      color: #01579b;
      margin-bottom: 15px;
      font-size: 2rem;
      text-align: center;
    }
    main p {
      line-height: 1.6;
      margin-bottom: 20px;
      font-size: 1.1rem;
    }

    /* LISTAS */
    ul.lista-mar {
      list-style-type: square;
      margin-left: 20px;
      color: #0277bd;
      font-weight: 600;
      font-size: 1.1rem;
    }
    ul.lista-mar li {
      margin-bottom: 10px;
    }

    /* GALERÍA */
    .galeria {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 15px;
      margin-top: 30px;
    }
    .galeria img {
      width: 100%;
      border-radius: 12px;
      border: 3px solid #0288d1;
      transition: transform 0.3s ease;
      cursor: pointer;
      box-shadow: 0 4px 8px rgba(2, 120, 189, 0.4);
    }
    .galeria img:hover {
      transform: scale(1.1);
      border-color: #01579b;
      box-shadow: 0 6px 14px rgba(1, 87, 155, 0.7);
    }

    /* FORMULARIO */
    form {
      margin-top: 40px;
      background: #e1f5fe;
      padding: 25px;
      border-radius: 12px;
      box-shadow: inset 0 0 15px #81d4fa;
    }
    form label {
      display: block;
      margin-bottom: 6px;
      font-weight: 600;
      color: #01579b;
    }
    form input, form textarea {
      width: 100%;
      padding: 10px;
      border-radius: 8px;
      border: 2px solid #0288d1;
      font-size: 1rem;
      margin-bottom: 20px;
      transition: border-color 0.3s ease;
      font-family: inherit;
    }
    form input:focus, form textarea:focus {
      border-color: #01579b;
      outline: none;
    }
    form button {
      background: #0277bd;
      color: white;
      font-weight: 700;
      padding: 12px 25px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      font-size: 1.1rem;
      transition: background 0.3s ease;
    }
    form button:hover {
      background: #01579b;
    }

    /* AUDIO CONTROL */
    .audio-control {
      text-align: center;
      margin-top: 25px;
    }
    .audio-control button {
      background: #0288d1;
      color: white;
      border: none;
      padding: 12px 22px;
      border-radius: 25px;
      font-weight: 600;
      cursor: pointer;
      font-size: 1.1rem;
      box-shadow: 0 4px 10px rgba(2, 120, 189, 0.6);
      transition: background 0.3s ease;
    }
    .audio-control button:hover {
      background: #01579b;
    }

    /* PIE DE PÁGINA */
    footer {
      background: #0277bd;
      color: white;
      padding: 18px 20px;
      text-align: center;
      font-size: 1rem;
      position: relative;
      z-index: 10;
    }
    footer a {
      color: #b3e5fc;
      text-decoration: none;
      margin: 0 10px;
      font-weight: 600;
    }
    footer a:hover {
      text-decoration: underline;
    }

    /* ANIMACIÓN DE OLA */
    .ola {
      position: fixed;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 120px;
      background: #03a9f4;
      overflow: hidden;
      z-index: 5;
    }

    .ola svg {
      position: absolute;
      bottom: 0;
      left: 50%;
      width: 200%;
      height: 120px;
      transform: translateX(-50%);
      animation: moverOla 6s linear infinite;
    }

    @keyframes moverOla {
      0% { transform: translateX(-50%) translateY(0); }
      50% { transform: translateX(-45%) translateY(-15px); }
      100% { transform: translateX(-50%) translateY(0); }
    }

    /* RESPONSIVE */
    @media(max-width: 600px) {
      nav ul {
        flex-direction: column;
      }
      nav ul li {
        width: 100%;
        text-align: center;
      }
      nav ul li ul {
        position: static;
        box-shadow: none;
        background: #81d4fa;
      }
    }
  </style>
</head>
<body>

  <!-- VIDEO DE FONDO -->
  <video autoplay muted loop playsinline id="video-fondo">
    <source src="../video del mar 2.mp4" type="video/mp4" />
    
  </video>

  <!-- ENCABEZADO -->
  <header>
    <h1>🌊 𝓟𝓪𝓻𝓪𝓲𝓼𝓸 𝓶𝓪𝓰𝓰 🩵</h1>
    <p>🦀🫧𝒮𝓊𝓂ℯ𝓇𝓰ℯ𝓉ℯ ℯ𝓃 𝓁𝒶 𝒸𝒶𝓁𝓂𝒶 𝓎 𝒷ℯ𝓁𝓁ℯ𝓏𝒶 𝒹ℯ𝓁 ℴ𝒸ℯ𝒶𝓃ℴ 🌊🌸</p>
  </header>

  <!-- MENÚ -->
  <nav>
    <ul>
      <li><a href="#">Inicio</a></li>
      <li>
        <a href="#">Explorar</a>
        <ul>
          <li><a href="#galeria">Galería</a></li>
          <li><a href="#listas">Listas</a></li>
          <li><a href="#contacto">Contacto</a></li>
        </ul>
      </li>
      <li>
</a><a href="https://www.nationalgeographic.com/animals/article/weirdest-sea-creatures" target="_blank" style="color:rgb(242, 242, 248);">
  Conoce animales exóticos del mar
    </ul>
  </nav>

  <!-- CONTENIDO PRINCIPAL -->
  <main>
    <section id="listas">
      <h2>🌊ᴅɪsғʀᴜᴛᴀ ᴇʟ ᴍᴀʀ ᴄᴏɴ☀</h2>
      <ul class="lista-mar">
        <li>𝐴𝑚𝑎𝑛𝑒𝑐𝑒𝑟𝑒𝑠 𝑦 𝑎𝑡𝑎𝑟𝑑𝑒𝑐𝑒𝑟𝑒𝑠 𝑝𝑖𝑛𝑡𝑎𝑑𝑜𝑠 𝑑𝑒 𝑎𝑧𝑢𝑙 𝑦 𝑛𝑎𝑟𝑎𝑛𝑗𝑎 🌈🫧</li>
        <li>𝐸𝑙 𝑠𝑜𝑛𝑖𝑑𝑜 𝑟𝑒𝑙𝑎𝑗𝑎𝑛𝑡𝑒 𝑑𝑒 𝑙𝑎𝑠 𝑜𝑙𝑎𝑠🌊</li>
        <li>𝑝𝑎𝑠𝑒𝑜𝑠 𝑝𝑜𝑟 𝑝𝑙𝑎𝑦𝑎𝑠 𝑑𝑒 𝑎𝑟𝑒𝑛𝑎⛱🏝</li>
        <li>𝐿𝑎 𝑏𝑟𝑖𝑠𝑎 𝑓𝑟𝑒𝑠𝑐𝑎 𝑞𝑢𝑒 𝑑𝑒𝑠𝑝𝑒𝑗𝑎 𝑙𝑎 𝑚𝑒𝑛𝑡𝑒 🏖🫧</li>
      </ul>
    </section>

  
    <section id="galeria">
      <h2>Galería de paisajes marinos</h2>
      <div class="galeria"alt="Mar">
        <img src="../todo sobre el mar/2.jpg" alt="Playa">
        <img src="../todo sobre el mar/3.jpg" alt="Océano">
        <img src="../todo sobre el mar/4.jpg" alt="Atardecer">
        <img src="../todo sobre el mar/5.jpg" alt="Atardecer">
        <img src="../todo sobre el mar/6.jpg" alt="Atardecer">
        <img src="../todo sobre el mar/7.jpg" alt="Atardecer">
        <img src="../todo sobre el mar/8.jpg" alt="Atardecer">
        <img src="../todo sobre el mar/9.jpg" alt="Atardecer">
        <img src="../todo sobre el mar/10.jpg" alt="Atardecer">
        <img src="../todo sobre el mar/11.jpg" alt="Atardecer">
        <img src="../todo sobre el mar/12.png" alt="Atardecer">
        <img src="../todo sobre el mar/13.jpg" alt="Atardecer">
      </div>
    </section>

    <section id="contacto">
      <h2>Contáctanos</h2>
      <form>
        <label for="nombre">Nombre:</label>
        <input type="text" id="nombre" name="nombre" placeholder="Tu nombre" required />

        <label for="email">Correo electrónico:</label>
        <input type="email" id="email" name="email" placeholder="tu@correo.com" required />

        <label for="mensaje">Mensaje:</label>
        <textarea id="mensaje" name="mensaje" rows="5" placeholder="Escribe tu mensaje aquí..." required></textarea>

        <button type="submit">Enviar</button>
      </form>
    </section>

    <div class="audio-control">
      <button onclick="document.getElementById('audio-mar').play()">🎧 Escuchar sonido del mar</button>
      <button onclick="document.getElementById('audio-mar').pause()">⏸ Pausar sonido</button>
      <audio id="audio-mar" loop>
        <source src="../olar del mar sonido.mp3" type="audio/mpeg" />
        
      </audio>
    </div>
  </main>

  <!-- ANIMACIÓN DE OLA -->
  <div class="ola" aria-hidden="true">
    <svg viewBox="0 0 1440 320" preserveAspectRatio="none">
      <path fill="#0288d1" fill-opacity="1" d="M0,160L60,165.3C120,171,240,181,360,186.7C480,192,600,192,720,181.3C840,171,960,149,1080,154.7C1200,160,1320,192,1380,208L1440,224L1440,320L1380,320C1320,320,1200,320,1080,320C960,320,840,320,720,320C600,320,480,320,360,320C240,320,120,320,60,320L0,320Z"></path>
    </svg>
  </div>

  <!-- PIE DE PÁGINA -->
  <footer>
    <p>
      &copy; 2025 🌊 𝓟𝓪𝓻𝓪𝓲𝓼𝓸 𝓶𝓪𝓰𝓰 🩵

      <a href="https://instagram.com" target="_blank" rel="noopener noreferrer">Instagram</a> | 
      <a href="mailto:info@marazul.com">Contáctanos</a>
    </p>
  </footer>
</body>
</html>
