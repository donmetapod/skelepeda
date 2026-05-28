<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Skeletor · Lanzamiento</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Permanent+Marker&family=Russo+One&family=Nunito:wght@400;700&display=swap');

* { margin: 0; padding: 0; box-sizing: border-box; }

body {
  background: #0a0a1f;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 1.5rem;
  font-family: 'Nunito', sans-serif;
}

.card {
  max-width: 500px;
  width: 100%;
  background: #0e0b2a;
  border: 3px solid #6a0dad;
  border-radius: 4px;
  overflow: hidden;
  position: relative;
  box-shadow: 0 0 0 1px #1a0f3a, 0 0 40px rgba(106,13,173,0.5), inset 0 0 60px rgba(0,0,50,0.8);
}

.scanlines {
  position: absolute;
  inset: 0;
  background: repeating-linear-gradient(0deg, transparent, transparent 3px, rgba(0,0,0,0.15) 3px, rgba(0,0,0,0.15) 4px);
  pointer-events: none;
  z-index: 10;
}

.header {
  background: linear-gradient(180deg, #1a0050 0%, #0e0b2a 100%);
  padding: 1.5rem 1.5rem 0;
  text-align: center;
  border-bottom: 2px solid #6a0dad;
}

.top-banner {
  background: #6a0dad;
  margin: -1.5rem -1.5rem 1.2rem;
  padding: 6px;
  font-family: 'Russo One', sans-serif;
  font-size: 0.6rem;
  letter-spacing: 6px;
  color: #d4a0ff;
  text-transform: uppercase;
  text-align: center;
}

.skull-wrap { display: flex; justify-content: center; margin-bottom: 1rem; }

.game-title {
  font-family: 'Permanent Marker', cursive;
  font-size: 4rem;
  color: #00e5ff;
  letter-spacing: 2px;
  text-shadow: 3px 3px 0 #6a0dad, 6px 6px 0 #1a0050;
  line-height: 1;
  margin-bottom: 0.2rem;
}

.tagline {
  font-family: 'Russo One', sans-serif;
  font-size: 0.6rem;
  letter-spacing: 4px;
  color: #9b59b6;
  text-transform: uppercase;
  margin-bottom: 1.2rem;
}

.body { padding: 1.5rem; }

.speech-bubble {
  background: #12084a;
  border: 2px solid #6a0dad;
  border-radius: 4px;
  padding: 14px 18px;
  margin-bottom: 1.4rem;
  position: relative;
  text-align: center;
}
.speech-bubble::before {
  content: '';
  position: absolute;
  top: -10px; left: 50%;
  transform: translateX(-50%);
  border-left: 10px solid transparent;
  border-right: 10px solid transparent;
  border-bottom: 10px solid #6a0dad;
}
.speech-bubble p { color: #d4a0ff; font-size: 0.9rem; line-height: 1.6; font-style: italic; }
.speech-bubble strong { color: #00e5ff; font-style: normal; }

.section-title {
  font-family: 'Russo One', sans-serif;
  font-size: 0.55rem;
  letter-spacing: 4px;
  color: #6a0dad;
  text-transform: uppercase;
  margin-bottom: 10px;
  display: flex;
  align-items: center;
  gap: 8px;
}
.section-title::after { content: ''; flex: 1; height: 1px; background: #6a0dad; opacity: 0.5; }

.details { display: flex; flex-direction: column; gap: 8px; margin-bottom: 1.2rem; }

.detail-row {
  display: flex;
  align-items: center;
  gap: 14px;
  background: rgba(106,13,173,0.12);
  border: 1px solid rgba(106,13,173,0.4);
  border-left: 3px solid #6a0dad;
  border-radius: 2px;
  padding: 10px 14px;
}
.detail-icon { font-size: 1.2rem; flex-shrink: 0; }
.detail-content label {
  display: block; font-size: 0.6rem; letter-spacing: 2px;
  text-transform: uppercase; color: #9b59b6; margin-bottom: 2px;
}
.detail-content span { font-size: 0.95rem; font-weight: 700; color: #e8d5ff; }
.detail-content small { display: block; font-size: 0.75rem; color: #6a0dad; margin-top: 1px; }

.highlights { display: flex; gap: 10px; margin-bottom: 1.4rem; }
.hl {
  flex: 1; text-align: center;
  background: rgba(106,13,173,0.15);
  border: 1px solid rgba(106,13,173,0.4);
  border-top: 3px solid #ff00ff;
  border-radius: 2px;
  padding: 12px 8px;
}
.hl .hl-icon { font-size: 1.3rem; margin-bottom: 4px; }
.hl .hl-label { font-size: 0.55rem; letter-spacing: 2px; text-transform: uppercase; color: #9b59b6; margin-bottom: 4px; }
.hl .hl-value { font-family: 'Russo One', sans-serif; font-size: 0.95rem; color: #ff00ff; }

.rsvp-section {
  background: #12084a;
  border: 2px solid #ff00ff;
  border-radius: 4px;
  padding: 1.2rem;
  margin-bottom: 1rem;
}

.counter-wrap {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
  margin-bottom: 1.2rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid rgba(255,0,255,0.2);
}

.counter-skull { font-size: 2rem; animation: pulse 2s ease-in-out infinite; }
@keyframes pulse { 0%,100%{transform:scale(1)} 50%{transform:scale(1.1)} }

.counter-num {
  font-family: 'Permanent Marker', cursive;
  font-size: 3.5rem;
  color: #ff00ff;
  text-shadow: 2px 2px 0 #6a0dad;
  line-height: 1;
}

.counter-label {
  font-family: 'Russo One', sans-serif;
  font-size: 0.65rem;
  letter-spacing: 2px;
  color: #9b59b6;
  text-transform: uppercase;
  line-height: 1.4;
}

.form-row { display: flex; flex-direction: column; gap: 10px; }

.input-wrap input {
  width: 100%;
  background: #0a0520;
  border: 1px solid rgba(106,13,173,0.6);
  border-radius: 3px;
  padding: 10px 14px;
  color: #e8d5ff;
  font-family: 'Nunito', sans-serif;
  font-size: 0.9rem;
  outline: none;
  transition: border-color 0.2s;
}
.input-wrap input:focus { border-color: #ff00ff; }
.input-wrap input::placeholder { color: rgba(155,89,182,0.5); }

.check-row {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 8px 0;
}
.check-row input[type=checkbox] { accent-color: #ff00ff; width: 16px; height: 16px; cursor: pointer; }
.check-row label { color: #d4a0ff; font-size: 0.85rem; cursor: pointer; }

.btn-rsvp {
  width: 100%;
  background: linear-gradient(135deg, #6a0dad, #ff00ff);
  color: #fff;
  font-family: 'Russo One', sans-serif;
  font-size: 1rem;
  letter-spacing: 3px;
  text-transform: uppercase;
  padding: 13px;
  border: none;
  border-radius: 3px;
  cursor: pointer;
  transition: opacity 0.15s, transform 0.15s;
}
.btn-rsvp:hover { opacity: 0.9; transform: translateY(-1px); }
.btn-rsvp:active { transform: scale(0.98); }
.btn-rsvp:disabled { opacity: 0.5; cursor: not-allowed; transform: none; }

.success-msg {
  display: none;
  text-align: center;
  padding: 1rem 0 0;
  color: #00e5ff;
  font-family: 'Permanent Marker', cursive;
  font-size: 1.1rem;
}

.error-msg {
  display: none;
  text-align: center;
  color: #ff6b6b;
  font-size: 0.8rem;
  margin-top: 6px;
}

.footer-quote {
  text-align: center;
  font-family: 'Permanent Marker', cursive;
  font-size: 1rem;
  color: #00e5ff;
  opacity: 0.7;
  padding: 14px;
  border-top: 1px solid rgba(106,13,173,0.4);
  background: rgba(0,0,0,0.3);
}
</style>
</head>
<body>
<div class="card">
  <div class="scanlines"></div>
  <div class="header">
    <div class="top-banner">⚡ Lanzamiento oficial · Skeletor ⚡</div>
    <div class="skull-wrap">
      <svg width="130" height="150" viewBox="0 0 130 150" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <radialGradient id="sg" cx="50%" cy="45%" r="55%">
            <stop offset="0%" stop-color="#c9a0f0"/>
            <stop offset="100%" stop-color="#5a2080"/>
          </radialGradient>
          <radialGradient id="eg" cx="50%" cy="50%" r="50%">
            <stop offset="0%" stop-color="#00e5ff" stop-opacity="0.9"/>
            <stop offset="100%" stop-color="#0060aa" stop-opacity="0.3"/>
          </radialGradient>
        </defs>
        <ellipse cx="65" cy="58" rx="48" ry="50" fill="url(#sg)" stroke="#ff00ff" stroke-width="1.5"/>
        <ellipse cx="30" cy="80" rx="16" ry="10" fill="#7a30a0" stroke="#ff00ff" stroke-width="1"/>
        <ellipse cx="100" cy="80" rx="16" ry="10" fill="#7a30a0" stroke="#ff00ff" stroke-width="1"/>
        <path d="M28 90 Q28 118 65 122 Q102 118 102 90" fill="#8030b0" stroke="#ff00ff" stroke-width="1.5"/>
        <rect x="37" y="106" width="10" height="14" rx="2" fill="#e8d0ff" stroke="#ff00ff" stroke-width="0.8"/>
        <rect x="50" y="108" width="9" height="14" rx="2" fill="#e8d0ff" stroke="#ff00ff" stroke-width="0.8"/>
        <rect x="62" y="109" width="9" height="14" rx="2" fill="#e8d0ff" stroke="#ff00ff" stroke-width="0.8"/>
        <rect x="74" y="108" width="9" height="14" rx="2" fill="#e8d0ff" stroke="#ff00ff" stroke-width="0.8"/>
        <rect x="86" y="106" width="10" height="14" rx="2" fill="#e8d0ff" stroke="#ff00ff" stroke-width="0.8"/>
        <path d="M58 72 Q65 62 72 72 L70 85 Q65 88 60 85 Z" fill="#1a0050"/>
        <ellipse cx="42" cy="56" rx="15" ry="13" fill="#1a0050" stroke="#ff00ff" stroke-width="1"/>
        <ellipse cx="88" cy="56" rx="15" ry="13" fill="#1a0050" stroke="#ff00ff" stroke-width="1"/>
        <ellipse cx="42" cy="56" rx="9" ry="8" fill="url(#eg)"/>
        <ellipse cx="88" cy="56" rx="9" ry="8" fill="url(#eg)"/>
        <ellipse cx="42" cy="57" rx="4" ry="4" fill="#00e5ff"/>
        <ellipse cx="88" cy="57" rx="4" ry="4" fill="#00e5ff"/>
        <path d="M27 44 Q42 38 55 46" fill="none" stroke="#ff00ff" stroke-width="3" stroke-linecap="round"/>
        <path d="M75 46 Q88 38 103 44" fill="none" stroke="#ff00ff" stroke-width="3" stroke-linecap="round"/>
        <path d="M65 12 L63 28 L67 36 L64 45" fill="none" stroke="#ff00ff" stroke-width="0.8" stroke-dasharray="2,2" opacity="0.5"/>
        <path d="M17 50 Q10 20 65 8 Q120 20 113 50" fill="#1a0050" opacity="0.5"/>
      </svg>
    </div>
    <div class="game-title">SKELETOR</div>
    <div class="tagline">☠ Por el poder de Grayskull… ¡a jugar! ☠</div>
  </div>

  <div class="body">
    <div class="speech-bubble">
      <p>¡Estás invitado al lanzamiento de <strong>Skeletor</strong>!<br>
      Ven, come tacos y sé testigo de algo <strong>épico</strong>.</p>
    </div>

    <div class="section-title">Detalles del ritual</div>
    <div class="details">
      <div class="detail-row">
        <div class="detail-icon">📅</div>
        <div class="detail-content"><label>Fecha</label><span>Sábado 6 de junio, 2025</span></div>
      </div>
      <div class="detail-row">
        <div class="detail-icon">🕑</div>
        <div class="detail-content"><label>Hora</label><span>2:00 PM</span></div>
      </div>
      <div class="detail-row">
        <div class="detail-icon">📍</div>
        <div class="detail-content"><label>Lugar</label><span>Depto de Roy · Plaza Sania</span></div>
      </div>
      <div class="detail-row">
        <div class="detail-icon">🌮</div>
        <div class="detail-content"><label>Menú</label><span>Taquiza</span><small>¡Tacos para mortales y esqueletos!</small></div>
      </div>
    </div>

    <div class="highlights">
      <div class="hl">
        <div class="hl-icon">👫</div>
        <div class="hl-label">Puedes traer</div>
        <div class="hl-value">+1 acompañante</div>
      </div>
      <div class="hl">
        <div class="hl-icon">💜</div>
        <div class="hl-label">Contribución</div>
        <div class="hl-value">$200 por persona</div>
      </div>
    </div>

    <div class="section-title">Confirma tu asistencia</div>

    <div class="rsvp-section">
      <div class="counter-wrap">
        <div class="counter-skull">💀</div>
        <div>
          <div class="counter-num" id="counter">0</div>
          <div class="counter-label">almas<br>confirmadas</div>
        </div>
        <div class="counter-skull">💀</div>
      </div>

      <div class="form-row" id="rsvp-form">
        <div class="input-wrap">
          <input type="text" id="nombre" placeholder="Tu nombre" maxlength="50"/>
        </div>
        <div class="check-row">
          <input type="checkbox" id="acompanante"/>
          <label for="acompanante">Voy con acompañante (+$200)</label>
        </div>
        <button class="btn-rsvp" id="btn-confirm" onclick="confirmar()">☠ ¡Confirmo mi asistencia! ☠</button>
        <div class="error-msg" id="error-msg">Por favor escribe tu nombre para confirmar.</div>
      </div>

      <div class="success-msg" id="success-msg"></div>
    </div>
  </div>

  <div class="footer-quote">"¡Tienen el poder... de venir!" 💀</div>
</div>

<script>
  // Contador usando localStorage (funciona en GitHub Pages)
  const STORAGE_KEY = 'skeletor_rsvp_count';

  function loadCount() {
    const count = parseInt(localStorage.getItem(STORAGE_KEY)) || 0;
    document.getElementById('counter').textContent = count;
  }

  function confirmar() {
    const nombre = document.getElementById('nombre').value.trim();
    const errorMsg = document.getElementById('error-msg');

    if (!nombre) {
      errorMsg.style.display = 'block';
      return;
    }
    errorMsg.style.display = 'none';

    const btn = document.getElementById('btn-confirm');
    btn.disabled = true;
    btn.textContent = 'Confirmando...';

    const acompanante = document.getElementById('acompanante').checked;
    const personas = acompanante ? 2 : 1;

    const current = parseInt(localStorage.getItem(STORAGE_KEY)) || 0;
    const newCount = current + personas;
    localStorage.setItem(STORAGE_KEY, String(newCount));
    document.getElementById('counter').textContent = newCount;

    document.getElementById('rsvp-form').style.display = 'none';
    const msg = document.getElementById('success-msg');
    msg.style.display = 'block';
    msg.innerHTML = acompanante
      ? `¡${nombre} y su acompañante están en la lista! 💀🎉`
      : `¡${nombre} está en la lista de Skeletor! 💀🎉`;
  }

  loadCount();
</script>
</body>
</html>
