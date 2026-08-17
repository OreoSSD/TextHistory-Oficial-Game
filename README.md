[Phase BETA.html](https://github.com/user-attachments/files/31126201/Phase.BETA.html)
# TextHistory-Oficial-Game
Phase BETA
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Origin Texting Hub - Uzyan Company</title>
    <style>
        :root {
            --bg-primary: #0b0914;
            --bg-secondary: #120f24;
            --bg-glass: rgba(18, 15, 36, 0.88);
            --accent-pink: #ff0077;
            --accent-cyan: #00f3ff;
            --accent-purple: #7928ca;
            --text-main: #f3f4f6;
            --text-muted: #8a88a0;
            --border-color: rgba(0, 243, 255, 0.2);
            --radius: 12px;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Courier New', Courier, monospace;
        }

        body {
            background-color: var(--bg-primary);
            color: var(--text-main);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            overflow-x: hidden;
        }

        .galaxy-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at center, #1b0c36 0%, #0b0914 80%);
            z-index: -1;
        }

        header {
            background: #05040a;
            border-bottom: 2px solid rgba(255, 0, 119, 0.4);
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.2rem;
            font-weight: 900;
            color: #fff;
            text-shadow: 0 0 10px var(--accent-pink);
        }

        .logo span {
            color: var(--accent-cyan);
        }

        .hub-container {
            max-width: 1100px;
            width: 95%;
            margin: 2rem auto;
            display: grid;
            grid-template-columns: 350px 1fr;
            gap: 2rem;
            flex: 1;
        }

        @media (max-width: 850px) {
            .hub-container {
                grid-template-columns: 1fr;
            }
        }

        .control-panel {
            background: var(--bg-glass);
            border: 2px solid rgba(255, 0, 119, 0.4);
            border-radius: var(--radius);
            padding: 1.5rem;
            backdrop-filter: blur(12px);
            box-shadow: 0 0 25px rgba(255, 0, 119, 0.15);
            display: flex;
            flex-direction: column;
            gap: 1.2rem;
            height: fit-content;
        }

        .control-panel h3 {
            color: var(--accent-cyan);
            font-size: 0.95rem;
            border-bottom: 1px dashed var(--border-color);
            padding-bottom: 0.5rem;
        }

        .input-group {
            display: flex;
            flex-direction: column;
            gap: 0.4rem;
        }

        .input-group label {
            font-size: 0.78rem;
            color: var(--text-muted);
        }

        .input-group input, .input-group select {
            background: #08060f;
            border: 1px solid var(--border-color);
            color: #fff;
            padding: 8px 12px;
            border-radius: 6px;
            font-size: 0.85rem;
            outline: none;
        }

        .input-group input:focus, .input-group select:focus {
            border-color: var(--accent-cyan);
            box-shadow: 0 0 8px rgba(0, 243, 255, 0.3);
        }

        .btn-action {
            background: linear-gradient(135deg, var(--accent-pink), var(--accent-purple));
            border: 1px solid var(--accent-cyan);
            color: #fff;
            padding: 10px;
            font-weight: bold;
            border-radius: 6px;
            cursor: pointer;
            transition: 0.2s;
            text-align: center;
            font-size: 0.85rem;
        }

        .btn-action:hover {
            opacity: 0.9;
            box-shadow: 0 0 12px var(--accent-pink);
        }

        .character-list-box {
            display: flex;
            flex-direction: column;
            gap: 6px;
            max-height: 120px;
            overflow-y: auto;
            background: #08060f;
            padding: 8px;
            border-radius: 6px;
            border: 1px solid var(--border-color);
        }

        .char-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 0.78rem;
            color: var(--text-main);
            background: #120f24;
            padding: 4px 8px;
            border-radius: 4px;
        }

        .char-item button {
            background: none;
            border: none;
            color: var(--accent-pink);
            cursor: pointer;
            font-weight: bold;
        }

        .chat-frame {
            background: var(--bg-glass);
            border: 2px solid var(--border-color);
            border-radius: var(--radius);
            backdrop-filter: blur(12px);
            box-shadow: 0 0 30px rgba(0, 243, 255, 0.1);
            display: flex;
            flex-direction: column;
            height: 650px;
            position: relative;
            overflow: hidden;
        }

        .chat-header {
            background: #05040a;
            border-bottom: 1px solid var(--border-color);
            padding: 1rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .chat-title-display {
            font-size: 0.95rem;
            color: var(--accent-cyan);
            font-weight: bold;
        }

        .chat-status {
            font-size: 0.72rem;
            color: var(--text-muted);
        }

        .chat-messages {
            flex: 1;
            padding: 1.5rem;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .message-row {
            display: flex;
            width: 100%;
        }

        .message-row.left {
            justify-content: flex-start;
        }

        .message-row.right {
            justify-content: flex-end;
        }

        .message-bubble {
            max-width: 75%;
            padding: 10px 14px;
            border-radius: 10px;
            font-size: 0.88rem;
            line-height: 1.4;
            word-break: break-word;
        }

        .message-row.left .message-bubble {
            background: #1b1635;
            border: 1px solid rgba(0, 243, 255, 0.3);
            color: var(--text-main);
            border-top-left-radius: 2px;
        }

        .message-row.right .message-bubble {
            background: linear-gradient(135deg, rgba(255, 0, 119, 0.25), rgba(121, 40, 202, 0.3));
            border: 1px solid rgba(255, 0, 119, 0.5);
            color: #fff;
            border-top-right-radius: 2px;
        }

        .msg-sender-name {
            font-size: 0.7rem;
            color: var(--text-muted);
            margin-bottom: 3px;
            display: block;
        }

        .chat-input-area {
            background: #05040a;
            border-top: 1px solid var(--border-color);
            padding: 1rem;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .chat-input-row {
            display: flex;
            gap: 10px;
        }

        .chat-input {
            flex: 1;
            background: #08060f;
            border: 1px solid var(--border-color);
            color: #fff;
            padding: 10px 14px;
            border-radius: 6px;
            font-size: 0.88rem;
            outline: none;
        }

        .chat-input:focus {
            border-color: var(--accent-pink);
        }

        .sender-select-dropdown {
            background: #08060f;
            border: 1px solid var(--border-color);
            color: var(--accent-cyan);
            padding: 6px 12px;
            border-radius: 6px;
            font-size: 0.8rem;
            outline: none;
        }

        .presets-toolbar {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
            max-height: 60px;
            overflow-y: auto;
            padding-top: 4px;
        }

        .btn-preset {
            background: rgba(0, 243, 255, 0.08);
            border: 1px solid var(--border-color);
            color: var(--accent-cyan);
            padding: 5px 10px;
            border-radius: 4px;
            font-size: 0.72rem;
            cursor: pointer;
            transition: 0.2s;
        }

        .btn-preset:hover {
            background: rgba(0, 243, 255, 0.2);
            border-color: var(--accent-cyan);
        }

        footer {
            text-align: center;
            padding: 1.5rem;
            color: var(--text-muted);
            font-size: 0.75rem;
            border-top: 1px solid var(--border-color);
            margin-top: auto;
        }
    </style>
</head>
<body>

    <div class="galaxy-bg"></div>

    <header>
        <div class="logo">TERMINAL <span>ORIGIN</span> // TEXTING HUB</div>
        <div style="font-size: 0.75rem; color: var(--accent-cyan);">DEVELOPMENT v2.5</div>
    </header>

    <div class="hub-container">
        <!-- Panel de Configuración Avanzada -->
        <div class="control-panel">
            <h3>⚙️ Configuración del Historial</h3>
            
            <div class="input-group">
                <label>Título del Historial</label>
                <input type="text" id="cfg-title" value="Operación: Rescate Silencioso" oninput="actualizarCabecera()">
            </div>

            <h3>👥 Gestionar Personajes</h3>
            <div class="input-group">
                <label>Nombre del Nuevo Personaje</label>
                <input type="text" id="new-char-name" placeholder="Ej: Uzy, Rayan, Val...">
            </div>
            <div class="input-group">
                <label>Lado y Tono de Voz</label>
                <div style="display: flex; gap: 6px;">
                    <select id="new-char-side" style="flex:1;">
                        <option value="left">Izquierda (A)</option>
                        <option value="right">Derecha (B)</option>
                    </select>
                    <select id="new-char-tone" style="flex:1;">
                        <option value="female">Femenino</option>
                        <option value="male">Masculino</option>
                        <option value="neutral">Neutral</option>
                    </select>
                </div>
            </div>
            <button class="btn-action" onclick="agregarPersonaje()">➕ Agregar Personaje</button>

            <div class="character-list-box" id="character-list-display">
                <!-- Se llenará dinámicamente -->
            </div>

            <h3>💬 Agregar Nuevo Preset</h3>
            <div class="input-group">
                <input type="text" id="new-preset-text" placeholder="Texto rápido de mensaje...">
            </div>
            <button class="btn-action" onclick="agregarPreset()">⚡ Crear Botón Preset</button>

            <button class="btn-action" style="background: rgba(255,0,119,0.2); border-color: var(--accent-pink); margin-top: 5px;" onclick="reiniciarChat()">🗑️ Limpiar Historial</button>
        </div>

        <!-- Zona de Chat Principal -->
        <div class="chat-frame">
            <div class="chat-header">
                <div>
                    <div class="chat-title-display" id="display-title">Operación: Rescate Silencioso</div>
                    <div class="chat-status">● Modo Texto Dinámico Activo (Audio WebAPI)</div>
                </div>
                <div style="font-size: 0.75rem; color: var(--accent-pink);">SECURE PORT</div>
            </div>

            <div class="chat-messages" id="chat-messages">
                <!-- Mensajes renderizados aquí -->
            </div>

            <div class="chat-input-area">
                <div style="display: flex; justify-content: space-between; align-items: center;">
                    <div style="font-size: 0.78rem; color: var(--text-muted);">Enviar como:</div>
                    <select id="active-sender-select" class="sender-select-dropdown">
                        <!-- Opciones de personajes dinámicos -->
                    </select>
                </div>

                <div class="chat-input-row">
                    <input type="text" id="chat-input-text" class="chat-input" placeholder="Escribe un mensaje..." autocomplete="off" onkeydown="if(event.key === 'Enter') enviarMensajePersonalizado();">
                    <button class="btn-action" style="padding: 0 20px;" onclick="enviarMensajePersonalizado()">ENVIAR</button>
                </div>

                <!-- Barra de Presets Dinámicos -->
                <div class="presets-toolbar" id="presets-toolbar">
                    <!-- Botones rápidos generados por usuario -->
                </div>
            </div>
        </div>
    </div>

    <footer>
        <p>© 2026 UZYAN COMPANY — TERMINAL ORIGIN GAMING ZONE</p>
    </footer>

    <script>
        // Web Audio API para sintetizar tonos de voz al enviar mensajes
        const audioCtx = new (window.AudioContext || window.webkitAudioContext)();

        function reproducirSonidoMensaje(tono) {
            if (audioCtx.state === 'suspended') { audioCtx.resume(); }
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();
            osc.connect(gain);
            gain.connect(audioCtx.destination);

            let freqInicio = (tono === 'female') ? 900 : (tono === 'male' ? 300 : 600);
            let freqFin = (tono === 'female') ? 1400 : (tono === 'male' ? 500 : 800);

            osc.type = 'sine';
            osc.frequency.setValueAtTime(freqInicio, audioCtx.currentTime);
            osc.frequency.exponentialRampToValueAtTime(freqFin, audioCtx.currentTime + 0.08);
            gain.gain.setValueAtTime(0.15, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.08);

            osc.start();
            osc.stop(audioCtx.currentTime + 0.08);
        }

        // Estado inicial de Personajes, Presets e Historial
        let personajes = [
            { id: 'p1', nombre: 'Uzy', lado: 'left', tono: 'female' },
            { id: 'p2', nombre: 'Rayan', lado: 'right', tono: 'male' }
        ];

        let presets = [
            "¿Estás listo para iniciar el protocolo?",
            "Afirmativo, sistemas en línea.",
            "Revisando registros de la API...",
            "Todo en orden por aquí."
        ];

        let historialMensajes = [
            { texto: "Iniciando secuencia de conexión con Terminal Origin...", remitenteId: 'p1' },
            { texto: "Conexión establecida de forma segura.", remitenteId: 'p2' }
        ];

        function actualizarCabecera() {
            document.getElementById('display-title').innerText = document.getElementById('cfg-title').value;
        }

        function renderizarPersonajes() {
            const listDisplay = document.getElementById('character-list-display');
            const selectDropdown = document.getElementById('active-sender-select');
            
            listDisplay.innerHTML = '';
            selectDropdown.innerHTML = '';

            personajes.forEach((char, index) => {
                // Item en panel lateral
                const item = document.createElement('div');
                item.className = 'char-item';
                item.innerHTML = `<span><b>${char.nombre}</b> (${char.lado === 'left' ? 'Izq' : 'Der'})</span> ${personajes.length > 1 ? `<button onclick="eliminarPersonaje(${index})">✖</button>` : ''}`;
                listDisplay.appendChild(item);

                // Selector de envío activo
                const option = document.createElement('option');
                option.value = char.id;
                option.innerText = `${char.nombre} (${char.lado === 'left' ? 'Izquierda' : 'Derecha'})`;
                selectDropdown.appendChild(option);
            });

            renderizarChat();
        }

        function agregarPersonaje() {
            const nombreInput = document.getElementById('new-char-name');
            const nombre = nombreInput.value.trim();
            if (!nombre) return;

            const lado = document.getElementById('new-char-side').value;
            const tono = document.getElementById('new-char-tone').value;
            const id = 'char_' + Date.now();

            personajes.push({ id, nombre, lado, tono });
            nombreInput.value = '';
            renderizarPersonajes();
        }

        function eliminarPersonaje(index) {
            personajes.splice(index, 1);
            renderizarPersonajes();
        }

        function renderizarPresets() {
            const toolbar = document.getElementById('presets-toolbar');
            toolbar.innerHTML = '';

            presets.forEach((presetText, index) => {
                const btn = document.createElement('button');
                btn.className = 'btn-preset';
                btn.innerText = presetText.length > 22 ? presetText.substring(0, 20) + '...' : presetText;
                btn.title = presetText;
                btn.onclick = () => enviarPreset(presetText);
                toolbar.appendChild(btn);
            });
        }

        function agregarPreset() {
            const input = document.getElementById('new-preset-text');
            const texto = input.value.trim();
            if (!texto) return;

            presets.push(texto);
            input.value = '';
            renderizarPresets();
        }

        function renderizarChat() {
            const contenedor = document.getElementById('chat-messages');
            contenedor.innerHTML = '';

            historialMensajes.forEach(msg => {
                const char = personajes.find(p => p.id === msg.remitenteId) || personajes[0];
                const row = document.createElement('div');
                row.className = `message-row ${char.lado}`;

                const bubble = document.createElement('div');
                bubble.className = 'message-bubble';

                const senderSpan = document.createElement('span');
                senderSpan.className = 'msg-sender-name';
                senderSpan.innerText = char.nombre;

                const textSpan = document.createElement('span');
                textSpan.innerText = msg.texto;

                bubble.appendChild(senderSpan);
                bubble.appendChild(textSpan);
                row.appendChild(bubble);
                contenedor.appendChild(row);
            });

            contenedor.scrollTop = contenedor.scrollHeight;
        }

        function enviarMensajePersonalizado() {
            const input = document.getElementById('chat-input-text');
            const texto = input.value.trim();
            if (!texto) return;

            const activeId = document.getElementById('active-sender-select').value;
            const char = personajes.find(p => p.id === activeId) || personajes[0];

            reproducirSonidoMensaje(char.tono);
            historialMensajes.push({ texto, remitenteId: char.id });
            input.value = '';
            renderizarChat();
        }

        function enviarPreset(textoPreset) {
            const activeId = document.getElementById('active-sender-select').value;
            const char = personajes.find(p => p.id === activeId) || personajes[0];

            reproducirSonidoMensaje(char.tono);
            historialMensajes.push({ texto: textoPreset, remitenteId: char.id });
            renderizarChat();
        }

        function reiniciarChat() {
            historialMensajes = [];
            renderizarChat();
        }

        // Inicialización general al abrir la página
        renderizarPersonajes();
        renderizarPresets();
    </script>
</body>
</html>
