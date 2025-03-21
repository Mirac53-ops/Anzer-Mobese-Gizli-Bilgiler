
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kırmızı Uyarı</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: black;
            color: white;
            text-align: center;
        }
        #warning {
            font-size: 24px;
            color: red;
            font-weight: bold;
        }
        #imageContainer {
            display: none;
            position: relative;
        }
        img {
            max-width: 100%;
            height: auto;
            border: none;
        }
        #textOverlay {
            position: absolute;
            top: -140px; /* Yazıyı daha yukarı taşıdım */
            left: 50%;
            transform: translateX(-50%);
            color: white; /* Yazı rengi beyaz yapıldı */
            font-size: 32px;
            font-weight: bold;
            text-align: center;
            line-height: 1.5; /* İki satır arasında boşluk */
        }
    </style>
</head>
<body>
    <div id="warning">
        ⚠️ <br> Uyarı: <span id="countdown">5</span> saniye bekleyin!
    </div>
    <div id="imageContainer">
        <img src="https://i.hizliresim.com/LyoPgz.png" alt="Uyarı Sonrası Resim">
        <div id="textOverlay">
            Uhud Kartalı <br> Affetmez
        </div>
    </div>

    <script>
        let countdown = 5; // Geriye sayım başlangıç değeri
        const countdownElement = document.getElementById("countdown");
        const warningElement = document.getElementById("warning");
        const imageContainer = document.getElementById("imageContainer");

        // Geriye doğru sayımı başlat
        const countdownInterval = setInterval(() => {
            countdown--;
            countdownElement.innerText = countdown;

            // 0'a ulaştığında resmi ve metni göster
            if (countdown === 0) {
                clearInterval(countdownInterval);
                warningElement.style.display = "none"; // Uyarıyı gizle
                imageContainer.style.display = "flex"; // Resmi ve yazıyı göster

                // Arka plan rengini resim görünürken değiştir
                setInterval(() => {
                    document.body.style.backgroundColor = `#${Math.floor(Math.random() * 16777215).toString(16)}`;
                }, 1000);
            }
        }, 1000); // Her saniyede bir çalışır
    </script>
</body>
</html>
