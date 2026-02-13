<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Valentine's Proposal for Sadika</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
            touch-action: manipulation;
        }
        
        body {
            background: linear-gradient(135deg, #ff9a9e, #fad0c4, #fad0c4, #ff9a9e);
            min-height: 100vh;
            overflow-x: hidden;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, sans-serif;
            padding: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .container {
            width: 100%;
            max-width: 95vw;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 25px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
            padding: 20px 15px;
            text-align: center;
            position: relative;
            z-index: 10;
            backdrop-filter: blur(10px);
            border: 4px solid #ff4d6d;
            margin: 5px;
        }
        
        .title {
            color: #ff4d6d;
            font-size: 1.6rem;
            margin-bottom: 10px;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.1);
        }
        
        .proposal-text {
            font-size: 1.8rem;
            font-weight: 900;
            color: #d81b60;
            margin: 10px 0 10px 0;
            padding: 12px 8px;
            line-height: 1.2;
            background: rgba(255, 182, 193, 0.2);
            border-radius: 20px;
            border: 3px dashed #ff4d6d;
            text-transform: uppercase;
        }
        
        /* Message box styles */
        .message-section {
            margin: 10px 0 15px 0;
            padding: 12px;
            background: rgba(255, 240, 245, 0.7);
            border-radius: 15px;
            border: 2px solid #ffb6c1;
        }
        
        .message-label {
            font-size: 1rem;
            color: #d81b60;
            font-weight: 600;
            margin-bottom: 5px;
            display: block;
        }
        
        .message-input-container {
            position: relative;
            width: 100%;
        }
        
        #message-input {
            width: 100%;
            padding: 12px;
            font-size: 1rem;
            border: 2px solid #ff4d6d;
            border-radius: 12px;
            text-align: center;
            background: white;
            font-weight: 500;
            color: #333;
            outline: none;
        }
        
        #message-input:focus {
            border-color: #ff1493;
            box-shadow: 0 0 8px rgba(255, 20, 147, 0.3);
        }
        
        .char-counter {
            position: absolute;
            right: 8px;
            bottom: -18px;
            font-size: 0.8rem;
            color: #666;
            font-weight: 600;
        }
        
        .char-counter.warning {
            color: #ff9800;
        }
        
        .char-counter.limit-reached {
            color: #d81b60;
            font-weight: 700;
        }
        
        .buttons-container {
            display: flex;
            justify-content: space-around;
            align-items: center;
            margin: 20px 0 15px 0;
            min-height: 90px;
            position: relative;
            flex-wrap: wrap;
        }
        
        .valentine-btn {
            padding: 14px 20px;
            font-size: 1.3rem;
            font-weight: 800;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.2s ease;
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
            min-width: 110px;
            z-index: 2;
            position: relative;
        }
        
        #yes-btn {
            background: linear-gradient(145deg, #4CAF50, #2E7D32);
            color: white;
        }
        
        #no-btn {
            background: linear-gradient(145deg, #f44336, #c62828);
            color: white;
            user-select: none;
            position: absolute;
            transition: left 0.3s, top 0.3s;
        }
        
        #yes-btn:active {
            transform: scale(0.95);
        }
        
        /* Response container - COMPACT VERSION with less empty space */
        .response-container {
            margin-top: 15px;
            padding: 15px 12px;
            display: none;
            background: rgba(255, 228, 230, 0.7);
            border-radius: 15px;
            border: 2px solid #ff4d6d;
        }
        
        .response-text {
            font-size: 1.3rem;
            font-weight: 900;
            color: #d81b60;
            margin-bottom: 10px;
            line-height: 1.2;
        }
        
        .date-input-container {
            margin-top: 5px;
            margin-bottom: 10px;
        }
        
        .date-label {
            font-size: 1.1rem;
            color: #ff4d6d;
            font-weight: 700;
            display: block;
            margin-bottom: 5px;
        }
        
        #date-input {
            padding: 12px 10px;
            font-size: 1rem;
            width: 100%;
            border: 2px solid #ff4d6d;
            border-radius: 12px;
            text-align: center;
            background: white;
            font-weight: 600;
            color: #d81b60;
        }
        
        /* NEW: Admin section - to view her responses (hidden from her) */
        .admin-section {
            margin-top: 15px;
            padding: 10px;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 12px;
            border: 2px dashed #ff4d6d;
        }
        
        .admin-btn {
            background: #ff4d6d;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 50px;
            font-weight: 700;
            font-size: 1rem;
            cursor: pointer;
            margin: 5px;
        }
        
        .admin-data {
            margin-top: 10px;
            padding: 10px;
            background: #fff0f3;
            border-radius: 10px;
            display: none;
            text-align: left;
        }
        
        .data-item {
            padding: 8px;
            border-bottom: 1px solid #ffb6c1;
            font-size: 1rem;
        }
        
        .data-item:last-child {
            border-bottom: none;
        }
        
        .data-label {
            font-weight: 700;
            color: #d81b60;
        }
        
        .data-value {
            color: #333;
            word-break: break-word;
        }
        
        .hearts-container {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
            z-index: 1;
            overflow: hidden;
        }
        
        .heart {
            position: absolute;
            font-size: 24px;
            color: #ff4d6d;
            opacity: 0.7;
            animation: float 8s infinite ease-in-out;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg) scale(1); }
            50% { transform: translateY(-30px) rotate(10deg) scale(1.1); }
        }
        
        .footer {
            margin-top: 10px;
            color: #666;
            font-size: 0.8rem;
            padding-top: 8px;
            border-top: 1px solid #ffccd5;
        }
        
        /* Mobile-specific adjustments */
        @media (max-width: 480px) {
            .proposal-text {
                font-size: 1.5rem;
                padding: 10px 5px;
            }
            
            .valentine-btn {
                padding: 12px 16px;
                font-size: 1.2rem;
                min-width: 100px;
            }
            
            .response-text {
                font-size: 1.2rem;
            }
            
            .admin-btn {
                padding: 8px 16px;
                font-size: 0.9rem;
            }
        }
        
        /* Animation for NO button */
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-5px); }
            75% { transform: translateX(5px); }
        }
        
        .shake {
            animation: shake 0.3s ease;
        }
        
        .no-select {
            -webkit-user-select: none;
            -moz-user-select: none;
            -ms-user-select: none;
            user-select: none;
        }
        
        /* Secret code input (for you to access admin panel) */
        .secret-code-container {
            margin-top: 10px;
            display: flex;
            gap: 5px;
            justify-content: center;
        }
        
        #secret-code {
            padding: 8px;
            border: 2px solid #ffb6c1;
            border-radius: 8px;
            width: 100px;
            text-align: center;
        }
        
        .unlock-btn {
            background: #ffb6c1;
            border: none;
            padding: 8px 12px;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="hearts-container" id="hearts-container"></div>
    
    <div class="container">
        <h1 class="title">For My Love Sadika</h1>
        
        <div class="proposal-text">
            Sadika, WILL YOU BE MY VALENTINE?
        </div>
        
        <!-- Message box section with 30 character limit -->
        <div class="message-section">
            <label class="message-label" for="message-input">Leave me a sweet message (max 30 letters):</label>
            <div class="message-input-container">
                <input type="text" id="message-input" placeholder="Type here..." maxlength="30">
                <div class="char-counter" id="char-counter">0/30</div>
            </div>
        </div>
        
        <div class="buttons-container" id="buttons-container">
            <button class="valentine-btn" id="yes-btn">YES 💕</button>
            <button class="valentine-btn no-select" id="no-btn">NO</button>
        </div>
        
        <!-- COMPACT response container - less empty space -->
        <div class="response-container" id="response-container">
            <div class="response-text" id="response-text">
                Seems like you do love me after all, date when?!
            </div>
            
            <div class="date-input-container">
                <label class="date-label" for="date-input">Pick our Valentine's date:</label>
                <input type="date" id="date-input">
            </div>
            
            <!-- Hidden data display that only appears after she submits -->
            <div class="admin-section" id="her-response-summary" style="display: none; margin-top: 10px;">
                <div class="data-item">
                    <span class="data-label">Her message:</span> 
                    <span class="data-value" id="display-message"></span>
                </div>
                <div class="data-item">
                    <span class="data-label">Selected date:</span> 
                    <span class="data-value" id="display-date"></span>
                </div>
            </div>
        </div>
        
        <!-- SECRET ADMIN SECTION - Only visible with passcode -->
        <div class="admin-section" id="admin-section" style="margin-top: 10px;">
            <div class="secret-code-container">
                <input type="password" id="secret-code" placeholder="Code" maxlength="4">
                <button class="unlock-btn" id="unlock-btn">🔓 View Her Answers</button>
            </div>
            
            <div class="admin-data" id="admin-data">
                <div class="data-item">
                    <span class="data-label">💌 Her message:</span> 
                    <span class="data-value" id="saved-message">Not yet</span>
                </div>
                <div class="data-item">
                    <span class="data-label">📅 Date chosen:</span> 
                    <span class="data-value" id="saved-date">Not yet</span>
                </div>
                <div class="data-item">
                    <span class="data-label">⏰ Time:</span> 
                    <span class="data-value" id="saved-time">-</span>
                </div>
                <button class="admin-btn" id="clear-data-btn" style="margin-top: 10px;">Clear Data</button>
            </div>
        </div>
        
        <div class="footer">
            Made with <i class="fas fa-heart" style="color: #ff4d6d;"></i> for Sadika
        </div>
    </div>

    <script>
        // ========== HEARTS BACKGROUND ==========
        const heartsContainer = document.getElementById('hearts-container');
        const heartEmojis = ['❤️', '💖', '💗', '💓', '💞', '💕', '💘', '💝'];
        
        function createHeart() {
            const heart = document.createElement('div');
            heart.className = 'heart';
            heart.textContent = heartEmojis[Math.floor(Math.random() * heartEmojis.length)];
            
            const left = Math.random() * 100;
            const size = Math.random() * 20 + 15;
            const delay = Math.random() * 5;
            const duration = Math.random() * 8 + 5;
            
            heart.style.left = `${left}%`;
            heart.style.fontSize = `${size}px`;
            heart.style.animationDelay = `${delay}s`;
            heart.style.animationDuration = `${duration}s`;
            heart.style.top = '100vh';
            
            heartsContainer.appendChild(heart);
            
            setTimeout(() => {
                if (heart.parentNode) heart.parentNode.removeChild(heart);
            }, (delay + duration) * 1000);
        }
        
        for (let i = 0; i < 10; i++) setTimeout(createHeart, i * 200);
        setInterval(createHeart, 600);
        
        // ========== DOM ELEMENTS ==========
        const yesBtn = document.getElementById('yes-btn');
        const noBtn = document.getElementById('no-btn');
        const responseContainer = document.getElementById('response-container');
        const dateInput = document.getElementById('date-input');
        const buttonsContainer = document.getElementById('buttons-container');
        const messageInput = document.getElementById('message-input');
        const charCounter = document.getElementById('char-counter');
        
        // Admin elements
        const secretCode = document.getElementById('secret-code');
        const unlockBtn = document.getElementById('unlock-btn');
        const adminData = document.getElementById('admin-data');
        const savedMessage = document.getElementById('saved-message');
        const savedDate = document.getElementById('saved-date');
        const savedTime = document.getElementById('saved-time');
        const clearDataBtn = document.getElementById('clear-data-btn');
        const herResponseSummary = document.getElementById('her-response-summary');
        const displayMessage = document.getElementById('display-message');
        const displayDate = document.getElementById('display-date');
        
        // ========== MESSAGE BOX (30 char limit) ==========
        messageInput.addEventListener('input', function() {
            const len = this.value.length;
            charCounter.textContent = `${len}/30`;
            
            charCounter.classList.remove('warning', 'limit-reached');
            if (len === 30) charCounter.classList.add('limit-reached');
            else if (len >= 25) charCounter.classList.add('warning');
            
            // Auto-save to localStorage
            localStorage.setItem('valentineMessage', this.value);
        });
        
        // Load saved message
        const savedMsg = localStorage.getItem('valentineMessage') || '';
        messageInput.value = savedMsg;
        charCounter.textContent = `${savedMsg.length}/30`;
        if (savedMsg.length >= 25) charCounter.classList.add('warning');
        if (savedMsg.length === 30) charCounter.classList.add('limit-reached');
        
        // ========== DATE INPUT SETUP ==========
        const tomorrow = new Date();
        tomorrow.setDate(tomorrow.getDate() + 1);
        const formatDate = (date) => date.toISOString().split('T')[0];
        dateInput.min = formatDate(tomorrow);
        dateInput.value = formatDate(tomorrow);
        
        // ========== YES BUTTON ==========
        yesBtn.addEventListener('click', function() {
            // Show response container
            responseContainer.style.display = 'block';
            yesBtn.style.display = 'none';
            noBtn.style.display = 'none';
            
            // Get her message
            const herMessage = messageInput.value.trim() || "I love you!";
            
            // SAVE HER RESPONSE TO LOCALSTORAGE (so you can see it)
            const now = new Date();
            const responseData = {
                message: herMessage,
                date: dateInput.value,
                formattedDate: new Date(dateInput.value).toLocaleDateString('en-US', { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' }),
                timestamp: now.toLocaleString(),
                saidYes: true
            };
            
            localStorage.setItem('herValentineResponse', JSON.stringify(responseData));
            
            // Show summary in the response container
            herResponseSummary.style.display = 'block';
            displayMessage.textContent = herMessage;
            displayDate.textContent = responseData.formattedDate;
            
            // Celebration hearts
            for (let i = 0; i < 15; i++) {
                setTimeout(() => {
                    const heart = document.createElement('div');
                    heart.className = 'heart';
                    heart.textContent = '❤️';
                    heart.style.left = Math.random() * 100 + '%';
                    heart.style.fontSize = (Math.random() * 25 + 20) + 'px';
                    heart.style.color = '#4CAF50';
                    heart.style.animationDuration = '3s';
                    heart.style.top = '80vh';
                    heartsContainer.appendChild(heart);
                    setTimeout(() => heart.remove(), 3000);
                }, i * 100);
            }
        });
        
        // ========== NO BUTTON - MOVES AWAY ==========
        let isMoving = false;
        
        function moveNoButton() {
            if (isMoving) return;
            isMoving = true;
            
            noBtn.classList.add('shake');
            
            const containerRect = buttonsContainer.getBoundingClientRect();
            const maxX = containerRect.width - noBtn.offsetWidth;
            const maxY = containerRect.height - noBtn.offsetHeight;
            
            if (maxX > 0 && maxY > 0) {
                noBtn.style.left = Math.floor(Math.random() * maxX) + 'px';
                noBtn.style.top = Math.floor(Math.random() * maxY) + 'px';
            }
            
            const texts = ["Nope!", "Try again!", "Think twice!", "Really?", "Not today!", "Ask me nicely!", "Click YES!"];
            noBtn.textContent = texts[Math.floor(Math.random() * texts.length)];
            
            setTimeout(() => {
                noBtn.classList.remove('shake');
                isMoving = false;
            }, 300);
        }
        
        noBtn.addEventListener('mouseover', moveNoButton);
        noBtn.addEventListener('touchstart', (e) => { e.preventDefault(); moveNoButton(); });
        noBtn.addEventListener('click', (e) => { e.preventDefault(); moveNoButton(); });
        
        // ========== DATE SELECTION ==========
        dateInput.addEventListener('change', function() {
            const selectedDate = new Date(this.value);
            const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
            const formatted = selectedDate.toLocaleDateString('en-US', options);
            
            // Update saved data
            const existing = JSON.parse(localStorage.getItem('herValentineResponse') || '{}');
            existing.date = this.value;
            existing.formattedDate = formatted;
            existing.dateConfirmed = true;
            localStorage.setItem('herValentineResponse', JSON.stringify(existing));
            
            // Update display
            if (displayDate) displayDate.textContent = formatted;
            
            // Celebration
            alert(`Perfect! See you on ${formatted}! 💕`);
        });
        
        // ========== SECRET ADMIN PANEL (for you to see her answers) ==========
        const SECRET_CODE = "1414"; // Change this to your preferred code
        
        unlockBtn.addEventListener('click', function() {
            if (secretCode.value === SECRET_CODE) {
                // Load saved response
                const savedResponse = localStorage.getItem('herValentineResponse');
                if (savedResponse) {
                    const data = JSON.parse(savedResponse);
                    savedMessage.textContent = data.message || 'Not yet';
                    savedDate.textContent = data.formattedDate || data.date || 'Not yet';
                    savedTime.textContent = data.timestamp || '-';
                } else {
                    savedMessage.textContent = 'She hasn\'t responded yet';
                    savedDate.textContent = '-';
                    savedTime.textContent = '-';
                }
                
                adminData.style.display = 'block';
                secretCode.value = '';
            } else {
                alert('Wrong code! Try again.');
            }
        });
        
        clearDataBtn.addEventListener('click', function() {
            localStorage.removeItem('herValentineResponse');
            localStorage.removeItem('valentineMessage');
            adminData.style.display = 'none';
            alert('Data cleared!');
        });
        
        // Initialize NO button position
        window.addEventListener('load', () => setTimeout(moveNoButton, 200));
    </script>
</body>
</html>
