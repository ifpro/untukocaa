<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Halo Oca, Ex!</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #fce4ec;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            text-align: center;
            color: #ff69b4;
            overflow: hidden;
            position: relative;
        }

        .container {
            background: #fff;
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
            max-width: 95%;
            width: 100%;
            position: relative;
            z-index: 1;
            overflow: hidden;
        }

        .intro, .main-content, .video-page {
            display: block;
        }

        .main-content, .video-page {
            display: none;
        }

        .slide {
            display: none;
        }

        .slide.active {
            display: block;
            animation: fadeIn 1s ease-in-out;
        }

        .title {
            font-size: 1.8em;
            margin-bottom: 15px;
            color: #ff4081;
            font-weight: bold;
            animation: fadeInDown 1.5s ease;
        }

        .message {
            font-size: 1em;
            margin-bottom: 15px;
            color: #333;
            line-height: 1.6;
            animation: fadeInUp 1.5s ease;
        }

        .heart {
            font-size: 2em;
            color: #ff4081;
            animation: pulse 1s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        .image {
            margin-top: 15px;
            animation: bounceIn 1s ease;
        }

        .image img {
            width: 120px;
            height: 120px;
            object-fit: cover;
            border-radius: 50%;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
        }

        .signature {
            font-size: 0.9em;
            margin-top: 15px;
            color: #555;
            animation: fadeInUp 1.5s ease;
        }

        .next-btn, .start-btn, .send-btn, .video-btn {
            background-color: #ff4081;
            color: #fff;
            border: none;
            padding: 10px 15px;
            font-size: 1em;
            border-radius: 5px;
            margin-top: 15px;
            cursor: pointer;
            transition: background-color 0.3s ease, transform 0.3s ease;
            animation: fadeInUp 1.5s ease;
        }

        .next-btn:hover, .start-btn:hover, .send-btn:hover, .video-btn:hover {
            background-color: #e91e63;
            transform: scale(1.05);
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes bounceIn {
            0%, 20%, 40%, 60%, 80%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        .flower {
            position: absolute;
            width: 40px;
            height: 40px;
            background: url('FOTO1.PNG') no-repeat center;
            background-size: contain;
            animation: fall 10s linear infinite;
            z-index: 0;
        }

        @keyframes fall {
            0% { transform: translateY(-100px); opacity: 1; }
            100% { transform: translateY(110vh); opacity: 0; }
        }

        .flower:nth-child(2) { left: 15%; animation-duration: 8s; }
        .flower:nth-child(3) { left: 30%; animation-duration: 6s; }
        .flower:nth-child(4) { left: 45%; animation-duration: 12s; }
        .flower:nth-child(5) { left: 60%; animation-duration: 9s; }
        .flower:nth-child(6) { left: 75%; animation-duration: 10s; }
        .flower:nth-child(7) { left: 85%; animation-duration: 7s; }
        .flower:nth-child(8) { left: 95%; animation-duration: 11s; }

        .video-page {
            display: none;
            text-align: center;
        }

        .video-container {
            position: relative;
            padding-top: 56.25%; /* 16:9 Aspect Ratio */
            height: 0;
            overflow: hidden;
            max-width: 100%;
            border-radius: 15px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
            background-color: #000;
        }

        .video-container video {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
        }

        /* Responsive Design */
        @media (max-width: 600px) {
            .title {
                font-size: 1.5em;
            }

            .message {
                font-size: 0.9em;
            }

            .next-btn, .start-btn, .send-btn, .video-btn {
                font-size: 0.9em;
                padding: 8px 14px;
            }

            .image img {
                width: 100px;
                height: 100px;
            }

            .flower {
                width: 30px;
                height: 30px;
            }
        }
    </style>
</head>
<body>
    <!-- Flower Animation -->
    <div class="flower"></div>
    <div class="flower"></div>
    <div class="flower"></div>
    <div class="flower"></div>
    <div class="flower"></div>
    <div class="flower"></div>
    <div class="flower"></div>
    <div class="flower"></div>

    <!-- Background Music -->
    <audio id="background-music" loop>
        <source src="audio1.mp3" type="audio/mp3">
        Your browser does not support the audio element.
    </audio>

    <div class="container intro">
        <div class="title">Halo Monicandra Puspitasari!</div>
        <div class="message">Kasih masukki namata yang saya panggil biar bisaki lanjut:</div>
        <input type="text" id="userName" placeholder="*Panggilanku Untuk Kita" style="padding: 10px; font-size: 1.2em; border-radius: 5px; border: 1px solid #ddd; width: calc(100% - 24px); box-sizing: border-box;">
        <button class="start-btn" onclick="startExperience()">lanjutki</button>
    </div>

    <div class="container main-content">
        <div class="slide active">
            <div class="title">Halo Oca <span id="displayName"></span>!</div>
            <div class="message">
                heheh Aneh toh ada yang dekatiki orang seperti saya wkwkw, tapi nda bercandaka untuk dekatiki ini, mungki nda terbiasaki dengan orang seperti saya hehe nda tauka mau buatkan ki cuma iniji saya bisa buatkan ki.
            </div>
            <div class="heart">❤️</div>
            <div class="image">
                <img src="foto2.jpeg" alt="Your Love's Picture 1">
            </div>
            <div class="signature">With all my hopes, Andi Irfan Maulana</div>
            <button class="next-btn" onclick="nextSlide(1)">Next</button>
        </div>

        <div class="slide">
            <div class="title">Harapan</div>
            <div class="message">
              nda banyak harapanku dari kita, dan nda bisaka banyak janji dengan kita harapanku cukup bisaka dengan kita sesuai dengan niatku, dan nda bisaka janji banyak kekita dan ke king tapi saya usahakan untuk kita dan king.
            </div>
            <div class="heart">💖</div>
            <div class="image">
                <img src="foto1.jpg" alt="Your Love's Picture 2">
            </div>
            <div class="signature">Forever yours, Monicandra Puspitasari</div>
            <button class="next-btn" onclick="nextSlide(2)">Next</button>
        </div>

        <div class="slide">
            <div class="title">Selalu Dihati</div>
            <div class="message">
                Meskipun kita mungkin anehki dan belum bisaki sama - sama dengan saya, tapi jujur dari awal saya dmki ditiktok punya ka perasaan dengan kita yang mana itu perasaan sudah lama mka nda rasaki tapi nda saya paksaki untuk bisaki sama tapi tujuanku dan harapanku bisaki sama -  sama walaupun mungin aneh karna bemum pernahki ketemu 
            </div>
            <div class="heart">💞</div>
            <div class="image">
                <img src="foto3.jpeg" alt="Your Love's Picture 3">
            </div>
          
        <button class="send-btn" onclick="sendGiftRequest()">Jawabanta heheh</button>
    </div>

    <script>
        function startExperience() {
            var userName = document.getElementById("userName").value;
            if (userName.trim() !== "") {
                document.getElementById("displayName").textContent = userName;
                document.querySelector(".intro").style.display = "none";
                document.querySelector(".main-content").style.display = "block";
                document.getElementById("background-music").play();
            } else {
                alert("Please enter your name to continue.");
            }
        }

        function nextSlide(index) {
            var slides = document.querySelectorAll(".slide");
            slides.forEach(function(slide, i) {
                slide.classList.remove("active");
                if (i === index) {
                    slide.classList.add("active");
                }
            });
        }

        function showVideo() {
            document.querySelector(".main-content").style.display = "none";
            document.querySelector(".video-page").style.display = "block";
            document.getElementById("background-music").pause();
        }

        function backToSlides() {
            document.querySelector(".video-page").style.display = "none";
            document.querySelector(".main-content").style.display = "block";
            document.getElementById("background-music").play();
        }

        function sendGiftRequest() {
            var userName = document.getElementById("userName").value;
            var url = "https://api.whatsapp.com/send?phone=+6285345674445&text=" + encodeURIComponent("Happy Birthday! dihari spesialta mauki kado apa? " + userName);
            window.open(url, "_blank");
        }
    </script>
</body>
</html>
`
