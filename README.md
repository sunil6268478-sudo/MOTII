<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Someone Special</title>
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --primary-rose: #ff0054;
            --dark-rose: #800020;
            --gold: #ffd700;
        }

        body {
            background: radial-gradient(circle at center, #1a0505 0%, #000000 100%);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
            font-family: 'Poppins', sans-serif;
        }

        /* Hidden YouTube Player */
        #youtube-player {
            position: absolute;
            width: 0;
            height: 0;
            border: 0;
            pointer-events: none;
        }

        /* The Rose */
        .rose-wrapper {
            position: relative;
            cursor: pointer;
            transition: transform 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            z-index: 10;
        }

        .flower { position: relative; width: 120px; height: 120px; }

        .petal {
            position: absolute;
            background: linear-gradient(145deg, var(--primary-rose), var(--dark-rose));
            border-radius: 50% 50% 10% 50%;
            box-shadow: 0 0 25px rgba(255, 0, 84, 0.5);
            animation: bloom 2.5s ease-in-out forwards;
        }

        .p1 { width: 60px; height: 60px; left: 30px; top: 30px; z-index: 5; }
        .p2 { width: 80px; height: 80px; left: 20px; top: 10px; transform: rotate(45deg); }
        .p3 { width: 80px; height: 80px; left: 20px; top: 10px; transform: rotate(-45deg); }

        .sparkle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: white;
            border-radius: 50%;
            box-shadow: 0 0 10px var(--gold);
            animation: twinkle 2s infinite;
        }

        /* Handwritten Message Card */
        #card {
            display: none;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 300px;
            padding: 40px 20px;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(25px);
            -webkit-backdrop-filter: blur(25px);
            border: 1px solid rgba(255, 255, 255, 0.15);
            border-radius: 30px;
            text-align: center;
            color: white;
            box-shadow: 0 20px 50px rgba(0,0,0,0.9);
            z-index: 100;
            animation: slideUp 1.2s cubic-bezier(0.23, 1, 0.32, 1);
        }

        #card h2 {
            font-family: 'Great Vibes', cursive;
            font-size: 3rem;
            color: var(--primary-rose);
            margin: 0 0 10px 0;
            text-shadow: 0 0 10px rgba(255, 0, 84, 0.3);
        }

        #card p {
            font-family: 'Poppins', sans-serif;
            font-weight: 300;
            letter-spacing: 1px;
            line-height: 1.6;
            margin-bottom: 20px;
        }

        @keyframes bloom {
            0% { transform: scale(0) rotate(-10deg); filter: brightness(0); }
            100% { transform: scale(1) rotate(0deg); filter: brightness(1); }
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0; transform: translateY(0) scale(1); }
            50% { opacity: 1; transform: translateY(-40px) scale(1.5); }
        }

        @keyframes slideUp {
            from { opacity: 0; transform: translate(-50%, -10%); scale: 0.9; }
            to { opacity: 1; transform: translate(-50%, -50%); scale: 1; }
        }
    </style>
</head>
<body>

    <iframe id="youtube-player" 
            src="https://www.youtube.com/embed/FMKv26gKu8c&list=RDFMKv26gKu8c&start_radio=1" 
            allow="autoplay">
    </iframe>

    <div class="rose-wrapper" onclick="startExperience()">
        <div class="flower">
            <div class="petal p1"></div>
            <div class="petal p2"></div>
            <div class="petal p3"></div>
        </div>
    </div>

    <div id="card">
        <h2>Happy Rose Day meriiiiiiiiiii motiiiiiiiiiiii pandaaaaaaa</h2>
        <p>A beautiful soul deserves a beautiful rose. Thank you for making my world bloom.</p>
        <span style="color: var(--gold); font-size: 1.5rem;">❤</span>
    </div>

    <script>
        const wrapper = document.querySelector('.rose-wrapper');

        // Create 30 random sparkles
        for(let i=0; i<30; i++) {
            let s = document.createElement('div');
            s.className = 'sparkle';
            s.style.left = Math.random() * 150 + 'px';
            s.style.top = Math.random() * 150 + 'px';
            s.style.animationDelay = Math.random() * 3 + 's';
            wrapper.appendChild(s);
        }

        function startExperience() {
            // Reveal Card
            document.getElementById('card').style.display = 'block';
            
            // Start YouTube Clip
            const iframe = document.getElementById('youtube-player');
            iframe.src += "&autoplay=1";

            // Hide the rose head to focus on the message
            wrapper.style.opacity = "0.3";
            wrapper.style.filter = "blur(5px)";
        }
    </script>
</body>
</html>
