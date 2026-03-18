<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VANZS STORE | Official Portfolio</title>
    
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;700;900&display=swap" rel="stylesheet">

    <style>
        :root {
            --bg-dark: #050505;
            --accent-red: #ff0000;
            --text-light: #ffffff;
            --card-bg: #111111;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-dark);
            color: var(--text-light);
            overflow-x: hidden;
        }

        /* --- NAVIGATION --- */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 8%;
            background: rgba(0,0,0,0.95);
            position: fixed;
            width: 100%;
            z-index: 1000;
            border-bottom: 2px solid var(--accent-red);
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 900;
            color: var(--accent-red);
            letter-spacing: 2px;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            margin-left: 25px;
            font-size: 0.9rem;
            font-weight: 500;
            transition: 0.3s;
        }

        .nav-links a:hover {
            color: var(--accent-red);
        }

        /* --- HERO SECTION --- */
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            background: radial-gradient(circle at center, #200000 0%, #050505 100%);
        }

        .hero h1 {
            font-size: clamp(3rem, 10vw, 6rem);
            font-weight: 900;
            line-height: 1;
            margin-bottom: 10px;
        }

        .hero span {
            color: var(--accent-red);
            text-shadow: 0 0 25px rgba(255, 0, 0, 0.8);
        }

        .hero p {
            font-size: 1.2rem;
            letter-spacing: 5px;
            color: #ccc;
            text-transform: uppercase;
            margin-bottom: 30px;
        }

        .btn-main {
            padding: 15px 45px;
            background: var(--accent-red);
            color: white;
            text-decoration: none;
            border-radius: 5px;
            font-weight: bold;
            transition: 0.4s;
            box-shadow: 0 5px 20px rgba(255, 0, 0, 0.4);
            border: 1px solid transparent;
        }

        .btn-main:hover {
            transform: translateY(-5px);
            background: transparent;
            border-color: var(--accent-red);
            box-shadow: 0 10px 30px rgba(255, 0, 0, 0.6);
        }

        /* --- GALLERY SECTION --- */
        .gallery {
            padding: 100px 8%;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 60px;
            font-weight: 800;
        }

        .section-title span { color: var(--accent-red); }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }

        .grid-item {
            position: relative;
            height: 400px;
            border-radius: 10px;
            overflow: hidden;
            background: var(--card-bg);
            border: 1px solid #222;
        }

        .grid-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: 0.7s ease;
            filter: brightness(0.7);
        }

        .grid-item:hover img {
            transform: scale(1.1);
            filter: brightness(1);
        }

        .overlay {
            position: absolute;
            inset: 0;
            background: linear-gradient(to top, rgba(255, 0, 0, 0.8), transparent);
            display: flex;
            flex-direction: column;
            justify-content: flex-end;
            padding: 25px;
            opacity: 0;
            transition: 0.4s;
        }

        .grid-item:hover .overlay {
            opacity: 1;
        }

        /* --- MUSIC TOGGLE --- */
        #music-control {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 65px;
            height: 65px;
            background: #000;
            border: 2px solid var(--accent-red);
            border-radius: 50%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            z-index: 9999;
            box-shadow: 0 0 15px rgba(255, 0, 0, 0.5);
            transition: 0.3s;
        }

        #music-status {
            font-size: 10px;
            font-weight: bold;
            margin-top: 2px;
        }

        .playing {
            animation: pulse-red 1.5s infinite;
        }

        @keyframes pulse-red {
            0% { box-shadow: 0 0 0 0 rgba(255, 0, 0, 0.7); }
            70% { box-shadow: 0 0 0 15px rgba(255, 0, 0, 0); }
            100% { box-shadow: 0 0 0 0 rgba(255, 0, 0, 0); }
        }

        footer {
            padding: 50px;
            text-align: center;
            border-top: 1px solid #222;
            color: #888;
            background: #000;
        }
    </style>
</head>
<body>

    <audio id="myAudio" loop>
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
    </audio>

    <div id="music-control" onclick="toggleMusic()">
        <span id="music-icon" style="font-size: 20px;">🎵</span>
        <span id="music-status" style="color: #ff0000;">OFF</span>
    </div>

    <nav>
        <div class="logo">VANZS STORE</div>
        <div class="nav-links">
            <a href="#home">HOME</a>
            <a href="#work">COLLECTION</a>
        </div>
    </nav>

    <section class="hero" id="home">
        <h1 data-aos="zoom-out" data-aos-duration="1200">WELCOME TO <span>VANZS STORE</span></h1>
        <p data-aos="fade-up" data-aos-delay="400">Premium Quality | Trusted | Fast Service</p>
        <div data-aos="fade-up" data-aos-delay="800">
            <a href="#work" class="btn-main">EXPLORE NOW</a>
        </div>
    </section>

    <section class="gallery" id="work">
        <h2 class="section-title" data-aos="fade-down">OUR <span>GALLERY</span></h2>
        
        <div class="grid">
            <div class="grid-item" data-aos="fade-up" data-aos-delay="100">
                <img src="https://images.unsplash.com/photo-1550684848-fac1c5b4e853?q=80&w=1000" alt="Work 1">
                <div class="overlay"><h3>Vanzs Design 1</h3><p>Exclusive Edition</p></div>
            </div>
            <div class="grid-item" data-aos="fade-up" data-aos-delay="200">
                <img src="https://images.unsplash.com/photo-1506157786151-b8491531f063?q=80&w=1000" alt="Work 2">
                <div class="overlay"><h3>Vanzs Design 2</h3><p>Streetwear Style</p></div>
            </div>
            <div class="grid-item" data-aos="fade-up" data-aos-delay="300">
                <img src="https://images.unsplash.com/photo-1515462277126-2dd0c162007a?q=80&w=1000" alt="Work 3">
                <div class="overlay"><h3>Neon Vibe</h3><p>Aesthetic Look</p></div>
            </div>
            <div class="grid-item" data-aos="fade-up" data-aos-delay="100">
                <img src="https://images.unsplash.com/photo-1544005313-94ddf0286df2?q=80&w=1000" alt="Work 4">
                <div class="overlay"><h3>Classic Black</h3><p>Minimalist</p></div>
            </div>
            <div class="grid-item" data-aos="fade-up" data-aos-delay="200">
                <img src="https://images.unsplash.com/photo-1614850523296-d8c1af93d400?q=80&w=1000" alt="Work 5">
                <div class="overlay"><h3>Red Passion</h3><p>Premium Feel</p></div>
            </div>
            <div class="grid-item" data-aos="fade-up" data-aos-delay="300">
                <img src="https://images.unsplash.com/photo-1534447677768-be436bb09401?q=80&w=1000" alt="Work 6">
                <div class="overlay"><h3>Dark Soul</h3><p>Cinematic</p></div>
            </div>
        </div>
    </section>

    <footer>
        <p>&copy; 2026 VANZS STORE. All Rights Reserved.</p>
    </footer>

    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        AOS.init({ duration: 1000, once: false });

        var audio = document.getElementById("myAudio");
        var control = document.getElementById("music-control");
        var statusText = document.getElementById("music-status");

        function toggleMusic() {
            if (audio.paused) {
                audio.play();
                control.classList.add("playing");
                statusText.innerText = "ON";
                statusText.style.color = "#00ff00";
            } else {
                audio.pause();
                control.classList.remove("playing");
                statusText.innerText = "OFF";
                statusText.style.color = "#ff0000";
            }
        }
    </script>
</body>
</html>
