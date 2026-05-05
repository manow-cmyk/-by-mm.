<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>วงล้อสุ่มอาหารชาวออฟฟิศ</title>
    <style>
        :root {
            --blue: #4285F4;
            --red: #EA4335;
            --yellow: #FBBC05;
            --green: #34A853;
            --white: #ffffff;
        }

        * {
            box-sizing: border-box;
            font-family: 'Kanit', sans-serif, system-ui;
        }

        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            margin: 0;
            background-color: #f8f9fa;
            overflow-x: hidden;
        }

        .container {
            position: relative;
            width: 90vw;
            max-width: 500px;
            aspect-ratio: 1/1;
            margin-bottom: 30px;
        }

        /* เข็มชี้ */
        .pointer {
            position: absolute;
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
            width: 0;
            height: 0;
            border-left: 15px solid transparent;
            border-right: 15px solid transparent;
            border-top: 30px solid #333;
            z-index: 10;
        }

        /* วงล้อ */
        #wheel {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            border: 8px solid #333;
            position: relative;
            overflow: hidden;
            transition: transform 4s cubic-bezier(0.15, 0, 0.15, 1);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }

        .segment {
            position: absolute;
            width: 50%;
            height: 50%;
            left: 50%;
            top: 50%;
            transform-origin: 0 0;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 14px;
            font-weight: bold;
            text-align: center;
            padding-left: 40px;
            word-wrap: break-word;
            white-space: pre-line; /* รองรับการขึ้นบรรทัดใหม่ */
        }

        /* ปุ่มกด */
        .spin-btn {
            padding: 15px 40px;
            font-size: 1.5rem;
            font-weight: bold;
            background-color: var(--blue);
            color: white;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 4px 0 #2a6dd4;
            transition: all 0.1s;
        }

        .spin-btn:active {
            transform: translateY(4px);
            box-shadow: none;
        }

        .result-display {
            margin-top: 20px;
            font-size: 1.8rem;
            font-weight: bold;
            color: #333;
            height: 40px;
            text-align: center;
        }

        /* ปรับแต่งตัวอักษรให้อ่านง่ายบนมือถือ */
        @media (max-width: 400px) {
            .segment {
                font-size: 11px;
                padding-left: 30px;
            }
        }
    </style>
</head>
<body>

    <h2 style="color: #333; margin-top: 20px;">วันนี้กินอะไรดี?</h2>
    
    <div class="container">
        <div class="pointer"></div>
        <canvas id="wheelCanvas"></canvas>
    </div>

    <button class="spin-btn" onclick="spinWheel()">หมุนวงล้อ!</button>
    <div class="result-display" id="resultText"></div>

    <script>
        const canvas = document.getElementById('wheelCanvas');
        const ctx = canvas.getContext('2d');
        const resultText = document.getElementById('resultText');
        
        const foods = [
            "กะเพรา\nไข่ดาว", "ก๋วยเตี๋ยว\nน้ำตก", "ข้าวมันไก่", "ข้าวขาหมู", 
            "ส้มตำ\nไก่ย่าง", "ราดหน้า", "ผัดซีอิ๊ว", "ข้าวผัด", 
            "ยำมาม่า", "สุกี้", "ข้าวราด\nแกง", "โจ๊ก", 
            "แซนวิช", "สลัดผัก", "ข้าวหมูแดง", "เล้งแซ่บ", 
            "น้ำพริก\nปลาทู", "ผัดไทย", "ต้มจืด", "ไก่ทอด", 
            "หมูกรอบ", "ข้าวเหนียว\nหมูปิ้ง", "ลาบหมู", "ขนมจีน"
        ];

        const colors = ['#4285F4', '#EA4335', '#FBBC05', '#34A853'];
        let currentRotation = 0;
        let isSpinning = false;

        function drawWheel() {
            const size = 500;
            canvas.width = size;
            canvas.height = size;
            const center = size / 2;
            const radius = size / 2 - 10;
            const sliceAngle = (2 * Math.PI) / foods.length;

            foods.forEach((food, i) => {
                const angle = i * sliceAngle;
                
                // วาดเสี้ยววงล้อ
                ctx.beginPath();
                ctx.fillStyle = colors[i % colors.length];
                ctx.moveTo(center, center);
                ctx.arc(center, center, radius, angle, angle + sliceAngle);
                ctx.lineTo(center, center);
                ctx.fill();
                ctx.stroke();
                ctx.strokeStyle = '#ffffff';
                ctx.lineWidth = 2;

                // วาดตัวอักษร
                ctx.save();
                ctx.translate(center, center);
                ctx.rotate(angle + sliceAngle / 2);
                ctx.textAlign = "right";
                ctx.fillStyle = "white";
                ctx.font = "bold 18px Kanit";
                
                // จัดการการแบ่งบรรทัด (ถ้ามี \n)
                const lines = food.split('\n');
                lines.forEach((line, index) => {
                    ctx.fillText(line, radius - 20, (index * 20) - (lines.length - 1) * 10 + 5);
                });
                
                ctx.restore();
            });
        }

        function spinWheel() {
            if (isSpinning) return;
            
            isSpinning = true;
            resultText.innerText = "กำลังสุ่ม...";
            
            const extraDegrees = Math.floor(Math.random() * 360) + 3600; // หมุนอย่างน้อย 10 รอบ
            currentRotation += extraDegrees;
            
            canvas.style.transition = "transform 4s cubic-bezier(0.15, 0, 0.15, 1)";
            canvas.style.transform = `rotate(${currentRotation}deg)`;

            setTimeout(() => {
                isSpinning = false;
                const actualRotation = currentRotation % 360;
                const sliceSize = 360 / foods.length;
                
                // คำนวณหา index ของอาหาร (ต้องคำนวณย้อนกลับจากการหมุน)
                // เนื่องจาก Canvas วาดเริ่มจากทิศตะวันออก (0 องศา) แต่เข็มอยู่ทิศเหนือ (-90 องศา)
                const winningIndex = Math.floor(((360 - actualRotation + 270) % 360) / sliceSize);
                const winner = foods[winningIndex].replace('\n', ' ');
                resultText.innerText = `เมนูที่ได้: ${winner}`;
            }, 4000);
        }

        // เริ่มต้นวาด
        drawWheel();

        // ปรับขนาด Canvas ให้ Responsive ตาม Container
        window.addEventListener('resize', () => {
            const containerWidth = document.querySelector('.container').offsetWidth;
            canvas.style.width = containerWidth + 'px';
            canvas.style.height = containerWidth + 'px';
        });
        
        // รันครั้งแรกเพื่อให้ขนาดพอดี
        window.dispatchEvent(new Event('resize'));
    </script>
</body>
</html>
