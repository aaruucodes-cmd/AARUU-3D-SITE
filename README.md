<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>💖✨ Grand Romantic 3D Birthday · Love Universe ✨💖</title>
    <style>
        /* ===== EPIC ROMANTIC AESTHETIC ===== */
        body {
            margin: 0;
            overflow: hidden;
            font-family: 'Quicksand', 'Segoe UI', cursive, sans-serif;
            background: #0a0010;
        }
        #canvas-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
        }
        .atmosphere {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 40% 30%, rgba(255,105,180,0.15) 0%, rgba(138,43,226,0.1) 60%, rgba(0,0,0,0.3) 100%);
            pointer-events: none;
            z-index: 2;
        }
        /* UI OVERLAY */
        #ui-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 20;
            pointer-events: none;
        }
        .top-bar {
            position: absolute;
            top: 20px;
            left: 20px;
            right: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            pointer-events: auto;
        }
        .logo {
            color: #ffe4f2;
            font-size: 1.8rem;
            font-weight: 700;
            text-shadow: 0 0 30px #ff1493;
            letter-spacing: 8px;
            backdrop-filter: blur(8px);
            padding: 8px 25px;
            border-radius: 60px;
            background: rgba(20,5,30,0.3);
            border: 1px solid #ffb6c1;
        }
        .nav-buttons {
            display: flex;
            gap: 12px;
        }
        .nav-btn {
            background: rgba(30,10,40,0.5);
            backdrop-filter: blur(10px);
            border: 1.5px solid rgba(255,182,193,0.7);
            color: #fff0f5;
            padding: 12px 24px;
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: 600;
            letter-spacing: 2px;
            cursor: pointer;
            box-shadow: 0 0 25px rgba(255,20,147,0.4);
            text-shadow: 0 0 15px #ff69b4;
            transition: 0.3s;
            pointer-events: auto;
        }
        .nav-btn:hover {
            background: rgba(100,20,70,0.8);
            border-color: #ffb6c1;
            box-shadow: 0 0 40px #ff1493;
            transform: scale(1.08);
        }
        .bottom-panel {
            position: absolute;
            bottom: 25px;
            left: 20px;
            right: 20px;
            display: flex;
            justify-content: space-between;
            align-items: flex-end;
            pointer-events: auto;
        }
        .hint-text {
            color: #ffd0dd;
            background: rgba(0,0,0,0.2);
            padding: 8px 20px;
            border-radius: 40px;
            backdrop-filter: blur(5px);
            font-size: 1rem;
            border-left: 4px solid deeppink;
        }
        .birthday-message {
            color: rgba(255,240,245,0.95);
            text-shadow: 0 0 30px #ff69b4, 0 0 60px #8a2be2;
            font-size: 1.5rem;
            letter-spacing: 6px;
            font-weight: 400;
            backdrop-filter: blur(4px);
            padding: 12px 30px;
            border-radius: 60px;
            background: rgba(20,5,30,0.2);
            border: 1px solid rgba(255,182,193,0.5);
            text-align: center;
        }
        .music-control {
            position: absolute;
            bottom: 25px;
            right: 20px;
            pointer-events: auto;
        }
        #playMusicBtn {
            background: rgba(255,105,180,0.3);
            border: 1px solid pink;
            color: white;
            padding: 10px 20px;
            border-radius: 40px;
            backdrop-filter: blur(5px);
            cursor: pointer;
            font-size: 1rem;
        }
        /* Modals */
        .modal-overlay {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(10,0,20,0.75);
            backdrop-filter: blur(8px);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 40;
            opacity: 0; visibility: hidden;
            transition: 0.3s;
            pointer-events: auto;
        }
        .modal-overlay.active { opacity: 1; visibility: visible; }
        .modal-card {
            background: rgba(40,10,30,0.7);
            backdrop-filter: blur(15px);
            border: 2px solid #ffb6c1;
            border-radius: 50px;
            padding: 30px 40px;
            max-width: 700px;
            width: 90%;
            box-shadow: 0 0 80px #ff69b4, 0 0 150px #8a2be2;
            color: #ffe4f2;
            text-align: center;
            transform: scale(0.9);
            transition: 0.3s;
            max-height: 85vh;
            overflow-y: auto;
        }
        .modal-overlay.active .modal-card { transform: scale(1); }
        .modal-card h2 { font-size: 2.8rem; margin-bottom: 20px; text-shadow: 0 0 30px hotpink; }
        .close-btn {
            background: rgba(255,105,180,0.4); border: 1px solid pink; color: white;
            padding: 12px 30px; border-radius: 40px; font-size: 1.2rem; cursor: pointer; margin-top: 20px;
        }
        /* Gallery with animated pictures */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(3,1fr);
            gap: 20px;
            margin: 20px 0;
        }
        .gallery-card {
            aspect-ratio: 1;
            background: rgba(255,200,220,0.15);
            border-radius: 25px;
            border: 1.5px solid rgba(255,182,193,0.6);
            box-shadow: 0 0 20px rgba(255,20,147,0.2);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: 0.3s;
            backdrop-filter: blur(4px);
            padding: 8px;
        }
        .gallery-card:hover {
            transform: scale(1.03);
            border-color: #ff69b4;
            box-shadow: 0 0 35px #ff1493;
        }
        .animated-pic {
            width: 100%;
            height: 80%;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .pic-label {
            color: #ffe4f2;
            font-size: 0.9rem;
            text-shadow: 0 0 8px deeppink;
            margin-top: 5px;
        }
        /* Game container */
        #game-container {
            position: absolute; top: 100px; left: 30px; width: 320px; background: rgba(20,5,30,0.6);
            backdrop-filter: blur(12px); border-radius: 30px; border: 2px solid #ffb6c1;
            padding: 20px; z-index: 30; display: none; pointer-events: auto;
        }
        #game-container.active { display: block; }
        #treasure-container {
            position: absolute; bottom: 150px; right: 30px; width: 260px; background: rgba(20,5,30,0.6);
            backdrop-filter: blur(12px); border-radius: 30px; border: 2px solid gold; padding: 15px;
            z-index: 30; display: none; pointer-events: auto; color: #fff0e0;
        }
        #treasure-container.active { display: block; }
        .treasure-btn { background: #b8860b; color: white; border: none; padding: 8px; border-radius: 30px; margin-top: 10px; cursor: pointer; }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;600;700&display=swap" rel="stylesheet">
</head>
<body>
    <div id="canvas-container"></div>
    <div class="atmosphere"></div>

    <div id="ui-container">
        <div class="top-bar">
            <div class="logo">💖 LOVEVERSE 💖</div>
            <div class="nav-buttons">
                <button class="nav-btn" id="letterBtn">💌 Letters</button>
                <button class="nav-btn" id="galleryBtn">🖼️ Memories</button>
                <button class="nav-btn" id="giftBtn">🎁 Gifts</button>
                <button class="nav-btn" id="gameBtn">🎮 Game</button>
                <button class="nav-btn" id="treasureBtn">🔮 Treasure</button>
                <button class="nav-btn" id="fireworksBtn">✨ Fireworks</button>
            </div>
        </div>
        <div class="bottom-panel">
            <div class="hint-text" id="dynamic-hint">✨ Click gifts · Find treasures · Catch hearts ✨</div>
            <div class="birthday-message">🌸 Happy Birthday, My Eternal Love 🌸</div>
        </div>
        <div class="music-control">
            <button id="playMusicBtn">🎵 Play Romantic Music</button>
        </div>
    </div>

    <!-- Game container -->
    <div id="game-container">
        <h3 style="color:#ffd0dd; text-align:center;">💕 Catch the Hearts 💕</h3>
        <canvas id="game-canvas" width="280" height="280" style="border-radius:20px; background:rgba(0,0,0,0.2);"></canvas>
        <div style="color:white; font-size:1.5rem; margin:10px;">Score: <span id="score-value">0</span></div>
        <button class="nav-btn" id="reset-game" style="padding:8px 20px;">New Game</button>
        <button class="nav-btn" id="close-game" style="padding:8px 20px; background:#6a2c5e;">Close</button>
    </div>

    <!-- Treasure hunt -->
    <div id="treasure-container">
        <h4 style="color:gold;">🔮 Secret Treasure</h4>
        <p>Find the hidden heart somewhere in the scene! Click it to reveal a secret message.</p>
        <p id="treasure-message" style="font-style:italic;">💎 You found it! "You are my greatest treasure." 💎</p>
        <button class="treasure-btn" id="close-treasure">Close</button>
    </div>

    <!-- Modals -->
    <div class="modal-overlay" id="letterModal">
        <div class="modal-card">
            <h2>💌 Love Letters 💌</h2>
            <div style="text-align:left; max-height:300px; overflow-y:auto; padding:10px;">
                <p style="font-size:1.3rem;">📜 Letter #1<br>Every sunrise reminds me of your smile. You are my light. Happy birthday, my love.</p>
                <p style="font-size:1.3rem;">📜 Letter #2<br>In this vast universe, I found you. And I'll cherish you forever. 💖</p>
                <p style="font-size:1.3rem;">📜 Letter #3<br>Today we celebrate you — the most beautiful soul. I love you endlessly.</p>
            </div>
            <button class="close-btn" data-modal="letterModal">Close</button>
        </div>
    </div>

    <!-- MEMORIES MODAL WITH ANIMATED PICTURES -->
    <div class="modal-overlay" id="galleryModal">
        <div class="modal-card">
            <h2>🖼️ Our Animated Memories</h2>
            <div class="gallery-grid" id="animated-gallery">
                <!-- Will be populated by JS with animated SVGs -->
            </div>
            <p style="margin-top:10px; opacity:0.9;">✨ Click on any memory to enlarge the feeling ✨</p>
            <button class="close-btn" data-modal="galleryModal">Close</button>
        </div>
    </div>

    <div class="modal-overlay" id="giftMessageModal">
        <div class="modal-card">
            <h2>🎁 A Gift for You</h2>
            <p id="gift-message-text" style="font-size:1.8rem;">You are my everything.</p>
            <button class="close-btn" data-modal="giftMessageModal">Thank you 💝</button>
        </div>
    </div>

    <div class="modal-overlay" id="secretModal">
        <div class="modal-card">
            <h2>🔓 Secret Revealed!</h2>
            <p id="secret-message">You are the reason I believe in magic.</p>
            <button class="close-btn" data-modal="secretModal">💖</button>
        </div>
    </div>

    <script type="importmap">
        {
            "imports": {
                "three": "https://unpkg.com/three@0.128.0/build/three.module.js",
                "three/addons/": "https://unpkg.com/three@0.128.0/examples/jsm/"
            }
        }
    </script>

    <script type="module">
        // ==================== ANIMATED PICTURES SETUP ====================
        // Create animated SVG cards for the gallery
        function createAnimatedMemoryCards() {
            const galleryGrid = document.getElementById('animated-gallery');
            if (!galleryGrid) return;
            
            // Define 6 animated pictures as inline SVGs with CSS animations
            const memories = [
                {
                    title: "First Kiss",
                    svg: `<svg viewBox="0 0 100 100" width="100%" height="100%">
                        <defs>
                            <radialGradient id="grad1" cx="50%" cy="50%"><stop offset="0%" stop-color="#ffb6c1"/><stop offset="100%" stop-color="#ff1493"/></radialGradient>
                        </defs>
                        <circle cx="50" cy="50" r="40" fill="url(#grad1)" opacity="0.3">
                            <animate attributeName="r" values="40;45;40" dur="3s" repeatCount="indefinite"/>
                            <animate attributeName="opacity" values="0.3;0.6;0.3" dur="3s" repeatCount="indefinite"/>
                        </circle>
                        <path d="M50 35 C50 35, 30 20, 30 40 C30 60, 50 75, 50 75 C50 75, 70 60, 70 40 C70 20, 50 35, 50 35Z" fill="#ff69b4" opacity="0.9">
                            <animateTransform attributeName="transform" type="scale" values="1;1.05;1" dur="2s" repeatCount="indefinite"/>
                            <animate attributeName="fill" values="#ff69b4;#ff1493;#ff69b4" dur="4s" repeatCount="indefinite"/>
                        </path>
                        <text x="50" y="92" text-anchor="middle" fill="#ffe4f2" font-size="8">First Kiss</text>
                    </svg>`
                },
                {
                    title: "Starry Night",
                    svg: `<svg viewBox="0 0 100 100" width="100%" height="100%">
                        <rect width="100" height="100" fill="#1a0a2e"/>
                        <circle cx="20" cy="30" r="2" fill="white"><animate attributeName="opacity" values="0.2;1;0.2" dur="2s" repeatCount="indefinite"/></circle>
                        <circle cx="80" cy="20" r="3" fill="#ffe4f2"><animate attributeName="opacity" values="0.5;1;0.5" dur="3s" repeatCount="indefinite"/></circle>
                        <circle cx="40" cy="70" r="1.5" fill="white"><animate attributeName="opacity" values="0;1;0" dur="2.5s" repeatCount="indefinite"/></circle>
                        <circle cx="70" cy="60" r="2" fill="#ffb6c1"><animate attributeName="opacity" values="0.3;1;0.3" dur="1.8s" repeatCount="indefinite"/></circle>
                        <path d="M50 50 L55 60 L65 62 L58 70 L60 80 L50 75 L40 80 L42 70 L35 62 L45 60 Z" fill="#ffd700" opacity="0.8">
                            <animateTransform attributeName="transform" type="rotate" values="0 50 50;360 50 50" dur="20s" repeatCount="indefinite"/>
                        </path>
                        <text x="50" y="92" text-anchor="middle" fill="#fff" font-size="8">Starry Night</text>
                    </svg>`
                },
                {
                    title: "Dancing Hearts",
                    svg: `<svg viewBox="0 0 100 100" width="100%" height="100%">
                        <rect width="100" height="100" fill="#2d0a2e"/>
                        <g>
                            <path d="M25 25 L30 35 L40 37 L33 45 L35 55 L25 50 L15 55 L17 45 L10 37 L20 35 Z" fill="#ff69b4">
                                <animateTransform attributeName="transform" type="translate" values="0,0; 5,-5; 0,0" dur="2s" repeatCount="indefinite"/>
                            </path>
                            <path d="M70 60 L75 70 L85 72 L78 80 L80 90 L70 85 L60 90 L62 80 L55 72 L65 70 Z" fill="#ffb6c1">
                                <animateTransform attributeName="transform" type="translate" values="0,0; -5,5; 0,0" dur="2.5s" repeatCount="indefinite"/>
                            </path>
                            <path d="M50 30 L55 40 L65 42 L58 50 L60 60 L50 55 L40 60 L42 50 L35 42 L45 40 Z" fill="#ff1493">
                                <animateTransform attributeName="transform" type="scale" values="1;1.1;1" dur="1.8s" repeatCount="indefinite"/>
                            </path>
                        </g>
                        <text x="50" y="92" text-anchor="middle" fill="#ffe4f2" font-size="8">Dancing Hearts</text>
                    </svg>`
                },
                {
                    title: "Sunset Love",
                    svg: `<svg viewBox="0 0 100 100" width="100%" height="100%">
                        <defs><linearGradient id="sunset" x1="0" y1="0" x2="0" y2="1"><stop offset="0%" stop-color="#ff9a9e"/><stop offset="100%" stop-color="#fecfef"/></linearGradient></defs>
                        <rect width="100" height="100" fill="url(#sunset)"/>
                        <circle cx="70" cy="30" r="15" fill="#ffd700" opacity="0.9">
                            <animate attributeName="r" values="15;17;15" dur="4s" repeatCount="indefinite"/>
                        </circle>
                        <path d="M30 80 Q50 60 70 80" stroke="#ff1493" stroke-width="3" fill="none">
                            <animate attributeName="d" values="M30 80 Q50 60 70 80;M30 80 Q50 70 70 80;M30 80 Q50 60 70 80" dur="3s" repeatCount="indefinite"/>
                        </path>
                        <text x="50" y="92" text-anchor="middle" fill="#4a0030" font-size="8">Sunset Love</text>
                    </svg>`
                },
                {
                    title: "Floating Petals",
                    svg: `<svg viewBox="0 0 100 100" width="100%" height="100%">
                        <rect width="100" height="100" fill="#3d1c3d"/>
                        <ellipse cx="30" cy="40" rx="6" ry="4" fill="#ffb6c1" transform="rotate(30 30 40)">
                            <animateTransform attributeName="transform" type="translate" values="0,0; -10,-20; 0,0" dur="5s" repeatCount="indefinite"/>
                        </ellipse>
                        <ellipse cx="70" cy="60" rx="5" ry="3" fill="#ff69b4" transform="rotate(-20 70 60)">
                            <animateTransform attributeName="transform" type="translate" values="0,0; 15,-15; 0,0" dur="6s" repeatCount="indefinite"/>
                        </ellipse>
                        <ellipse cx="50" cy="70" rx="7" ry="4" fill="#ffaacc">
                            <animateTransform attributeName="transform" type="translate" values="0,0; -5,10; 0,0" dur="4s" repeatCount="indefinite"/>
                        </ellipse>
                        <text x="50" y="92" text-anchor="middle" fill="#ffe4f2" font-size="8">Floating Petals</text>
                    </svg>`
                },
                {
                    title: "Moonlight",
                    svg: `<svg viewBox="0 0 100 100" width="100%" height="100%">
                        <rect width="100" height="100" fill="#0f0c29"/>
                        <circle cx="50" cy="40" r="20" fill="#f5f5dc" opacity="0.8">
                            <animate attributeName="opacity" values="0.8;1;0.8" dur="5s" repeatCount="indefinite"/>
                        </circle>
                        <path d="M50 80 Q30 60 50 50 Q70 60 50 80" fill="#ffb6c1" opacity="0.6">
                            <animate attributeName="d" values="M50 80 Q30 60 50 50 Q70 60 50 80;M50 80 Q20 60 50 45 Q80 60 50 80;M50 80 Q30 60 50 50 Q70 60 50 80" dur="7s" repeatCount="indefinite"/>
                        </path>
                        <text x="50" y="92" text-anchor="middle" fill="#fff" font-size="8">Moonlight</text>
                    </svg>`
                }
            ];

            galleryGrid.innerHTML = '';
            memories.forEach(mem => {
                const card = document.createElement('div');
                card.className = 'gallery-card';
                card.innerHTML = `
                    <div class="animated-pic">${mem.svg}</div>
                    <div class="pic-label">${mem.title}</div>
                `;
                card.addEventListener('click', () => {
                    alert(`✨ ${mem.title}: A beautiful moment we shared. ✨`);
                });
                galleryGrid.appendChild(card);
            });
        }

        // Call after DOM ready
        window.addEventListener('DOMContentLoaded', createAnimatedMemoryCards);

        // ==================== THREE.JS SCENE ====================
        import * as THREE from 'three';
        import { OrbitControls } from 'three/addons/controls/OrbitControls.js';
        import { CSS2DRenderer, CSS2DObject } from 'three/addons/renderers/CSS2DRenderer.js';

        const scene = new THREE.Scene();
        scene.background = new THREE.Color('#0d0314');
        scene.fog = new THREE.FogExp2('#1a0a2e', 0.0018);
        const camera = new THREE.PerspectiveCamera(45, window.innerWidth/window.innerHeight, 0.1, 1000);
        camera.position.set(0, 3, 22);
        const renderer = new THREE.WebGLRenderer({ antialias: true });
        renderer.setSize(window.innerWidth, window.innerHeight);
        renderer.shadowMap.enabled = true;
        renderer.shadowMap.type = THREE.PCFSoftShadowMap;
        document.getElementById('canvas-container').appendChild(renderer.domElement);
        
        const cssRenderer = new CSS2DRenderer();
        cssRenderer.setSize(window.innerWidth, window.innerHeight);
        cssRenderer.domElement.style.pointerEvents = 'none';
        document.getElementById('canvas-container').appendChild(cssRenderer.domElement);

        const controls = new OrbitControls(camera, renderer.domElement);
        controls.enableDamping = true;
        controls.dampingFactor = 0.05;
        controls.autoRotate = true;
        controls.autoRotateSpeed = 0.6;
        controls.enableZoom = true;
        controls.enablePan = true;
        controls.maxPolarAngle = Math.PI/1.7;
        controls.target.set(0, 1.8, 0);

        // Lighting
        scene.add(new THREE.AmbientLight(0x404060, 0.5));
        const sunLight = new THREE.DirectionalLight(0xffbbdd, 1.4);
        sunLight.position.set(3, 8, 6);
        sunLight.castShadow = true;
        sunLight.shadow.mapSize.width = 2048;
        sunLight.shadow.mapSize.height = 2048;
        sunLight.shadow.camera.near = 1; sunLight.shadow.camera.far = 30;
        sunLight.shadow.camera.left = -12; sunLight.shadow.camera.right = 12;
        sunLight.shadow.camera.top = 12; sunLight.shadow.camera.bottom = -12;
        scene.add(sunLight);
        
        const fillLight1 = new THREE.PointLight(0xff69b4, 1.5, 30); fillLight1.position.set(-4,4,5); scene.add(fillLight1);
        const fillLight2 = new THREE.PointLight(0xba7df5, 1.3, 30); fillLight2.position.set(5,3,-6); scene.add(fillLight2);
        const backRim = new THREE.PointLight(0xcc88ff, 1.0); backRim.position.set(-3,2,-10); scene.add(backRim);

        // Giant Heart Particles
        const heartGroup = new THREE.Group();
        function heartCurve(t, s=1) {
            const x = 16 * Math.pow(Math.sin(t),3);
            const y = 13*Math.cos(t) - 5*Math.cos(2*t) - 2*Math.cos(3*t) - Math.cos(4*t);
            return new THREE.Vector3(x*0.055*s, y*0.055*s, 0);
        }
        const particleCount = 12000;
        const pos = new Float32Array(particleCount*3);
        const col = new Float32Array(particleCount*3);
        for (let i=0; i<particleCount; i++) {
            const t = Math.random()*Math.PI*2;
            const sc = 0.9 + Math.random()*0.8;
            const base = heartCurve(t, sc);
            const z = (Math.random()-0.5)*2.2;
            const xOff = (Math.random()-0.5)*0.35;
            const yOff = (Math.random()-0.5)*0.35;
            pos[i*3] = base.x + xOff;
            pos[i*3+1] = base.y + yOff;
            pos[i*3+2] = z;
            const mix = new THREE.Color(0xff1493).lerp(new THREE.Color(0xffb6c1), Math.random());
            col[i*3]=mix.r; col[i*3+1]=mix.g; col[i*3+2]=mix.b;
        }
        const heartGeo = new THREE.BufferGeometry();
        heartGeo.setAttribute('position', new THREE.BufferAttribute(pos,3));
        heartGeo.setAttribute('color', new THREE.BufferAttribute(col,3));
        const tex = (()=>{const c=document.createElement('canvas');c.width=64;c.height=64;const g=c.getContext('2d');const grad=g.createRadialGradient(32,32,0,32,32,32);grad.addColorStop(0,'white');grad.addColorStop(0.6,'#ffb6c1');grad.addColorStop(1,'rgba(255,140,180,0)');g.fillStyle=grad;g.fillRect(0,0,64,64);return new THREE.CanvasTexture(c);})();
        heartGroup.add(new THREE.Points(heartGeo, new THREE.PointsMaterial({size:0.14, map:tex, vertexColors:true, blending:THREE.AdditiveBlending, depthWrite:false, transparent:true})));
        scene.add(heartGroup);

        // Floating Quotes
        const quotes = ["You are my today and all of my tomorrows.","My heart is and always will be yours.","I love you more than stars.","Happy birthday, my soulmate."];
        quotes.forEach((q, i) => {
            const div = document.createElement('div');
            div.textContent = `❤️ ${q} ❤️`;
            div.style.color = '#ffe4f2'; div.style.fontSize = '1.2rem'; div.style.textShadow = '0 0 20px deeppink';
            div.style.background = 'rgba(30,5,20,0.5)'; div.style.padding = '5px 15px'; div.style.borderRadius = '30px';
            div.style.backdropFilter = 'blur(5px)'; div.style.border = '1px solid pink';
            const label = new CSS2DObject(div);
            const ang = (i/quotes.length)*Math.PI*2;
            label.position.set(Math.cos(ang)*6, 2.5 + Math.sin(i)*1.5, Math.sin(ang)*6);
            scene.add(label);
        });

        // Gifts
        const gifts = [];
        const giftMsgs = ["💝 Forever yours.","💐 You're my dream.","🌟 Shine bright, love.","🎀 Wrapped with love.","💎 Precious you.","🌸 Blooming love."];
        function makeGift(pos, col, idx) {
            const g = new THREE.Group();
            const box = new THREE.Mesh(new THREE.BoxGeometry(1.0,1.0,1.0), new THREE.MeshStandardMaterial({color:col, roughness:0.3, emissive:new THREE.Color(0x331122)}));
            box.castShadow=box.receiveShadow=true; g.add(box);
            const rib = new THREE.Mesh(new THREE.BoxGeometry(1.1,0.15,0.15), new THREE.MeshStandardMaterial({color:0xffe4f5}));
            rib.castShadow=true; g.add(rib);
            const rib2 = rib.clone(); rib2.scale.set(0.15,1.1,0.15); g.add(rib2);
            const bow1 = new THREE.Mesh(new THREE.SphereGeometry(0.2), new THREE.MeshStandardMaterial({color:0xffb3c6}));
            bow1.position.set(0.35,0.5,0); g.add(bow1);
            const bow2 = bow1.clone(); bow2.position.set(-0.35,0.5,0); g.add(bow2);
            g.position.set(pos[0], pos[1], pos[2]);
            g.userData = { msg: giftMsgs[idx%giftMsgs.length] };
            scene.add(g);
            return g;
        }
        [[-3.2,0.8,2.5],[3.5,0.9,2.0],[-2.5,0.8,-3.0],[4.0,1.0,-1.8],[0.5,1.0,-4.0],[-4.0,0.7,0.5],[3.0,0.9,-3.5]].forEach((p,i)=>gifts.push(makeGift(p, i%2?0xffaacc:0xddaaff, i)));

        // Hidden Treasure
        const treasureHeart = new THREE.Mesh(new THREE.SphereGeometry(0.4), new THREE.MeshStandardMaterial({color:0xffd700, emissive:0x553300}));
        treasureHeart.position.set(1.2, 1.8, -2.8);
        treasureHeart.userData = { secret: "You are the treasure of my life. 💛" };
        scene.add(treasureHeart);

        // Ground
        const ground = new THREE.Mesh(new THREE.CircleGeometry(18,32), new THREE.MeshStandardMaterial({color:0x1a0a2e, transparent:true, opacity:0.25, side:THREE.DoubleSide}));
        ground.rotation.x = -Math.PI/2; ground.position.y = -1.2; ground.receiveShadow = true; scene.add(ground);
        
        for(let i=0;i<30;i++) {
            const petal = new THREE.Mesh(new THREE.ConeGeometry(0.15,0.4), new THREE.MeshStandardMaterial({color:0xffaacc}));
            petal.position.set((Math.random()-0.5)*14, -1.0, (Math.random()-0.5)*14);
            petal.receiveShadow=true; scene.add(petal);
        }

        // Fireworks
        let fireworks = [];
        function launchFirework() {
            const count = 12;
            for(let i=0;i<count;i++) {
                const color = new THREE.Color().setHSL(Math.random(), 0.8, 0.6);
                const particles = [];
                for(let j=0;j<30;j++) {
                    const p = new THREE.Mesh(new THREE.SphereGeometry(0.08), new THREE.MeshStandardMaterial({color:color, emissive:color}));
                    p.position.set((Math.random()-0.5)*2, 3+Math.random()*3, (Math.random()-0.5)*2);
                    p.userData = { vel: new THREE.Vector3((Math.random()-0.5)*0.08, Math.random()*0.05, (Math.random()-0.5)*0.08), life: 1.0 };
                    scene.add(p); particles.push(p);
                }
                fireworks.push(particles);
            }
        }
        document.getElementById('fireworksBtn').addEventListener('click', ()=>{
            for(let i=0;i<3;i++) setTimeout(()=>launchFirework(), i*200);
        });

        // Music simulation
        let audioCtx; 
        document.getElementById('playMusicBtn').addEventListener('click', ()=>{
            if(!audioCtx) {
                audioCtx = new (window.AudioContext || window.webkitAudioContext)();
                const gain = audioCtx.createGain(); gain.gain.value = 0.15;
                const osc = audioCtx.createOscillator(); osc.type = 'sine';
                osc.frequency.value = 440;
                osc.connect(gain).connect(audioCtx.destination);
                osc.start();
                setTimeout(()=> osc.stop(), 2000);
            }
        });

        // Raycaster
        const raycaster = new THREE.Raycaster();
        const mouse = new THREE.Vector2();
        renderer.domElement.addEventListener('click', (e)=>{
            mouse.x = (e.clientX/renderer.domElement.clientWidth)*2-1;
            mouse.y = -(e.clientY/renderer.domElement.clientHeight)*2+1;
            raycaster.setFromCamera(mouse, camera);
            const intersects = raycaster.intersectObjects([...gifts, treasureHeart]);
            if(intersects.length) {
                const hit = intersects[0].object;
                if(hit === treasureHeart) {
                    document.getElementById('secret-message').textContent = hit.userData.secret;
                    document.getElementById('secretModal').classList.add('active');
                    treasureHeart.material.emissiveIntensity = 2;
                } else {
                    let parent = hit.parent;
                    while(parent && !parent.userData?.msg) parent = parent.parent;
                    if(parent?.userData?.msg) {
                        document.getElementById('gift-message-text').textContent = parent.userData.msg;
                        document.getElementById('giftMessageModal').classList.add('active');
                    }
                }
            }
        });

        // Game logic
        const gameCanvas = document.getElementById('game-canvas');
        const ctx = gameCanvas.getContext('2d');
        let gameActive=false, score=0, hearts=[];
        function spawnHeart(){ hearts.push({x:Math.random()*260+10, y:-20, sz:18+Math.random()*15, sp:1+Math.random()*2.5}); }
        function gameLoop(){
            if(!gameActive) return;
            ctx.clearRect(0,0,280,280);
            ctx.shadowColor='#ff69b4'; ctx.shadowBlur=15;
            hearts = hearts.filter(h=>{ h.y+=h.sp; if(h.y>300) return false;
                ctx.fillStyle='#ffb6c1'; ctx.beginPath(); ctx.moveTo(h.x, h.y-5);
                ctx.bezierCurveTo(h.x-15,h.y-15,h.x-20,h.y+10,h.x,h.y+20);
                ctx.bezierCurveTo(h.x+20,h.y+10,h.x+15,h.y-15,h.x,h.y-5); ctx.fill();
                return true;
            });
            if(hearts.length<10 && Math.random()<0.05) spawnHeart();
            requestAnimationFrame(gameLoop);
        }
        gameCanvas.addEventListener('click', (e)=>{
            if(!gameActive) return;
            const rect = gameCanvas.getBoundingClientRect();
            const mx = (e.clientX-rect.left)*(280/rect.width), my = (e.clientY-rect.top)*(280/rect.height);
            for(let i=hearts.length-1;i>=0;i--) {
                const h=hearts[i]; if(Math.hypot(mx-h.x, my-h.y)<h.sz) { hearts.splice(i,1); score++; document.getElementById('score-value').textContent=score; spawnHeart(); break; }
            }
        });
        document.getElementById('gameBtn').onclick=()=>{ document.getElementById('game-container').classList.add('active'); if(!gameActive){ gameActive=true; hearts=[]; score=0; for(let i=0;i<8;i++)spawnHeart(); gameLoop(); }};
        document.getElementById('close-game').onclick=()=>{ document.getElementById('game-container').classList.remove('active'); gameActive=false; };
        document.getElementById('reset-game').onclick=()=>{ hearts=[]; score=0; document.getElementById('score-value').textContent='0'; for(let i=0;i<8;i++)spawnHeart(); };
        
        document.getElementById('treasureBtn').onclick=()=> document.getElementById('treasure-container').classList.toggle('active');
        document.getElementById('close-treasure').onclick=()=> document.getElementById('treasure-container').classList.remove('active');
        
        // Modals
        document.querySelectorAll('[data-modal]').forEach(b=>b.addEventListener('click', ()=>document.getElementById(b.dataset.modal).classList.remove('active')));
        document.getElementById('letterBtn').onclick=()=>document.getElementById('letterModal').classList.add('active');
        document.getElementById('galleryBtn').onclick=()=>document.getElementById('galleryModal').classList.add('active');
        document.querySelectorAll('.modal-overlay').forEach(m=>m.addEventListener('click', (e)=>{if(e.target===m) m.classList.remove('active');}));

        // Animation loop
        let clock = new THREE.Clock();
        function animate(){
            const t = performance.now()*0.001;
            controls.update();
            heartGroup.rotation.y = Math.sin(t*0.1)*0.3;
            heartGroup.position.y = 1.5 + Math.sin(t*0.7)*0.15;
            gifts.forEach(g=>{g.rotation.y+=0.008; g.position.y=g.userData.origY+Math.sin(t*2)*0.08;});
            treasureHeart.rotation.y+=0.01;
            fireworks = fireworks.filter(set=>{
                set.forEach(p=>{ p.position.add(p.userData.vel); p.userData.vel.y-=0.002; p.userData.life-=0.01; p.material.opacity=p.userData.life; });
                return set[0].userData.life>0;
            });
            renderer.render(scene, camera);
            cssRenderer.render(scene, camera);
            requestAnimationFrame(animate);
        }
        gifts.forEach(g=>g.userData.origY=g.position.y);
        animate();

        window.addEventListener('resize', ()=>{
            camera.aspect = window.innerWidth/window.innerHeight; camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
            cssRenderer.setSize(window.innerWidth, window.innerHeight);
        });
    </script>
</body>
</html>
