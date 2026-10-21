# VuiveNPQ
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
