# Valentine-for-Sadika
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
            padding: 15px;
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
            padding: 25px 20px;
            text-align: center;
            position: relative;
            z-index: 10;
            backdrop-filter: blur(10px);
            border: 4px solid #ff4d6d;
            margin: 10px;
        }
        
        .title {
            color: #ff4d6d;
            font-size: 1.8rem;
            margin-bottom: 15px;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.1);
        }
        
        .proposal-text {
            font-size: 2rem;
            font-weight: 900;
            color: #d81b60;
            margin: 20px 0;
            padding: 15px 10px;
            line-height: 1.3;
            background: rgba(255, 182, 193, 0.2);
            border-radius: 20px;
            border: 3px dashed #ff4d6d;
            text-transform: uppercase;
        }
        
        .buttons-container {
            display: flex;
            justify-content: space-around;
            align-items: center;
            margin: 30px 0;
            min-height: 120px;
            position: relative;
            flex-wrap: wrap;
        }
        
        .valentine-btn {
            padding: 18px 25px;
            font-size: 1.5rem;
            font-weight: 800;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.2s ease;
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
            min-width: 130px;
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
            background: linear-gradient(145deg, #388E3C, #1B5E20);
        }
        
        .response-container {
            margin-top: 25px;
            padding: 20px 15px;
            display: none;
            background: rgba(255, 228, 230, 0.7);
            border-radius: 20px;
            border: 2px solid #ff4d6d;
        }
        
        .response-text {
            font-size: 1.7rem;
            font-weight: 900;
            color: #d81b60;
            margin-bottom: 20px;
            line-height: 1.3;
        }
        
        .date-input-container {
            margin-top: 15px;
        }
        
        #date-input {
            padding: 18px 15px;
            font-size: 1.2rem;
            width: 100%;
            border: 3px solid #ff4d6d;
            border-radius: 15px;
            text-align: center;
            background: white;
            font-weight: 600;
            color: #d81b60;
        }
        
        .date-label {
            font-size: 1.3rem;
            color: #ff4d6d;
            font-weight: 700;
            display: block;
            margin-bottom: 10px;
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
            font-size: 28px;
            color: #ff4d6d;
            opacity: 0.8;
            animation: float 8s infinite ease-in-out;
        }
        
        @keyframes float {
            0%, 100% {
                transform: translateY(0) rotate(0deg) scale(1);
            }
            25% {
                transform: translateY(-20px) rotate(10deg) scale(1.1);
            }
            50% {
                transform: translateY(-40px) rotate(0deg) scale(1);
            }
            75% {
                transform: translateY(-20px) rotate(-10deg) scale(0.9);
            }
        }
        
        .footer {
            margin-top: 20px;
            color: #666;
            font-size: 0.9rem;
            padding-top: 15px;
            border-top: 1px solid #ffccd5;
        }
        
        /* Mobile-specific adjustments */
        @media (max-width: 480px) {
            .proposal-text {
                font-size: 1.7rem;
                padding: 12px 8px;
            }
            
            .valentine-btn {
                padding: 16px 22px;
                font-size: 1.4rem;
                min-width: 120px;
            }
            
            .response-text {
                font-size: 1.5rem;
            }
            
            .date-label {
                font-size: 1.2rem;
            }
            
            .container {
                padding: 20px 15px;
            }
        }
        
        @media (max-width: 380px) {
            .proposal-text {
                font-size: 1.5rem;
            }
            
            .valentine-btn {
                padding: 14px 20px;
                font-size: 1.3rem;
                min-width: 110px;
            }
            
            .buttons-container {
                flex-direction: column;
                gap: 15px;
            }
            
            #no-btn {
                position: relative;
            }
        }
        
        /* Animation for when NO button moves */
        @keyframes shake {
            0% { transform: translateX(0); }
            25% { transform: translateX(-5px); }
            50% { transform: translateX(5px); }
            75% { transform: translateX(-5px); }
            100% { transform: translateX(0); }
        }
        
        .shake {
            animation: shake 0.5s ease;
        }
        
        /* Success message styling */
        .success-message {
            display: none;
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: rgba(255, 255, 255, 0.95);
            padding: 25px;
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
            z-index: 100;
            text-align: center;
            border: 4px solid #4CAF50;
            max-width: 85%;
        }
        
        .success-text {
            font-size: 1.5rem;
            font-weight: 800;
            color: #2E7D32;
            margin-bottom: 15px;
        }
        
        .close-btn {
            padding: 10px 25px;
            background: #4CAF50;
            color: white;
            border: none;
            border-radius: 50px;
            font-weight: 700;
            font-size: 1.1rem;
            cursor: pointer;
        }
        
        /* Prevent text selection on NO button */
        .no-select {
            -webkit-user-select: none;
            -moz-user-select: none;
            -ms-user-select: none;
            user-select: none;
        }
    </style>
