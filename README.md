# VuiveNPQ
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trang Web Niềm Vui</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #fdfbfb 0%, #ebedee 100%);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            text-align: center;
            color: #333;
        }
        h1 {
            color: #ff6b6b;
            margin-bottom: 20px;
        }
        .container {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
            max-width: 500px;
            width: 90%;
        }
        button {
            background-color: #4ecdc4;
            color: white;
            border: none;
            padding: 12px 24px;
            font-size: 16px;
            border-radius: 50px;
            cursor: pointer;
            transition: transform 0.2s, background-color 0.2s;
            margin: 10px;
            font-weight: bold;
        }
        button:hover {
            background-color: #36b9b0;
            transform: scale(1.05);
        }
        button:active {
            transform: scale(0.95);
        }
        #story-box {
            margin-top: 20px;
            min-height: 60px;
            font-size: 18px;
            font-style: italic;
            color: #555;
            line-height: 1.5;
        }
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: #f00;
            animation: fall linear forwards;
        }
        @keyframes fall {
            to { transform: translateY(100vh) rotate(720deg); }
        }
    </style>
</head>
<body>

    <h1>🎉 Góc Vui Vẻ Của Bạn 🎉</h1>

    <div class="container">
        <p>Nhấn nút để nhận niềm vui ngẫu nhiên!</p>
        <button onclick="generateStory()">📖 Kể chuyện vui</button>
        <button onclick="clap()">👏 Vỗ tay ảo</button>
        
        <div id="story-box">Chờ một câu chuyện vui vẻ...</div>
    </div>

    <script>
        const stories = [
            "Một ngày nọ, một chú mèo đi học về và nói: 'Hôm nay thầy giáo dạy về sự im lặng, nhưng bạn của tôi lại học về tiếng kêu gào!'",
            "Tại sao cá không biết bơi? Vì chúng đã có chân tay rồi, chúng chỉ cần đứng yên và để nước chảy qua!",
            "Một người đi xin việc: 'Anh có thể làm việc cả ngày lẫn đêm không?' - Nhà tuyển dụng: 'Được, nhưng anh có thể ngủ lúc 3 giờ sáng không?'",
            "Con kiến hỏi mẹ: 'Mẹ ơi, chúng ta có nên lo lắng về tương lai không?' Mẹ kiến đáp: 'Không, vì tương lai sẽ tự đến, còn bây giờ ta cứ đi tìm hạt gạo.'",
            "Một chú chó đi gặp bác sĩ thú y: 'Bác sĩ ơi, tôi bị đau lưng.' Bác sĩ: 'Cầm thuốc này về uống đi.' Chú chó: 'Thế còn lưng của tôi thì sao?'",
            "Tại sao mặt trời không bao giờ buồn? Vì nó luôn có 'nhiều' ánh sáng và 'nhiều' năng lượng!"
        ];

        function generateStory() {
            const box = document.getElementById('story-box');
            const randomStory = stories[Math.floor(Math.random() * stories.length)];
            box.textContent = randomStory;
            createConfetti(10);
        }

        function clap() {
            const box = document.getElementById('story-box');
            box.textContent = "👏 👏 👏 Vỗ tay thật to! Bạn làm tốt lắm! 👏 👏 👏";
            createConfetti(30);
            
            // Hiệu ứng rung nhẹ
            const container = document.querySelector('.container');
            container.style.transform = "translateX(5px)";
            setTimeout(() => container.style.transform = "translateX(-5px)", 50);
            setTimeout(() => container.style.transform = "translateX(5px)", 100);
            setTimeout(() => container.style.transform = "translateX(0)", 150);
        }

        function createConfetti(amount) {
            const colors = ['#ff6b6b', '#4ecdc4', '#ffe66d', '#ff9ff3', '#54a0ff'];
            for (let i = 0; i < amount; i++) {
                const confetti = document.createElement('div');
                confetti.classList.add('confetti');
                confetti.style.left = Math.random() * 100 + 'vw';
                confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                confetti.style.animationDuration = (Math.random() * 2 + 2) + 's';
                document.body.appendChild(confetti);

                setTimeout(() => {
                    confetti.remove();
                }, 4000);
            }
        }
    </script>
</body>
</html>
