<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para Mi Amor</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&family=Poppins:wght@300;400;500&display=swap');
        
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #f5f7fa 0%, #ffeef8 100%);
            min-height: 100vh;
        }
        
        .dancing-font {
            font-family: 'Dancing Script', cursive;
        }
        
        .heart-beat {
            animation: heartbeat 1.5s ease-in-out infinite;
        }
        
        @keyframes heartbeat {
            0% { transform: scale(1); }
            25% { transform: scale(1.1); }
            50% { transform: scale(1); }
            75% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        
        .photo-frame {
            border: 15px solid white;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transform: rotate(-5deg);
            transition: all 0.3s ease;
        }
        
        .photo-frame:hover {
            transform: rotate(0deg) scale(1.05);
        }
        
        .message-box {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
        }
        
        .floating {
            animation: floating 3s ease-in-out infinite;
        }
        
        @keyframes floating {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-15px); }
            100% { transform: translateY(0px); }
        }
        
        .btn-romantic {
            background: linear-gradient(45deg, #ff6b8b, #ff8e53);
            transition: all 0.3s ease;
        }
        
        .btn-romantic:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(255, 107, 139, 0.3);
        }
        
        .polaroid {
            background: white;
            padding: 15px 15px 60px 15px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
            transform: rotate(3deg);
            transition: all 0.3s ease;
        }
        
        .polaroid:hover {
            transform: rotate(0deg) scale(1.05);
        }
        
        /* Estilos del reproductor de música */
        .music-player {
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(10px);
            border-radius: 50px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }
        
        .music-player:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }
        
        .progress-container {
            height: 6px;
            background: rgba(0, 0, 0, 0.1);
            border-radius: 3px;
        }
        
        .progress-bar {
            height: 100%;
            background: linear-gradient(90deg, #ff6b8b, #ff8e53);
            border-radius: 3px;
            width: 0%;
            transition: width 0.1s linear;
        }
        
        .volume-slider {
            -webkit-appearance: none;
            width: 100px;
            height: 4px;
            background: rgba(0, 0, 0, 0.1);
            border-radius: 2px;
            outline: none;
        }
        
        .volume-slider::-webkit-slider-thumb {
            -webkit-appearance: none;
            width: 12px;
            height: 12px;
            background: #ff6b8b;
            border-radius: 50%;
            cursor: pointer;
        }
    </style>
</head>
<body class="flex flex-col items-center justify-center p-4">
    <div class="max-w-4xl w-full">
        <!-- Header with title -->
        <header class="text-center mb-12">
            <h1 class="dancing-font text-5xl md:text-6xl font-bold text-pink-600 mb-4">Para Mi Amor</h1>
            <div class="flex justify-center">
                <div class="heart-beat text-4xl text-red-500 mx-2">❤️</div>
                <div class="heart-beat text-4xl text-red-500 mx-2" style="animation-delay: 0.2s">❤️</div>
                <div class="heart-beat text-4xl text-red-500 mx-2" style="animation-delay: 0.4s">❤️</div>
            </div>
        </header>
        
        <!-- Music Player -->
        <div class="music-player p-4 mb-12 max-w-md mx-auto">
            <div class="flex items-center justify-between">
                <div class="flex items-center">
                    <button id="playBtn" class="w-10 h-10 rounded-full bg-pink-500 text-white flex items-center justify-center mr-3">
                        <i class="fas fa-play"></i>
                    </button>
                    <div>
                        <p class="font-medium">Fuentes de Ortiz</p>
                        <p class="text-sm text-gray-600">Ed Maverick</p>
                    </div>
                </div>
                <div class="flex items-center space-x-3">
                    <button id="volumeBtn" class="text-gray-600">
                        <i class="fas fa-volume-up"></i>
                    </button>
                    <div id="volumeContainer" class="hidden">
                        <input type="range" id="volumeSlider" class="volume-slider" min="0" max="1" step="0.01" value="0.7">
                    </div>
                </div>
            </div>
            <div class="mt-3">
                <div class="progress-container">
                    <div id="progressBar" class="progress-bar"></div>
                </div>
                <div class="flex justify-between text-xs text-gray-500 mt-1">
                    <span id="currentTime">0:00</span>
                    <span id="duration">3:30</span>
                </div>
            </div>
            <audio id="audioPlayer" src="c:\Users\ALEXIS ROMARIO\Downloads\FUENTES DE ORTIZ - LOS DEL LIMIT PRÓXIMAMENTE.mp3"></audio>
        </div>
        
        <!-- Main content -->
        <main class="grid md:grid-cols-2 gap-8 items-center">
            <!-- Photo section -->
            <div class="flex justify-center">
                <div class="relative">
                    <div class="photo-frame w-64 h-64 md:w-80 md:h-80 bg-pink-200 overflow-hidden rounded-lg">
                        <!-- Replace with your photo -->
                        <img id="couplePhoto" src="https://images.unsplash.com/photo-1516589178581-6cd7833ae3b2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=774&q=80" 
                             alt="Nosotros" class="w-full h-full object-cover">
                    </div>
                    <div class="absolute -bottom-6 -right-6">
                        <div class="polaroid w-32 h-32">
                            <img src="https://images.unsplash.com/photo-1529626455594-4ff0802cfb7e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=774&q=80" 
                                 alt="Tú" class="w-full h-full object-cover">
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Message section -->
            <div class="message-box p-8">
                <h2 class="dancing-font text-3xl text-pink-600 mb-4">Mi Querida <span id="namePlaceholder">[Su Nombre]</span>,</h2>
                <p class="text-gray-700 mb-4">Cada día a tu lado es un regalo que atesoro profundamente. Tu sonrisa ilumina mis días y tu amor da sentido a mi vida.</p>
                <p class="text-gray-700 mb-4">Eres la persona más increíble que he conocido, y cada momento contigo es especial. Desde la primera vez que te vi, supe que eras alguien único.</p>
                <p class="text-gray-700 mb-6">Este pequeño detalle es solo una muestra de todo lo que siento por ti. Te amo más de lo que las palabras pueden expresar.</p>
                
                <div class="flex items-center">
                    <div class="floating text-4xl mr-4">💌</div>
                    <p class="dancing-font text-xl text-pink-600">Para siempre tuyo,</p>
                </div>
                <p class="dancing-font text-2xl text-pink-600 mt-2">[Tu Nombre]</p>
            </div>
        </main>
        
        <!-- Interactive elements -->
        <div class="mt-16 text-center">
            <button onclick="showSurprise()" class="btn-romantic text-white px-8 py-3 rounded-full font-semibold shadow-lg mb-8">
                <i class="fas fa-gift mr-2"></i> Haz clic para una sorpresa
            </button>
            
            <div id="surprise" class="hidden bg-white p-6 rounded-xl shadow-md max-w-md mx-auto">
                <h3 class="dancing-font text-2xl text-pink-600 mb-4">¡Te amo!</h3>
                <p class="mb-4">Este es solo el comienzo de muchas sorpresas que tengo para ti.</p>
                <div class="flex justify-center space-x-4">
                    <div class="floating text-3xl" style="animation-delay: 0.1s">🌹</div>
                    <div class="floating text-3xl" style="animation-delay: 0.3s">✨</div>
                    <div class="floating text-3xl" style="animation-delay: 0.5s">🥰</div>
                </div>
            </div>
            
            <!-- Memory gallery -->
            <div class="mt-12">
                <h3 class="dancing-font text-3xl text-pink-600 mb-6">Nuestros Recuerdos</h3>
                <div class="grid grid-cols-2 md:grid-cols-4 gap-4 max-w-2xl mx-auto">
                    </div>
                    <div class="polaroid transform -rotate-1">
                        <img src="https://images.unsplash.com/photo-1518621736915-f3b1c41bfd00?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=774&q=80" 
                             alt="Recuerdo 2" class="w-full h-24 object-cover">
                    </div>
                    <div class="polaroid transform rotate-3">
                        <img src="https://images.unsplash.com/photo-1529333166437-7750a6dd5a70?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=774&q=80" 
                             alt="Recuerdo 3" class="w-full h-24 object-cover">
                    </div>
                    <div class="polaroid transform -rotate-2">
                        <img src="https://images.unsplash.com/photo-1518199266791-5375a83190b7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=774&q=80" 
                             alt="Recuerdo 4" class="w-full h-24 object-cover">
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Floating hearts background -->
    <div id="heartsContainer" class="fixed top-0 left-0 w-full h-full pointer-events-none z-0"></div>
    
    <script>
        // Personalize name
        const names = ["Mi Amor", "Mi Vida", "Mi Reina", "Mi Todo", "Mi Cielo"];
        let currentNameIndex = 0;
        const nameElement = document.getElementById('namePlaceholder');
        
        setInterval(() => {
            currentNameIndex = (currentNameIndex + 1) % names.length;
            nameElement.textContent = names[currentNameIndex];
            nameElement.classList.add('animate-pulse');
            setTimeout(() => nameElement.classList.remove('animate-pulse'), 1000);
        }, 3000);
        
        // Show surprise
        function showSurprise() {
            const surprise = document.getElementById('surprise');
            surprise.classList.toggle('hidden');
            
            if (!surprise.classList.contains('hidden')) {
                // Create floating hearts
                createHearts(15);
            }
        }
        
        // Create floating hearts
        function createHearts(count) {
            const container = document.getElementById('heartsContainer');
            const colors = ['text-red-400', 'text-pink-400', 'text-rose-400', 'text-red-300'];
            const emojis = ['❤️', '💖', '💘', '💝', '💗', '💓'];
            
            for (let i = 0; i < count; i++) {
                const heart = document.createElement('div');
                heart.className = 'absolute text-2xl opacity-0';
                heart.style.left = Math.random() * 100 + '%';
                heart.style.top = Math.random() * 100 + '%';
                heart.textContent = emojis[Math.floor(Math.random() * emojis.length)];
                heart.classList.add(colors[Math.floor(Math.random() * colors.length)]);
                
                container.appendChild(heart);
                
                // Animate heart
                setTimeout(() => {
                    heart.style.transition = 'all 4s linear';
                    heart.style.opacity = '1';
                    heart.style.transform = `translate(${Math.random() * 100 - 50}px, ${-Math.random() * 150 - 100}px) rotate(${Math.random() * 360}deg)`;
                    
                    setTimeout(() => {
                        heart.remove();
                    }, 4000);
                }, i * 200);
            }
        }
        
        // Change main photo on hover
        const couplePhoto = document.getElementById('couplePhoto');
        const originalSrc = couplePhoto.src;
        const alternateSrc = "https://images.unsplash.com/photo-1529333166437-7750a6dd5a70?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=774&q=80";
        
        couplePhoto.parentElement.addEventListener('mouseenter', () => {
            couplePhoto.src = alternateSrc;
        });
        
        couplePhoto.parentElement.addEventListener('mouseleave', () => {
            couplePhoto.src = originalSrc;
        });
        
        // Create initial floating hearts
        window.addEventListener('load', () => {
            createHearts(5);
            setInterval(() => createHearts(3), 5000);
        });
        
        // Music Player Functionality
        const audioPlayer = document.getElementById('audioPlayer');
        const playBtn = document.getElementById('playBtn');
        const progressBar = document.getElementById('progressBar');
        const currentTimeElement = document.getElementById('currentTime');
        const durationElement = document.getElementById('duration');
        const volumeBtn = document.getElementById('volumeBtn');
        const volumeContainer = document.getElementById('volumeContainer');
        const volumeSlider = document.getElementById('volumeSlider');
        
        // Play/Pause button
        playBtn.addEventListener('click', () => {
            if (audioPlayer.paused) {
                audioPlayer.play();
                playBtn.innerHTML = '<i class="fas fa-pause"></i>';
            } else {
                audioPlayer.pause();
                playBtn.innerHTML = '<i class="fas fa-play"></i>';
            }
        });
        
        // Update progress bar
        audioPlayer.addEventListener('timeupdate', () => {
            const currentTime = audioPlayer.currentTime;
            const duration = audioPlayer.duration;
            const progressPercent = (currentTime / duration) * 100;
            progressBar.style.width = `${progressPercent}%`;
            
            // Update time display
            currentTimeElement.textContent = formatTime(currentTime);
            if (duration) {
                durationElement.textContent = formatTime(duration);
            }
        });
        
        // Click on progress bar to seek
        const progressContainer = document.querySelector('.progress-container');
        progressContainer.addEventListener('click', (e) => {
            const width = progressContainer.clientWidth;
            const clickX = e.offsetX;
            const duration = audioPlayer.duration;
            audioPlayer.currentTime = (clickX / width) * duration;
        });
        
        // Volume control
        volumeBtn.addEventListener('click', () => {
            volumeContainer.classList.toggle('hidden');
        });
        
        volumeSlider.addEventListener('input', () => {
            audioPlayer.volume = volumeSlider.value;
            
            // Update volume icon
            if (volumeSlider.value == 0) {
                volumeBtn.innerHTML = '<i class="fas fa-volume-mute"></i>';
            } else if (volumeSlider.value < 0.5) {
                volumeBtn.innerHTML = '<i class="fas fa-volume-down"></i>';
            } else {
                volumeBtn.innerHTML = '<i class="fas fa-volume-up"></i>';
            }
        });
        
        // Format time (seconds to MM:SS)
        function formatTime(seconds) {
            const minutes = Math.floor(seconds / 60);
            const secs = Math.floor(seconds % 60);
            return `${minutes}:${secs < 10 ? '0' : ''}${secs}`;
        }
        
        // When song ends
        audioPlayer.addEventListener('ended', () => {
            playBtn.innerHTML = '<i class="fas fa-play"></i>';
            progressBar.style.width = '0%';
            currentTimeElement.textContent = '0:00';
        });
        
        // Set initial volume
        audioPlayer.volume = 0.7;
    </script>
</body>
</html>