</head>
<body>
    <div class="hearts-container" id="hearts-container">
        <!-- Hearts will be generated with JavaScript -->
    </div>
    
    <div class="container">
        <h1 class="title">For My Love Sadika</h1>
        
        <div class="proposal-text">
            Sadika, WILL YOU BE MY VALENTINE?
        </div>
        
        <div class="buttons-container" id="buttons-container">
            <button class="valentine-btn" id="yes-btn">YES</button>
            <button class="valentine-btn no-select" id="no-btn">NO</button>
        </div>
        
        <div class="response-container" id="response-container">
            <div class="response-text">
                Seems like you do love me after all, date when?!
            </div>
            
            <div class="date-input-container">
                <label class="date-label" for="date-input">Choose a date for our Valentine's date:</label>
                <input type="date" id="date-input">
            </div>
        </div>
        
        <div class="footer">
            Made with <i class="fas fa-heart" style="color: #ff4d6d;"></i> for Sadika
        </div>
    </div>
    
    <div class="success-message" id="success-message">
        <div class="success-text" id="success-text"></div>
        <button class="close-btn" id="close-btn">OK</button>
    </div>

    <script>
        // Generate floating hearts
        const heartsContainer = document.getElementById('hearts-container');
        const heartEmojis = ['❤️', '💖', '💗', '💓', '💞', '💕', '💘', '💝', '🧡', '💛', '💚', '💙', '💜'];
        
        function createHeart() {
            const heart = document.createElement('div');
            heart.className = 'heart';
            heart.textContent = heartEmojis[Math.floor(Math.random() * heartEmojis.length)];
            
            // Random position
            const left = Math.random() * 100;
            const size = Math.random() * 25 + 20;
            const delay = Math.random() * 5;
            const duration = Math.random() * 10 + 8;
            
            heart.style.left = `${left}%`;
            heart.style.fontSize = `${size}px`;
            heart.style.animationDelay = `${delay}s`;
            heart.style.animationDuration = `${duration}s`;
            heart.style.top = '100vh'; // Start from bottom
            
            heartsContainer.appendChild(heart);
            
            // Remove heart after animation completes
            setTimeout(() => {
                if (heart.parentNode) {
                    heart.parentNode.removeChild(heart);
                }
            }, (delay + duration) * 1000);
        }
        
        // Create initial hearts
        for (let i = 0; i < 15; i++) {
            setTimeout(createHeart, i * 300);
        }
        
        // Continue creating hearts
        setInterval(createHeart, 800);
        
        // Get DOM elements
        const yesBtn = document.getElementById('yes-btn');
        const noBtn = document.getElementById('no-btn');
        const responseContainer = document.getElementById('response-container');
        const dateInput = document.getElementById('date-input');
        const buttonsContainer = document.getElementById('buttons-container');
        const successMessage = document.getElementById('success-message');
        const successText = document.getElementById('success-text');
        const closeBtn = document.getElementById('close-btn');
        
        // Set date input to today's date and min to today
        const today = new Date();
        const tomorrow = new Date(today);
        tomorrow.setDate(tomorrow.getDate() + 1);
        
        const formatDate = (date) => {
            return date.toISOString().split('T')[0];
        };
        
        dateInput.min = formatDate(tomorrow);
        dateInput.value = formatDate(tomorrow);
        
        // Handle YES button click
        yesBtn.addEventListener('click', function() {
            responseContainer.style.display = 'block';
            yesBtn.style.display = 'none';
            noBtn.style.display = 'none';
            
            // Create celebration hearts
            for (let i = 0; i < 20; i++) {
                setTimeout(() => {
                    const heart = document.createElement('div');
                    heart.className = 'heart';
                    heart.textContent = '❤️';
                    
                    const left = Math.random() * 100;
                    const size = Math.random() * 30 + 25;
                    
                    heart.style.left = `${left}%`;
                    heart.style.fontSize = `${size}px`;
                    heart.style.color = '#4CAF50';
                    heart.style.animationDuration = '5s';
                    heart.style.top = '80vh';
                    
                    heartsContainer.appendChild(heart);
                    
                    setTimeout(() => {
                        if (heart.parentNode) {
                            heart.parentNode.removeChild(heart);
                        }
                    }, 5000);
                }, i * 150);
            }
            
            // Scroll to response container on mobile
            responseContainer.scrollIntoView({ behavior: 'smooth', block: 'center' });
        });
        
        // Handle NO button - make it move away on hover/touch
        let isMoving = false;
        
        noBtn.addEventListener('mouseover', moveNoButton);
        noBtn.addEventListener('touchstart', function(e) {
            e.preventDefault();
            if (!isMoving) {
                moveNoButton();
            }
        });
        
        // Also move when cursor gets close on mobile
        noBtn.addEventListener('mousemove', function(e) {
            const rect = noBtn.getBoundingClientRect();
            const centerX = rect.left + rect.width / 2;
            const centerY = rect.top + rect.height / 2;
            const distance = Math.sqrt(Math.pow(e.clientX - centerX, 2) + Math.pow(e.clientY - centerY, 2));
            
            // If cursor is within 80px of button center, move it
            if (distance < 80 && !isMoving) {
                moveNoButton();
            }
        });
        
        // Prevent clicking on NO button
        noBtn.addEventListener('click', function(e) {
            e.preventDefault();
            e.stopPropagation();
            if (!isMoving) {
                moveNoButton();
            }
        });
        
        function moveNoButton() {
            if (isMoving) return;
            
            isMoving = true;
            
            // Add shake animation
            noBtn.classList.add('shake');
            
            // Get container dimensions
            const containerRect = buttonsContainer.getBoundingClientRect();
            
            // Calculate new random position within container
            const maxX = containerRect.width - noBtn.offsetWidth;
            const maxY = containerRect.height - noBtn.offsetHeight;
            
            // Ensure we don't go out of bounds
            if (maxX <= 0 || maxY <= 0) {
                isMoving = false;
                return;
            }
            
            const randomX = Math.floor(Math.random() * maxX);
            const randomY = Math.floor(Math.random() * maxY);
            
            // Move the button to the new position
            noBtn.style.left = `${randomX}px`;
            noBtn.style.top = `${randomY}px`;
            
            // Change the text to make it fun
            const noTexts = ["Are you sure?", "Think again!", "Really?", "Try again!", 
                           "Don't do this!", "Please?", "I'll be sad!", "Give me a chance!",
                           "You don't mean that!", "Click YES!", "Not a chance!", "Maybe later?",
                           "Nope!", "I'm shy!", "Ask me again!"];
            noBtn.textContent = noTexts[Math.floor(Math.random() * noTexts.length)];
            
            // Remove shake class after animation
            setTimeout(() => {
                noBtn.classList.remove('shake');
                isMoving = false;
            }, 500);
        }
        
        // Handle date selection
        dateInput.addEventListener('change', function() {
            const selectedDate = new Date(this.value);
            const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
            const formattedDate = selectedDate.toLocaleDateString('en-US', options);
            
            // Show success message
            successText.textContent = `Perfect! I'm counting down the days until ${formattedDate}! Can't wait for our Valentine's date! ❤️`;
            successMessage.style.display = 'block';
            
            // Add more celebration hearts
            for (let i = 0; i < 10; i++) {
                setTimeout(() => {
                    const heart = document.createElement('div');
                    heart.className = 'heart';
                    heart.textContent = '💖';
                    
                    const left = Math.random() * 100;
                    const size = Math.random() * 35 + 30;
                    
                    heart.style.left = `${left}%`;
                    heart.style.fontSize = `${size}px`;
                    heart.style.color = '#FF1493';
                    heart.style.animationDuration = '6s';
                    heart.style.top = '90vh';
                    
                    heartsContainer.appendChild(heart);
                    
                    setTimeout(() => {
                        if (heart.parentNode) {
                            heart.parentNode.removeChild(heart);
                        }
                    }, 6000);
                }, i * 200);
            }
        });
        
        // Close success message
        closeBtn.addEventListener('click', function() {
            successMessage.style.display = 'none';
        });
        
        // Initialize the NO button position to be random on load
        window.addEventListener('load', function() {
            setTimeout(() => {
                const containerRect = buttonsContainer.getBoundingClientRect();
                const maxX = containerRect.width - noBtn.offsetWidth;
                const maxY = containerRect.height - noBtn.offsetHeight;
                
                if (maxX > 0 && maxY > 0) {
                    const randomX = Math.floor(Math.random() * maxX);
                    const randomY = Math.floor(Math.random() * maxY);
                    
                    noBtn.style.left = `${randomX}px`;
                    noBtn.style.top = `${randomY}px`;
                }
            }, 100);
        });
        
        // Prevent context menu on NO button
        noBtn.addEventListener('contextmenu', function(e) {
            e.preventDefault();
            return false;
        });
    </script>
</body>
</html>
