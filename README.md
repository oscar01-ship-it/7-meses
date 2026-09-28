<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Felices 7 Meses, Mi Amor 💐</title>

    <!-- Fuentes elegantes de Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Caveat:wght@600;700&family=Montserrat:wght@400;500;600;700&display=swap" rel="stylesheet">

    <style>
        /* ==========================================
           1. ESTILOS BASE Y PALETA VIBRANTE
           ========================================== */
        :root {
            --pink-bright: #FF4B91;
            --pink-soft: #FFBFA9;
            --purple-vibrant: #8A2BE2;
            --yellow-sun: #FFD93D;
            --green-leaf: #4E9F3D;
            --bg-gradient: linear-gradient(135deg, #FFDEE9 0%, #B5FFFC 100%);
            --card-bg: rgba(255, 255, 255, 0.93);
            --text-dark: #2C3E50;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background: var(--bg-gradient);
            font-family: 'Montserrat', sans-serif;
            color: var(--text-dark);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow-x: hidden;
            padding: 20px 10px;
            position: relative;
        }

        /* Canvas de destellos y corazones flotantes */
        #bgCanvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .container {
            position: relative;
            z-index: 10;
            max-width: 620px;
            width: 100%;
            margin: 0 auto;
        }

        /* ==========================================
           2. MARCO LINDO CUBIERTO DE FLORES Y TULIPANES
           ========================================== */
        .colorful-frame {
            background: var(--card-bg);
            border-radius: 35px;
            padding: 45px 30px;
            box-shadow: 0 20px 50px rgba(138, 43, 226, 0.25);
            border: 6px solid #FF8E9E;
            outline: 4px dashed #FFD93D;
            outline-offset: -14px;
            text-align: center;
            position: relative;
            backdrop-filter: blur(8px);
            animation: popIn 1.1s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        /* Flores decorativas en las esquinas y bordes del marco */
        .frame-flower {
            position: absolute;
            font-size: 2rem;
            filter: drop-shadow(0 3px 6px rgba(0,0,0,0.15));
            animation: pulseFlower 3s ease-in-out infinite alternate;
        }

        .fl-top-left     { top: -18px; left: -15px; transform: rotate(-20deg); }
        .fl-top-right    { top: -18px; right: -15px; transform: rotate(20deg); }
        .fl-bottom-left  { bottom: -18px; left: -15px; transform: rotate(20deg); }
        .fl-bottom-right { bottom: -18px; right: -15px; transform: rotate(-20deg); }
        
        .fl-mid-left1    { top: 25%; left: -22px; }
        .fl-mid-left2    { top: 65%; left: -22px; }
        .fl-mid-right1   { top: 25%; right: -22px; }
        .fl-mid-right2   { top: 65%; right: -22px; }

        /* ==========================================
           3. ENCABEZADO Y TÍTULOS
           ========================================== */
        .header h1 {
            font-family: 'Caveat', cursive;
            font-size: 3.2rem;
            background: linear-gradient(45deg, #FF1493, #8A2BE2, #FF4500);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 5px;
        }

        .header p.subtitle {
            font-size: 0.95rem;
            font-weight: 600;
            color: #6A1B9A;
            margin-bottom: 22px;
            letter-spacing: 0.5px;
        }

        /* ==========================================
           4. RAMO DE TULIPANES EN EL CENTRO (SVG)
           ========================================== */
        .bouquet-container {
            width: 210px;
            height: 210px;
            margin: 0 auto 18px auto;
            cursor: pointer;
            transition: transform 0.4s ease;
            position: relative;
        }

        .bouquet-container:hover {
            transform: scale(1.08) rotate(2deg);
        }

        .bouquet-svg {
            width: 100%;
            height: 100%;
            filter: drop-shadow(0 10px 15px rgba(255, 75, 145, 0.35));
        }

        /* ==========================================
           5. REPRODUCTOR DE MÚSICA
           ========================================== */
        .music-card {
            background: linear-gradient(135deg, #FFE5EC 0%, #F0E6FF 100%);
            border: 2px solid #FF8E9E;
            border-radius: 20px;
            padding: 12px 20px;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            box-shadow: 0 4px 15px rgba(255, 75, 145, 0.15);
        }

        .music-text {
            text-align: left;
        }

        .music-text .title {
            font-weight: 700;
            font-size: 0.95rem;
            color: #8A2BE2;
        }

        .music-text .status {
            font-size: 0.8rem;
            color: #666;
        }

        .play-btn {
            background: linear-gradient(135deg, #FF4B91, #8A2BE2);
            color: white;
            border: none;
            width: 45px;
            height: 45px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            box-shadow: 0 4px 12px rgba(138, 43, 226, 0.4);
            transition: transform 0.2s ease;
        }

        .play-btn:hover {
            transform: scale(1.1);
        }

        /* ==========================================
           6. CAJA DE MENSAJE PRINCIPAL
           ========================================== */
        .message-card {
            background: #FFFFFF;
            border-radius: 20px;
            padding: 25px;
            text-align: left;
            border-left: 6px solid #FF4B91;
            box-shadow: 0 8px 20px rgba(0,0,0,0.05);
            margin-bottom: 25px;
        }

        .message-card p {
            font-size: 1.02rem;
            line-height: 1.8;
            color: #333;
            font-weight: 500;
        }

        .highlight {
            color: #FF1493;
            font-weight: 700;
        }

        .btn-modal {
            background: linear-gradient(135deg, #FF4B91 0%, #FF8E53 100%);
            color: white;
            border: none;
            padding: 14px 32px;
            font-size: 1rem;
            font-weight: 700;
            border-radius: 30px;
            cursor: pointer;
            box-shadow: 0 8px 22px rgba(255, 75, 145, 0.4);
            transition: all 0.3s ease;
        }

        .btn-modal:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 28px rgba(255, 75, 145, 0.5);
        }

        /* ==========================================
           7. MODAL DE ABRAZO
           ========================================== */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(44, 62, 80, 0.5);
            backdrop-filter: blur(6px);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 100;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.4s ease;
        }

        .modal-overlay.active {
            opacity: 1;
            pointer-events: auto;
        }

        .modal-card {
            background: white;
            padding: 35px 25px;
            border-radius: 25px;
            max-width: 440px;
            width: 90%;
            text-align: center;
            border: 4px solid #FFBFA9;
            box-shadow: 0 20px 40px rgba(0,0,0,0.2);
            transform: scale(0.8);
            transition: transform 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .modal-overlay.active .modal-card {
            transform: scale(1);
        }

        .modal-card h2 {
            font-family: 'Caveat', cursive;
            font-size: 2.6rem;
            color: #FF4B91;
            margin-bottom: 10px;
        }

        .modal-card p {
            font-size: 0.98rem;
            line-height: 1.6;
            margin-bottom: 20px;
            color: #555;
        }

        .btn-close {
            background: transparent;
            border: 2px solid #FF4B91;
            color: #FF4B91;
            padding: 8px 22px;
            border-radius: 20px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s ease;
        }

        .btn-close:hover {
            background: #FF4B91;
            color: white;
        }

        /* Animations */
        @keyframes popIn {
            0% { opacity: 0; transform: scale(0.9) translateY(20px); }
            100% { opacity: 1; transform: scale(1) translateY(0); }
        }

        @keyframes pulseFlower {
            0% { transform: scale(1) rotate(0deg); }
            100% { transform: scale(1.15) rotate(8deg); }
        }

        @media (max-width: 480px) {
            .colorful-frame { padding: 35px 18px; }
            .header h1 { font-size: 2.6rem; }
            .bouquet-container { width: 170px; height: 170px; }
        }
    </style>
</head>
<body>

    <canvas id="bgCanvas"></canvas>

    <!-- Reproductor con pista romántica de alta disponibilidad -->
    <audio id="bgSong" loop crossorigin="anonymous" preload="auto">
        <source src="https://cdn.pixabay.com/download/audio/2022/05/27/audio_1808fbf07a.mp3?filename=romantic-piano-112199.mp3" type="audio/mpeg">
    </audio>

    <div class="container">
        <!-- MARCO LINDO Y COLORIDO CUBIERTO DE FLORES Y TULIPANES -->
        <div class="colorful-frame">
            
            <!-- Flores alrededor del marco -->
            <div class="frame-flower fl-top-left">🌷🌸</div>
            <div class="frame-flower fl-top-right">🌸🌷</div>
            <div class="frame-flower fl-bottom-left">🌷🌼</div>
            <div class="frame-flower fl-bottom-right">🌼🌷</div>
            <div class="frame-flower fl-mid-left1">🌷</div>
            <div class="frame-flower fl-mid-left2">🌸</div>
            <div class="frame-flower fl-mid-right1">🌸</div>
            <div class="frame-flower fl-mid-right2">🌷</div>

            <header class="header">
                <h1>Felices 7 Meses, Mi Amor 🌷</h1>
                <p class="subtitle">Juntos en cada paso del camino</p>
            </header>

            <!-- RAMO DE TULIPANES EN EL CENTRO -->
            <div class="bouquet-container" onclick="toggleModal(true)" title="Haz clic aquí">
                <svg class="bouquet-svg" viewBox="0 0 200 200" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <defs>
                        <linearGradient id="p1" x1="0%" y1="0%" x2="0%" y2="100%">
                            <stop offset="0%" stop-color="#FF9EAA" />
                            <stop offset="100%" stop-color="#FF4365" />
                        </linearGradient>
                        <linearGradient id="p2" x1="0%" y1="0%" x2="0%" y2="100%">
                            <stop offset="0%" stop-color="#FFD07B" />
                            <stop offset="100%" stop-color="#FF9400" />
                        </linearGradient>
                        <linearGradient id="p3" x1="0%" y1="0%" x2="0%" y2="100%">
                            <stop offset="0%" stop-color="#E0AAFF" />
                            <stop offset="100%" stop-color="#7B2CBF" />
                        </linearGradient>
                        <linearGradient id="ribbon" x1="0%" y1="0%" x2="100%" y2="0%">
                            <stop offset="0%" stop-color="#FF1493" />
                            <stop offset="100%" stop-color="#FF85A1" />
                        </linearGradient>
                    </defs>

                    <!-- Tallos -->
                    <g stroke="#4E9F3D" stroke-width="4" stroke-linecap="round">
                        <path d="M100 170 L70 80"/>
                        <path d="M100 170 L85 70"/>
                        <path d="M100 170 L100 65"/>
                        <path d="M100 170 L115 70"/>
                        <path d="M100 170 L130 80"/>
                    </g>

                    <!-- Lazo / Moño del Ramo -->
                    <path d="M85 140 C70 135, 70 155, 85 150 Z" fill="url(#ribbon)"/>
                    <path d="M115 140 C130 135, 130 155, 115 150 Z" fill="url(#ribbon)"/>
                    <circle cx="100" cy="145" r="7" fill="#FF1493"/>
                    <path d="M95 150 L85 175 M105 150 L115 175" stroke="#FF1493" stroke-width="4" stroke-linecap="round"/>

                    <!-- Tulipán 1 (Izquierda) -->
                    <g transform="translate(65, 70) scale(0.7)">
                        <path d="M-15 0 Q-25 -20 -8 -40 Q5 -20 -15 0 Z" fill="url(#p1)"/>
                        <path d="M15 0 Q25 -20 8 -40 Q-5 -20 15 0 Z" fill="url(#p1)"/>
                        <path d="M0 5 Q-20 -20 0 -45 Q20 -20 0 5 Z" fill="#FF4365"/>
                    </g>

                    <!-- Tulipán 2 (Centro-Izquierda) -->
                    <g transform="translate(85, 55) scale(0.75)">
                        <path d="M-15 0 Q-25 -20 -8 -40 Q5 -20 -15 0 Z" fill="url(#p2)"/>
                        <path d="M15 0 Q25 -20 8 -40 Q-5 -20 15 0 Z" fill="url(#p2)"/>
                        <path d="M0 5 Q-20 -20 0 -45 Q20 -20 0 5 Z" fill="#FF9400"/>
                    </g>

                    <!-- Tulipán 3 (Centro Principal) -->
                    <g transform="translate(100, 45) scale(0.85)">
                        <path d="M-18 0 Q-30 -25 -10 -50 Q5 -25 -18 0 Z" fill="url(#p1)"/>
                        <path d="M18 0 Q30 -25 10 -50 Q-5 -25 18 0 Z" fill="url(#p1)"/>
                        <path d="M0 6 Q-22 -22 0 -55 Q22 -22 0 6 Z" fill="#FF1493"/>
                    </g>

                    <!-- Tulipán 4 (Centro-Derecha) -->
                    <g transform="translate(115, 55) scale(0.75)">
                        <path d="M-15 0 Q-25 -20 -8 -40 Q5 -20 -15 0 Z" fill="url(#p3)"/>
                        <path d="M15 0 Q25 -20 8 -40 Q-5 -20 15 0 Z" fill="url(#p3)"/>
                        <path d="M0 5 Q-20 -20 0 -45 Q20 -20 0 5 Z" fill="#7B2CBF"/>
                    </g>

                    <!-- Tulipán 5 (Derecha) -->
                    <g transform="translate(135, 70) scale(0.7)">
                        <path d="M-15 0 Q-25 -20 -8 -40 Q5 -20 -15 0 Z" fill="url(#p1)"/>
                        <path d="M15 0 Q25 -20 8 -40 Q-5 -20 15 0 Z" fill="url(#p1)"/>
                        <path d="M0 5 Q-20 -20 0 -45 Q20 -20 0 5 Z" fill="#FF4365"/>
                    </g>
                </svg>
            </div>

            <!-- REPRODUCTOR MÚSICA -->
            <div class="music-card">
                <div class="music-text">
                    <div class="title">Nuestra Melodía 🎵</div>
                    <div class="status" id="musicStatus">Haz clic para escuchar</div>
                </div>
                <button class="play-btn" id="playBtn" onclick="toggleAudio()" aria-label="Reproducir música">
                    <svg id="playIcon" width="16" height="18" viewBox="0 0 16 18" fill="currentColor">
                        <path d="M1.5 1.5L14.5 9L1.5 16.5V1.5Z"/>
                    </svg>
                </button>
            </div>

            <!-- MENSAJE CON TUS PALABRAS EXACTAS -->
            <div class="message-card">
                <p>
                    Hola amor mío, felices 7 meses contigo son los mejores que me han pasado contigo y por los que vendrán, eres lo más bello que tengo y hermoso amor de mi vida, solo quiero decirte que esto es el inicio de lo que está por venir y que vendrán días mejores, sé que estos días has estado decaída con pocos ánimos, pero aquí me tienes para apoyarte y que nos tenemos el uno al otro aunque estemos a distancia y la distancia es temporal te quiero mucho <span class="highlight">y no sabes cuánto te extraño cada segundo.</span> ❤️✨
                </p>
            </div>

            <button class="btn-modal" onclick="toggleModal(true)">Un Abrazo Fuerte 💖</button>

        </div>
    </div>

    <!-- MODAL POPUP -->
    <div class="modal-overlay" id="modal" onclick="handleOverlayClick(event)">
        <div class="modal-card">
            <h2>¡Te Extraño Muchísimo! 🌷</h2>
            <p>
                Recuerda que la distancia es solo temporal y que pronto estaremos juntos abrazándonos. ¡Gracias por estos 7 meses increíbles! Te amo con todo mi corazón. 💖
            </p>
            <button class="btn-close" onclick="toggleModal(false)">Guardar en el corazón 💕</button>
        </div>
    </div>

    <!-- JAVASCRIPT ANIMACIONES Y AUDIO -->
    <script>
        const audio = document.getElementById('bgSong');
        const playBtn = document.getElementById('playBtn');
        const playIcon = document.getElementById('playIcon');
        const musicStatus = document.getElementById('musicStatus');

        function toggleAudio() {
            if (audio.paused) {
                audio.play().then(() => {
                    playIcon.innerHTML = '<path d="M3 2H6V16H3V2ZM10 2H13V16H10V2Z"/>';
                    musicStatus.textContent = "Sonando con amor 💖";
                }).catch(err => {
                    musicStatus.textContent = "Toca de nuevo para reproducir";
                });
            } else {
                audio.pause();
                playIcon.innerHTML = '<path d="M1.5 1.5L14.5 9L1.5 16.5V1.5Z"/>';
                musicStatus.textContent = "Pausado";
            }
        }

        function toggleModal(show) {
            const modal = document.getElementById('modal');
            if (show) modal.classList.add('active');
            else modal.classList.remove('active');
        }

        function handleOverlayClick(e) {
            if (e.target.classList.contains('modal-overlay')) toggleModal(false);
        }

        /* Partículas flotantes en segundo plano */
        const canvas = document.getElementById('bgCanvas');
        const ctx = canvas.getContext('2d');
        let width, height, particles = [];

        function resize() {
            width = canvas.width = window.innerWidth;
            height = canvas.height = window.innerHeight;
        }
        window.addEventListener('resize', resize);
        resize();

        class Particle {
            constructor() { this.reset(); }
            reset() {
                this.x = Math.random() * width;
                this.y = height + 20;
                this.size = Math.random() * 12 + 8;
                this.speedY = Math.random() * 0.8 + 0.4;
                this.opacity = Math.random() * 0.6 + 0.3;
                this.char = ['🌷', '🌸', '✨', '💖', '💛'][Math.floor(Math.random() * 5)];
            }
            update() {
                this.y -= this.speedY;
                if (this.y < -20) this.reset();
            }
            draw() {
                ctx.save();
                ctx.globalAlpha = this.opacity;
                ctx.font = `${this.size}px serif`;
                ctx.fillText(this.char, this.x, this.y);
                ctx.restore();
            }
        }

        for (let i = 0; i < 25; i++) particles.push(new Particle());

        function animate() {
            ctx.clearRect(0, 0, width, height);
            particles.forEach(p => { p.update(); p.draw(); });
            requestAnimationFrame(animate);
        }
        animate();
    </script>
</body>
</html>
