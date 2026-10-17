<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="theme-color" content="#ffe8f1" />
  <title>Un cumpleaños muy especial ♡</title>
  <style>
    :root {
      --pink: #ec76a6;
      --hot-pink: #d94f8c;
      --soft-pink: #ffe6f0;
      --pale-pink: #fff6fa;
      --rose: #bd587e;
      --ink: #75465d;
      --white: #fffdfd;
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0;
      min-height: 100vh;
      color: var(--ink);
      font-family: "Trebuchet MS", "Segoe UI", sans-serif;
      background:
        radial-gradient(circle at 15% 12%, rgba(255,255,255,.95) 0 2px, transparent 3px),
        radial-gradient(circle at 83% 28%, rgba(255,255,255,.8) 0 3px, transparent 4px),
        linear-gradient(135deg, #fff5fa 0%, #ffe3ef 48%, #fff1f7 100%);
      overflow-x: hidden;
    }

    button, input { font: inherit; }
    button { -webkit-tap-highlight-color: transparent; }

    .petal-rain {
      position: fixed;
      inset: 0;
      overflow: hidden;
      pointer-events: none;
      z-index: 0;
    }
    .petal {
      position: absolute;
      top: -35px;
      width: 13px;
      height: 18px;
      border-radius: 80% 15% 75% 25%;
      background: linear-gradient(145deg, #ffc2da, #f28cb7);
      opacity: .62;
      animation: fall linear infinite;
      filter: drop-shadow(0 2px 2px rgba(185, 75, 123, .1));
    }
    @keyframes fall {
      0% { transform: translate3d(0, -5vh, 0) rotate(0deg); }
      100% { transform: translate3d(45px, 110vh, 0) rotate(520deg); }
    }

    .screen {
      min-height: 100vh;
      position: relative;
      z-index: 1;
      display: grid;
      place-items: center;
      padding: 28px 16px;
    }
    .login-card, .letter-card {
      width: min(100%, 460px);
      padding: clamp(25px, 6vw, 42px);
      text-align: center;
      border: 1px solid rgba(255,255,255,.9);
      border-radius: 30px;
      background: rgba(255, 253, 253, .83);
      box-shadow: 0 20px 60px rgba(186, 84, 126, .16), inset 0 0 0 5px rgba(255,255,255,.42);
      backdrop-filter: blur(10px);
    }
    .tiny-flower { font-size: 2rem; letter-spacing: 8px; margin-bottom: 8px; }
    .eyebrow {
      color: var(--hot-pink);
      text-transform: uppercase;
      letter-spacing: .2em;
      font-size: .72rem;
      font-weight: 800;
    }
    h1, h2, p { margin-top: 0; }
    h1 {
      margin-bottom: 12px;
      color: #c94880;
      font-family: Georgia, "Times New Roman", serif;
      font-weight: 700;
      font-size: clamp(2rem, 8vw, 3.1rem);
      line-height: 1.12;
    }
    .login-copy { color: #93647a; line-height: 1.65; margin: 0 auto 24px; max-width: 34ch; }
    .password-wrap { text-align: left; margin: 0 0 14px; }
    label { display: block; margin: 0 0 8px 5px; color: #9b5375; font-size: .9rem; font-weight: 700; }
    input[type="password"] {
      width: 100%;
      border: 1.5px solid #f1b6ce;
      border-radius: 15px;
      padding: 14px 16px;
      color: #75465d;
      background: #fff9fc;
      outline: none;
      transition: border-color .2s, box-shadow .2s;
    }
    input[type="password"]:focus { border-color: var(--pink); box-shadow: 0 0 0 4px rgba(236,118,166,.15); }
    .primary-btn {
      width: 100%;
      border: 0;
      border-radius: 999px;
      padding: 14px 20px;
      background: linear-gradient(100deg, #ed80ad, #d95791);
      color: white;
      font-weight: 800;
      cursor: pointer;
      box-shadow: 0 9px 20px rgba(217,87,145,.23);
      transition: transform .18s, box-shadow .18s;
    }
    .primary-btn:hover { transform: translateY(-2px); box-shadow: 0 12px 23px rgba(217,87,145,.3); }
    .primary-btn:active { transform: translateY(0); }
    .error { min-height: 1.25em; margin: 12px 0 0; color: #bd3b6a; font-size: .88rem; }
    .little-note { margin: 16px 0 0; color: #b88aa0; font-size: .76rem; }

    #birthdayScreen { display: none; padding-top: 40px; padding-bottom: 50px; }
    .birthday-shell { width: min(100%, 920px); margin: auto; }
    .hero {
      position: relative;
      text-align: center;
      padding: clamp(25px, 5vw, 48px) 18px 28px;
    }
    .wreath { font-size: clamp(1.3rem, 4vw, 2rem); letter-spacing: .22em; margin-bottom: 16px; }
    .hero h1 { font-size: clamp(2.8rem, 9vw, 5.3rem); margin: 10px auto 16px; text-shadow: 0 3px 0 rgba(255,255,255,.8); }
    .hero-subtitle { font-size: clamp(1rem, 3vw, 1.2rem); line-height: 1.7; max-width: 600px; margin: auto; color: #89596f; }
    .sparkle { display: inline-block; animation: twinkle 1.8s ease-in-out infinite alternate; }
    @keyframes twinkle { from { transform: scale(.85) rotate(-8deg); opacity: .65; } to { transform: scale(1.12) rotate(8deg); opacity: 1; } }

    .feature-card {
      display: grid;
      grid-template-columns: 1fr minmax(130px, 220px);
      align-items: center;
      gap: clamp(16px, 4vw, 34px);
      margin: 12px 0 25px;
      padding: clamp(20px, 5vw, 38px);
      border-radius: 28px;
      border: 1px solid rgba(255,255,255,.95);
      background: rgba(255,255,255,.79);
      box-shadow: 0 15px 45px rgba(186,84,126,.12);
    }
    .feature-card h2 { color: #cc5288; font: 700 clamp(1.45rem, 4vw, 2.1rem)/1.2 Georgia, serif; margin-bottom: 12px; }
    .feature-card p { line-height: 1.8; margin-bottom: 0; }
    .pochacco-frame {
      min-height: 190px;
      display: grid;
      place-items: center;
      position: relative;
      border-radius: 24px;
      background: radial-gradient(circle, #fff 0%, #ffe6f0 70%);
      overflow: hidden;
    }
    .pochacco-frame::before, .pochacco-frame::after {
      content: "✿";
      position: absolute;
      color: #ec80ad;
      font-size: 2rem;
      opacity: .85;
    }
    .pochacco-frame::before { left: 10px; top: 9px; transform: rotate(-18deg); }
    .pochacco-frame::after { right: 11px; bottom: 8px; transform: rotate(20deg); }
    .pochacco-frame img { display: block; max-width: 100%; width: 190px; max-height: 225px; object-fit: contain; position: relative; z-index: 1; filter: drop-shadow(0 8px 7px rgba(117,70,93,.09)); }
    .image-caption { font-size: .68rem; color: #b68a9d; margin-top: 10px; }

    .message-heading { text-align: center; font: 700 clamp(1.7rem, 5vw, 2.4rem) Georgia, serif; color: #c94880; margin: 35px 0 20px; }
    .messages { display: grid; grid-template-columns: repeat(2, minmax(0,1fr)); gap: 16px; }
    .message {
      position: relative;
      min-height: 145px;
      padding: 24px 22px 20px;
      border-radius: 22px;
      background: rgba(255,255,255,.84);
      border: 1px solid rgba(244,185,209,.75);
      box-shadow: 0 9px 25px rgba(186,84,126,.08);
      line-height: 1.7;
    }
    .message .flower { display: block; margin-bottom: 8px; font-size: 1.35rem; }
    .message p { margin: 0; }
    .message:nth-child(even) { transform: translateY(8px); }
    .final-note {
      margin: 34px auto 0;
      padding: clamp(25px, 5vw, 42px);
      text-align: center;
      border-radius: 28px;
      border: 1px dashed #e99abb;
      background: rgba(255,241,247,.88);
    }
    .final-note h2 { font: 700 clamp(1.6rem, 5vw, 2.3rem) Georgia, serif; color: #c94880; }
    .final-note p { line-height: 1.85; max-width: 620px; margin: 0 auto 22px; }
    .letter-btn { width: auto; min-width: 210px; }
    .secret-letter {
      display: none;
      margin: 22px auto 0;
      max-width: 600px;
      padding: 22px;
      text-align: left;
      border-radius: 18px;
      background: rgba(255,255,255,.82);
      line-height: 1.8;
      animation: popin .45s ease both;
    }
    @keyframes popin { from { opacity: 0; transform: translateY(8px) scale(.98); } to { opacity: 1; transform: translateY(0) scale(1); } }
    footer { padding: 30px 12px 8px; text-align: center; color: #b47f97; font-size: .8rem; }
    .back-btn { display: block; width: auto; margin: 20px auto 0; padding: 10px 18px; color: #bd6289; background: rgba(255,255,255,.6); border: 1px solid #f2c0d5; border-radius: 999px; cursor: pointer; }

    @media (max-width: 620px) {
      .feature-card { grid-template-columns: 1fr; text-align: center; }
      .pochacco-frame { min-height: 175px; grid-row: 1; }
      .pochacco-frame img { width: 150px; max-height: 190px; }
      .messages { grid-template-columns: 1fr; }
      .message:nth-child(even) { transform: none; }
      .message { min-height: auto; }
    }
    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after { animation-duration: .01ms !important; animation-iteration-count: 1 !important; scroll-behavior: auto !important; transition-duration: .01ms !important; }
      .petal-rain { display: none; }
    }
  </style>
</head>
<body>
  <div class="petal-rain" id="petalRain" aria-hidden="true"></div>

  <main>
    <section class="screen" id="loginScreen" aria-labelledby="loginTitle">
      <div class="login-card">
        <div class="tiny-flower" aria-hidden="true">🌸 🌷 🌸</div>
        <p class="eyebrow">un pequeño detalle para ti</p>
        <h1 id="loginTitle">Hay una sorpresa<br>esperándote ♡</h1>
        <p class="login-copy">Preparé un rinconcito lleno de flores, cariño y palabras bonitas. Pero primero… tienes que abrir la puertita. 💌</p>
        <form id="passwordForm">
          <div class="password-wrap">
            <label for="password">Contraseña secreta</label>
            <input id="password" name="password" type="password" placeholder="DD/MM/AAAA" autocomplete="off" required aria-describedby="passwordError" />
          </div>
          <button class="primary-btn" type="submit">Abrir mi sorpresa ♡</button>
          <p class="error" id="passwordError" role="status" aria-live="polite"></p>
        </form>
        <p class="little-note">Hecho con mucho cariño y pétalos rositas ✿</p>
      </div>
    </section>

    <section class="screen" id="birthdayScreen" aria-labelledby="birthdayTitle">
      <div class="birthday-shell">
        <header class="hero">
          <div class="wreath" aria-hidden="true">🌷 ✿ 🌸 ✿ 🌷</div>
          <p class="eyebrow">hoy es un día para celebrar</p>
          <h1 id="birthdayTitle">¡Feliz cumpleaños! <span class="sparkle">♡</span></h1>
          <p class="hero-subtitle">Que hoy te sobren sonrisas, abrazos bonitos y motivos para recordar lo especial que eres. Este pequeño espacio es solo para ti. 💗</p>
        </header>

        <section class="feature-card" aria-label="Un deseo de cumpleaños">
          <div>
            <h2>Un día tan bonito como tú</h2>
            <p>Deseo que esta nueva vuelta al sol esté llena de momentos que te hagan feliz, personas que te quieran de verdad y sueños que poco a poco se vuelvan realidad. Nunca olvides lo mucho que vales. 🌸</p>
          </div>
          <div>
            <div class="pochacco-frame">
              <img src="https://www.sanrio.co.jp/wp-content/uploads/2022/06/list-pochacco.png" alt="Pochacco, personaje de Sanrio" loading="lazy" onerror="this.style.display='none'; this.parentElement.insertAdjacentHTML('beforeend','<span style=&quot;font-size:5rem&quot; aria-label=&quot;perrito decorativo&quot;>🐶</span>');" />
            </div>
            <p class="image-caption">Un saludito de Pochacco ♡ · personaje de Sanrio</p>
          </div>
        </section>

        <h2 class="message-heading">Un ramo de mensajitos para ti</h2>
        <section class="messages" aria-label="Mensajes de cumpleaños">
          <article class="message"><span class="flower" aria-hidden="true">🌸</span><p>Espero que la vida te regale tantas razones para sonreír como pétalos tiene un jardín.</p></article>
          <article class="message"><span class="flower" aria-hidden="true">🌷</span><p>Que nunca te falten amor, tranquilidad, salud, aventuras bonitas y personas que te hagan sentir en casa.</p></article>
          <article class="message"><span class="flower" aria-hidden="true">💗</span><p>Hoy celebra todo lo que eres y todo lo lindo que todavía te falta vivir. ¡Te esperan cosas hermosas!</p></article>
          <article class="message"><span class="flower" aria-hidden="true">🌺</span><p>Ojalá cada deseo que pidas encuentre su camino y cada nuevo día te acerque un poquito más a tus sueños.</p></article>
          <article class="message"><span class="flower" aria-hidden="true">🌼</span><p>Gracias por ser una personita única. Que siempre tengas cerca motivos para reír y gente que cuide tu corazón.</p></article>
          <article class="message"><span class="flower" aria-hidden="true">🎀</span><p>Este día es tuyo: consiéntete, disfruta mucho y recuerda que mereces cosas bonitas hoy y todos los días.</p></article>
        </section>

        <section class="final-note">
          <div class="tiny-flower" aria-hidden="true">💐 💗 💐</div>
          <h2>Y antes de que te vayas…</h2>
          <p>Te dejo una última cartita escondida. Ábrela cuando quieras leer unas palabras más. ✨</p>
          <button class="primary-btn letter-btn" id="letterButton" type="button" aria-expanded="false" aria-controls="secretLetter">Abrir cartita 💌</button>
          <div class="secret-letter" id="secretLetter">
            <p>Feliz cumpleaños, de todo corazón. 💗</p>
            <p>Ojalá hoy puedas ver, aunque sea por un momentito, lo especial que eres y la alegría que puedes llevar a la vida de los demás. Deseo que este nuevo año venga acompañado de oportunidades bonitas, aprendizajes, risas sinceras y muchísima paz.</p>
            <p>Que florezcan tus sueños, que tengas fuerzas para los días difíciles y que nunca te falte alguien con quien compartir los días felices. Te mando un ramo enorme de flores rositas y los mejores deseos. 🌸🌷</p>
            <p style="text-align:right; margin-bottom:0;">Con mucho cariño, para ti ♡</p>
          </div>
        </section>
        <footer>Hecho con flores, estrellitas y mucho cariño ✿</footer>
        <button class="back-btn" id="backButton" type="button">Volver a la portada</button>
      </div>
    </section>
  </main>

  <script>
    // Contraseña de entrada solicitada: 20/10/2007.
    // Nota: al ser una página estática, esto es una sorpresa visual, no seguridad real.
    const correctPassword = '20/10/2007';
    const loginScreen = document.getElementById('loginScreen');
    const birthdayScreen = document.getElementById('birthdayScreen');
    const passwordForm = document.getElementById('passwordForm');
    const passwordInput = document.getElementById('password');
    const passwordError = document.getElementById('passwordError');
    const letterButton = document.getElementById('letterButton');
    const secretLetter = document.getElementById('secretLetter');
    const backButton = document.getElementById('backButton');

    passwordForm.addEventListener('submit', (event) => {
      event.preventDefault();
      // Acepta la fecha con diagonales, guiones, puntos o incluso sin separadores.
      // Ejemplos válidos: 20/10/2007, 20-10-2007, 20.10.2007 y 20102007.
      const enteredPassword = passwordInput.value.normalize('NFKC').replace(/\D/g, '');
      if (enteredPassword === correctPassword.replace(/\D/g, '')) {
        passwordError.textContent = '';
        loginScreen.style.display = 'none';
        birthdayScreen.style.display = 'grid';
        document.title = '¡Feliz cumpleaños! ♡';
        window.scrollTo({ top: 0, behavior: 'smooth' });
      } else {
        passwordError.textContent = 'Esa no es la contraseña correcta. Inténtalo de nuevo 💗';
        passwordInput.value = '';
        passwordInput.focus();
      }
    });

    letterButton.addEventListener('click', () => {
      const isOpen = secretLetter.style.display === 'block';
      secretLetter.style.display = isOpen ? 'none' : 'block';
      letterButton.textContent = isOpen ? 'Abrir cartita 💌' : 'Cerrar cartita ♡';
      letterButton.setAttribute('aria-expanded', String(!isOpen));
    });

    backButton.addEventListener('click', () => {
      birthdayScreen.style.display = 'none';
      loginScreen.style.display = 'grid';
      passwordInput.value = '';
      passwordInput.focus();
      window.scrollTo({ top: 0, behavior: 'smooth' });
    });

    // Pétalos flotantes para decorar el fondo sin cargar librerías externas.
    const petalRain = document.getElementById('petalRain');
    for (let i = 0; i < 24; i++) {
      const petal = document.createElement('span');
      petal.className = 'petal';
      petal.style.left = `${Math.random() * 100}%`;
      petal.style.animationDuration = `${9 + Math.random() * 12}s`;
      petal.style.animationDelay = `${Math.random() * -20}s`;
      petal.style.opacity = `${0.25 + Math.random() * 0.5}`;
      petal.style.transform = `rotate(${Math.random() * 360}deg)`;
      const size = 8 + Math.random() * 10;
      petal.style.width = `${size}px`;
      petal.style.height = `${size * 1.35}px`;
      petalRain.appendChild(petal);
    }
  </script>
</body>
</html>
