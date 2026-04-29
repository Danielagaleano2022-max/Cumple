# Cumple
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Felicitación Especial 2026</title>
<link href="https://googleapis.com" rel="stylesheet">
<style>
  :root {
    --neon-blue: #00d2ff;
    --neon-green: #00ff99;
    --neon-purple: #bc13fe;
    --glass: rgba(0, 0, 0, 0.9);
  }

  body {
    margin: 0;
    background: #000;
    overflow: hidden;
    font-family: 'Share Tech Mono', monospace;
    color: white;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
  }

  /* Pantalla de Inicio */
  #overlay {
    position: fixed;
    top: 0; left: 0; width: 100%; height: 100%;
    background: black;
    z-index: 100;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .start-btn {
    padding: 15px 30px;
    background: transparent;
    color: var(--neon-blue);
    border: 2px solid var(--neon-blue);
    font-family: 'Orbitron', sans-serif;
    cursor: pointer;
    box-shadow: 0 0 15px var(--neon-blue);
    font-weight: bold;
    letter-spacing: 2px;
    text-transform: uppercase;
  }

  /* HUD Principal */
  .hud-scanner {
    position: relative;
    width: 90%;
    max-width: 360px;
    border: 1px solid rgba(0, 210, 255, 0.3);
    border-radius: 20px;
    padding: 20px;
    background: var(--glass);
    box-shadow: 0 0 40px rgba(0, 210, 255, 0.2);
    z-index: 10;
    backdrop-filter: blur(10px);
    display: none;
  }

  /* Marco de la Foto */
  .photo-frame {
    width: 100%;
    height: 350px; /* Altura suficiente para ver la foto bien */
    overflow: hidden;
    border-radius: 10px;
    border: 1px solid var(--neon-blue);
    margin: 15px 0;
    position: relative;
    background: #000;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  /* ESTO HACE QUE SALGA TODA LA FOTO SIN RECORTAR */
  .photo-main {
    max-width: 100%;
    max-height: 100%;
    object-fit: contain; 
    display: block;
  }

  .scan-line {
    position: absolute;
    top: 0; left: 0; width: 100%; height: 2px;
    background: var(--neon-blue);
    box-shadow: 0 0 15px var(--neon-blue);
    animation: scanning 4s ease-in-out infinite;
    z-index: 12;
  }

  @keyframes scanning { 0%, 100% { top: 0%; } 50% { top: 100%; } }

  .stat-bar-container {
    width: 100%;
    background: #222;
    height: 6px;
    border-radius: 3px;
    margin: 5px 0 10px 0;
    overflow: hidden;
  }

  .stat-bar-fill {
    height: 100%;
    width: 0%;
    background: var(--neon-blue);
    transition: width 2s ease-out;
  }

  #typewriter {
    margin-top: 20px;
    font-size: 15px;
    color: var(--neon-blue);
    text-align: center;
    font-family: 'Orbitron', sans-serif;
    min-height: 100px;
    z-index: 20;
    line-height: 1.5;
  }

  .side-msg {
    position: absolute;
    font-size: 7px;
    color: var(--neon-blue);
    font-family: 'Orbitron', sans-serif;
    letter-spacing: 1px;
    opacity: 0.5;
  }
  .left-msg { left: -80px; transform: rotate(-90deg); top: 50%; }
  .right-msg { right: -80px; transform: rotate(90deg); top: 50%; }

</style>
</head>
<body>

<div id="overlay">
    <button class="start-btn" onclick="startSystem()">ABRIR MENSAJE</button>
</div>

<div class="hud-scanner" id="hud">
    <div class="side-msg left-msg">NUEVOS COMIENZOS</div>
    <div class="side-msg right-msg">MEJORES DESTINOS</div>
    
    <div style="display:flex; justify-content:space-between; font-size:10px; color:var(--neon-blue); margin-bottom:10px;">
        <span>SISTEMA: ACTIVO</span>
        <span>AÑO: 2026</span>
    </div>

    <div class="photo-frame">
        <div class="scan-line"></div>
        <img src="Fondocumple.jpeg" class="photo-main" alt="Felicitación">
    </div>

    <div style="font-size: 11px; color: var(--neon-green);">
        > PROCESANDO ALEGRÍAS
        <div class="stat-bar-container">
            <div id="bar1" class="stat-bar-fill"></div>
        </div>
        
        > CARGANDO DESEOS
        <div class="stat-bar-container">
            <div id="bar2" class="stat-bar-fill" style="background:var(--neon-purple);"></div>
        </div>
    </div>
</div>

<div id="typewriter"></div>

<script>
function startSystem() {
    document.getElementById('overlay').style.display = 'none';
    document.getElementById('hud').style.display = 'block';

    setTimeout(() => {
        document.getElementById('bar1').style.width = '100%';
        document.getElementById('bar2').style.width = '100%';
    }, 300);

    typeWriter();
}

const msg = "> INICIANDO...\n¡FELIZ CUMPLEAÑOS!\nQUE LA VIDA TE REGALE\nPAZ Y MUCHA FELICIDAD EN\nESTA NUEVA ETAPA.\nDISFRUTA TU DÍA AL MÁXIMO. ✨";

let i = 0;
function typeWriter() {
  if (i < msg.length) {
    let char = msg.charAt(i);
    document.getElementById("typewriter").innerHTML += char === '\n' ? '<br>' : char;
    i++;
    setTimeout(typeWriter, 50);
  }
}
</script>

</body>
</html>
