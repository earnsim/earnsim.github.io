
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>💰 EarnSim - Ultimate Fake Money Simulator</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Orbitron', monospace;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            color: white;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .header {
            text-align: center;
            margin-bottom: 30px;
            position: relative;
        }
        
        .header h1 {
            font-size: 3em;
            font-weight: 900;
            background: linear-gradient(45deg, #ffd700, #ffed4e);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 30px rgba(255, 215, 0, 0.5);
            animation: glow 2s ease-in-out infinite alternate;
        }
        
        @keyframes glow {
            from { text-shadow: 0 0 20px rgba(255, 215, 0, 0.5); }
            to { text-shadow: 0 0 40px rgba(255, 215, 0, 0.8); }
        }
        
        .disclaimer {
            background: rgba(255, 0, 0, 0.2);
            border: 2px solid #ff4444;
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 20px;
            text-align: center;
            font-weight: bold;
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }
        
        .balance-section {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            margin-bottom: 30px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
        }
        
        .balance {
            font-size: 2.5em;
            font-weight: 700;
            color: #00ff88;
            text-shadow: 0 0 20px rgba(0, 255, 136, 0.5);
        }
        
        .tabs {
            display: flex;
            justify-content: center;
            margin-bottom: 20px;
            flex-wrap: wrap;
            gap: 10px;
        }
        
        .tab {
            background: rgba(255, 255, 255, 0.1);
            border: none;
            border-radius: 10px;
            padding: 10px 20px;
            color: white;
            cursor: pointer;
            font-family: 'Orbitron', monospace;
            font-weight: bold;
            transition: all 0.3s ease;
        }
        
        .tab.active {
            background: linear-gradient(45deg, #00ff88, #00cc6a);
            box-shadow: 0 5px 20px rgba(0, 255, 136, 0.4);
        }
        
        .tab-content {
            display: none;
        }
        
        .tab-content.active {
            display: block;
        }
        
        .earning-section {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .earning-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }
        
        .earning-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.4);
        }
        
        .earn-btn {
            background: linear-gradient(45deg, #00ff88, #00cc6a);
            border: none;
            border-radius: 10px;
            padding: 15px 30px;
            font-size: 1.1em;
            font-weight: bold;
            color: white;
            cursor: pointer;
            transition: all 0.3s ease;
            text-transform: uppercase;
            font-family: 'Orbitron', monospace;
            width: 100%;
            margin-top: 10px;
        }
        
        .earn-btn:hover {
            background: linear-gradient(45deg, #00cc6a, #00ff88);
            transform: scale(1.05);
            box-shadow: 0 5px 20px rgba(0, 255, 136, 0.4);
        }
        
        .earn-btn:disabled {
            background: #666;
            cursor: not-allowed;
            transform: none;
        }
        
        .shop-section {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 30px;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .shop-title {
            text-align: center;
            font-size: 2em;
            margin-bottom: 20px;
            color: #ffd700;
        }
        
        .boosts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
        }
        
        .boost-item {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }
        
        .boost-item:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }
        
        .boost-price {
            color: #ff6b6b;
            font-weight: bold;
            font-size: 1.1em;
        }
        
        .buy-btn {
            background: linear-gradient(45deg, #ff6b6b, #ee5a52);
            border: none;
            border-radius: 8px;
            padding: 8px 16px;
            color: white;
            cursor: pointer;
            font-family: 'Orbitron', monospace;
            font-weight: bold;
            transition: all 0.3s ease;
            width: 100%;
            margin-top: 10px;
            font-size: 0.9em;
        }
        
        .buy-btn:hover {
            background: linear-gradient(45deg, #ee5a52, #ff6b6b);
            transform: scale(1.05);
        }
        
        .payout-section {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .payout-btn {
            background: linear-gradient(45deg, #ffd700, #ffed4e);
            border: none;
            border-radius: 10px;
            padding: 15px 30px;
            font-size: 1.2em;
            font-weight: bold;
            color: #333;
            cursor: pointer;
            font-family: 'Orbitron', monospace;
            transition: all 0.3s ease;
        }
        
        .payout-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 20px rgba(255, 215, 0, 0.4);
        }
        
        .payout-btn:disabled {
            background: #666;
            color: #999;
            cursor: not-allowed;
            transform: none;
        }
        
        .multiplier {
            display: inline-block;
            background: #ffd700;
            color: #333;
            padding: 5px 10px;
            border-radius: 15px;
            font-size: 0.8em;
            font-weight: bold;
            margin-left: 10px;
        }
        
        .notification {
            position: fixed;
            top: 20px;
            right: 20px;
            background: rgba(0, 255, 136, 0.9);
            color: white;
            padding: 15px 20px;
            border-radius: 10px;
            font-weight: bold;
            z-index: 1000;
            transform: translateX(400px);
            transition: transform 0.3s ease;
        }
        
        .notification.show {
            transform: translateX(0);
        }
        
        .rarity-common { border-left: 4px solid #888; }
        .rarity-rare { border-left: 4px solid #4a90e2; }
        .rarity-epic { border-left: 4px solid #9b59b6; }
        .rarity-legendary { border-left: 4px solid #f39c12; }
        .rarity-mythic { border-left: 4px solid #e74c3c; }
        .rarity-cosmic { border-left: 4px solid #ff00ff; animation: rainbow 3s linear infinite; }
        
        @keyframes rainbow {
            0% { border-left-color: #ff0000; }
            16% { border-left-color: #ff8000; }
            33% { border-left-color: #ffff00; }
            50% { border-left-color: #00ff00; }
            66% { border-left-color: #0080ff; }
            83% { border-left-color: #8000ff; }
            100% { border-left-color: #ff0000; }
        }
        
        .mini-game {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            padding: 20px;
            margin: 10px 0;
            text-align: center;
        }
        
        .progress-bar {
            width: 100%;
            height: 20px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            overflow: hidden;
            margin: 10px 0;
        }
        
        .progress-fill {
            height: 100%;
            background: linear-gradient(45deg, #00ff88, #00cc6a);
            width: 0%;
            transition: width 0.3s ease;
        }

        select {
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 8px;
            padding: 8px;
            color: white;
            font-family: 'Orbitron', monospace;
            margin: 10px 0;
            cursor: pointer;
        }

        select:focus {
            outline: none;
            border-color: #00ff88;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>💰 EarnSim Ultimate</h1>
            <p>The Most Advanced Fake Money Simulator</p>
        </div>
        
        <div class="disclaimer">
            ⚠️ THIS IS A SIMULATION GAME - NO REAL MONEY INVOLVED ⚠️
        </div>
        
        <div class="balance-section">
            <h2>Your Fake Balance</h2>
            <div class="balance">$<span id="balance">0.00</span></div>
            <div>Total Earned: $<span id="totalEarned">0.00</span> | Level: <span id="level">1</span></div>
            <div class="progress-bar">
                <div class="progress-fill" id="xpBar"></div>
            </div>
            <div>XP: <span id="xp">0</span> / <span id="xpNeeded">100</span></div>
            <button class="payout-btn" onclick="resetData()">RESET ALL DATA</button>
        </div>
        
        <div class="tabs">
            <button class="tab active" onclick="switchTab('basic')">Basic Earning</button>
            <button class="tab" onclick="switchTab('advanced')">Advanced Methods</button>
            <button class="tab" onclick="switchTab('minigames')">Mini Games</button>
            <button class="tab" onclick="switchTab('shop')">Boost Shop</button>
            <button class="tab" onclick="switchTab('payout')">Payouts</button>
        </div>
        
        <div id="basic" class="tab-content active">
            <div class="earning-section">
                <div class="earning-card">
                    <h3>⚡ Quick Earn</h3>
                    <p>Wait 5 seconds</p>
                    <p>Earn: $0.01 <span class="multiplier" id="multiplier1">x1</span></p>
                    <button class="earn-btn" id="earn1" onclick="startEarning(1, 5000, 0.01)">WAIT 5 SECONDS</button>
                    <div id="timer1"></div>
                </div>
                
                <div class="earning-card">
                    <h3>💎 Better Earn</h3>
                    <p>Wait 10 seconds</p>
                    <p>Earn: $0.03 <span class="multiplier" id="multiplier2">x1</span></p>
                    <button class="earn-btn" id="earn2" onclick="startEarning(2, 10000, 0.03)">WAIT 10 SECONDS</button>
                    <div id="timer2"></div>
                </div>
                
                <div class="earning-card">
                    <h3>🚀 Premium Earn</h3>
                    <p>Wait 15 seconds</p>
                    <p>Earn: $0.07 <span class="multiplier" id="multiplier3">x1</span></p>
                    <button class="earn-btn" id="earn3" onclick="startEarning(3, 15000, 0.07)">WAIT 15 SECONDS</button>
                    <div id="timer3"></div>
                </div>
                
                <div class="earning-card">
                    <h3>⭐ Mega Earn</h3>
                    <p>Wait 30 seconds</p>
                    <p>Earn: $0.20 <span class="multiplier" id="multiplier4">x1</span></p>
                    <button class="earn-btn" id="earn4" onclick="startEarning(4, 30000, 0.20)">WAIT 30 SECONDS</button>
                    <div id="timer4"></div>
                </div>
            </div>
        </div>
        
        <div id="advanced" class="tab-content">
            <div class="earning-section">
                <div class="earning-card">
                    <h3>📊 Fake Stock Market</h3>
                    <p>Invest and wait for returns</p>
                    <p>Investment: $1.00 | Return: $0-$2.00</p>
                    <select id="stockAmount">
                        <option value="1">Invest $1.00</option>
                        <option value="5">Invest $5.00</option>
                        <option value="10">Invest $10.00</option>
                    </select>
                    <button class="earn-btn" onclick="investStock()">INVEST IN STOCKS</button>
                    <div id="stockTimer"></div>
                </div>
                
                <div class="earning-card">
                    <h3>⛏️ Fake Mining</h3>
                    <p>Mine fake cryptocurrency</p>
                    <p>Cost: $0.50 | Earn: $0-$2.50</p>
                    <select id="miningAmount">
                        <option value="0.5">Mine $0.50</option>
                        <option value="2">Mine $2.00</option>
                        <option value="5">Mine $5.00</option>
                    </select>
                    <button class="earn-btn" onclick="startMining()">START MINING</button>
                    <div id="miningTimer"></div>
                </div>
                
                <div class="earning-card">
                    <h3>🎰 Lucky Spin</h3>
                    <p>Spin the wheel of fortune</p>
                    <p>Cost: $0.25 | Win: $0-$2.00</p>
                    <button class="earn-btn" onclick="spinWheel()">SPIN WHEEL</button>
                </div>
                
                <div class="earning-card">
                    <h3>📝 Fake Surveys</h3>
                    <p>Complete fake surveys</p>
                    <p>Time: 20s | Earn: $0.15</p>
                    <button class="earn-btn" id="surveyBtn" onclick="startSurvey()">DO SURVEY</button>
                    <div id="surveyTimer"></div>
                </div>
                
                <div class="earning-card">
                    <h3>📱 Watch Fake Ads</h3>
                    <p>Watch 10 second ads</p>
                    <p>Earn: $0.05 per ad</p>
                    <button class="earn-btn" id="adBtn" onclick="watchAd()">WATCH AD</button>
                    <div id="adTimer"></div>
                </div>
                
                <div class="earning-card">
                    <h3>🎯 Daily Bonus</h3>
                    <p>Claim your daily reward</p>
                    <p>Reward: $2.00</p>
                    <button class="earn-btn" id="dailyBtn" onclick="claimDaily()">CLAIM DAILY</button>
                </div>
            </div>
        </div>
        
        <div id="minigames" class="tab-content">
            <div class="earning-section">
                <div class="mini-game">
                    <h3>🎲 Number Guessing Game</h3>
                    <p>Guess a number between 1-10</p>
                    <input type="number" id="guessInput" min="1" max="10" placeholder="Enter guess">
                    <button class="earn-btn" onclick="playGuessGame()">GUESS & WIN</button>
                    <div>Win: $0.50 | Lose: -$0.15</div>
                </div>
                
                <div class="mini-game">
                    <h3>🃏 Card Flip</h3>
                    <p>Find the ace among 4 cards</p>
                    <div id="cardGame">
                        <button onclick="flipCard(0)">Card 1</button>
                        <button onclick="flipCard(1)">Card 2</button>
                        <button onclick="flipCard(2)">Card 3</button>
                        <button onclick="flipCard(3)">Card 4</button>
                    </div>
                    <div>Win: $1.00 | Lose: -$0.35</div>
                </div>
                
                <div class="mini-game">
                    <h3>⚡ Click Challenge</h3>
                    <p>Click as fast as you can in 10 seconds</p>
                    <button class="earn-btn" id="clickBtn" onclick="startClickChallenge()">START CHALLENGE</button>
                    <div>Clicks: <span id="clickCount">0</span> | Time: <span id="clickTime">10</span>s</div>
                    <div>Earn $0.005 per click!</div>
                </div>
            </div>
        </div>
        
        <div id="shop" class="tab-content">
            <div class="shop-section">
                <h2 class="shop-title">🚀 Ultimate Boost Shop</h2>
                <div class="boosts-grid" id="boostGrid">
                    <!-- Boosts will be dynamically generated -->
                </div>
            </div>
        </div>
        
        <div id="payout" class="tab-content">
            <div class="payout-section">
                <h2>💸 Advanced Payout System</h2>
                <p>Minimum payout: $10.00</p>
                <button class="payout-btn" id="payoutBtn" onclick="requestPayout()" disabled>REQUEST FAKE PAYOUT</button>
                <div id="payoutHistory"></div>
            </div>
        </div>
    </div>
    
    <div class="notification" id="notification"></div>
    
    <script>
        let gameData = {
            balance: 0,
            totalEarned: 0,
            multiplier1: 1,
            multiplier2: 1,
            multiplier3: 1,
            multiplier4: 1,
            payouts: 0,
            level: 1,
            xp: 0,
            clickCount: 0,
            dailyClaimed: false,
            acePosition: 0,
            luckBoost: false,
            xpDoubler: false,
            autoClicker: false,
            interestGenerator: false,
            efficiencyBoost: false,
            timeWarp: false,
            lastDailyClaim: 0
        };
        
        const boosts = [
            // Common Boosts
            {name: "Speed Boost", multiplier: 2, price: 0.50, rarity: "common", description: "2x earnings multiplier"},
            {name: "Quick Earn", multiplier: 3, price: 1.00, rarity: "common", description: "3x earnings multiplier"},
            {name: "Fast Track", multiplier: 4, price: 2.00, rarity: "common", description: "4x earnings multiplier"},
            
            // Rare Boosts
            {name: "Super Boost", multiplier: 5, price: 3.50, rarity: "rare", description: "5x earnings multiplier"},
            {name: "Turbo Mode", multiplier: 7, price: 6.00, rarity: "rare", description: "7x earnings multiplier"},
            {name: "Power Up", multiplier: 8, price: 8.50, rarity: "rare", description: "8x earnings multiplier"},
            
            // Epic Boosts
            {name: "Mega Boost", multiplier: 10, price: 12.00, rarity: "epic", description: "10x earnings multiplier"},
            {name: "Ultra Drive", multiplier: 15, price: 20.00, rarity: "epic", description: "15x earnings multiplier"},
            {name: "Hyper Speed", multiplier: 20, price: 35.00, rarity: "epic", description: "20x earnings multiplier"},
            
            // Legendary Boosts
            {name: "Ultimate Boost", multiplier: 25, price: 50.00, rarity: "legendary", description: "25x earnings multiplier"},
            {name: "Divine Power", multiplier: 40, price: 100.00, rarity: "legendary", description: "40x earnings multiplier"},
            {name: "Godlike Speed", multiplier: 60, price: 200.00, rarity: "legendary", description: "60x earnings multiplier"},
            
            // Mythic Boosts
            {name: "Infinite Rush", multiplier: 100, price: 500.00, rarity: "mythic", description: "100x earnings multiplier"},
            {name: "Reality Bender", multiplier: 250, price: 1000.00, rarity: "mythic", description: "250x earnings multiplier"},
            {name: "Time Destroyer", multiplier: 500, price: 2500.00, rarity: "mythic", description: "500x earnings multiplier"},
            
            // Cosmic Boosts
            {name: "Universe Shaker", multiplier: 1000, price: 5000.00, rarity: "cosmic", description: "1000x earnings multiplier"},
            {name: "Dimension Breaker", multiplier: 2500, price: 15000.00, rarity: "cosmic", description: "2500x earnings multiplier"},
            {name: "Multiverse King", multiplier: 10000, price: 50000.00, rarity: "cosmic", description: "10000x earnings multiplier"},
            
            // Special Boosts
            {name: "Luck Enhancer", multiplier: 1.2, price: 25.00, rarity: "rare", description: "1.2x rewards from games", special: "luck"},
            {name: "XP Doubler", multiplier: 1, price: 75.00, rarity: "epic", description: "Double XP gain", special: "xp"},
            {name: "Auto Clicker", multiplier: 1, price: 150.00, rarity: "legendary", description: "Clicks for you every second", special: "auto"},
            {name: "Interest Generator", multiplier: 1, price: 300.00, rarity: "mythic", description: "+0.5% balance every minute", special: "interest"},
            {name: "Efficiency Boost", multiplier: 1, price: 200.00, rarity: "legendary", description: "Reduce timers by 20%", special: "efficiency"},
            {name: "Time Warp", multiplier: 1, price: 400.00, rarity: "mythic", description: "Reduce timers by 50%", special: "timeWarp"}
        ];
        
        function loadGameData() {
            const savedData = localStorage.getItem('earnSimData');
            if (savedData) {
                gameData = JSON.parse(savedData);
                // Check if daily bonus can be reset
                const now = Date.now();
                if (gameData.lastDailyClaim && (now - gameData.lastDailyClaim >= 24 * 60 * 60 * 1000)) {
                    gameData.dailyClaimed = false;
                }
            }
            updateDisplay();
        }

        function saveGameData() {
            localStorage.setItem('earnSimData', JSON.stringify(gameData));
        }

        function resetData() {
            if (confirm('Are you sure you want to reset all game data? This cannot be undone!')) {
                gameData = {
                    balance: 0,
                    totalEarned: 0,
                    multiplier1: 1,
                    multiplier2: 1,
                    multiplier3: 1,
                    multiplier4: 1,
                    payouts: 0,
                    level: 1,
                    xp: 0,
                    clickCount: 0,
                    dailyClaimed: false,
                    acePosition: 0,
                    luckBoost: false,
                    xpDoubler: false,
                    autoClicker: false,
                    interestGenerator: false,
                    efficiencyBoost: false,
                    timeWarp: false,
                    lastDailyClaim: 0
                };
                localStorage.removeItem('earnSimData');
                document.getElementById('payoutHistory').innerHTML = '';
                updateDisplay();
                showNotification('Game data reset!');
            }
        }

        function initializeBoosts() {
            const boostGrid = document.getElementById('boostGrid');
            boosts.forEach((boost, index) => {
                const boostElement = document.createElement('div');
                boostElement.className = `boost-item rarity-${boost.rarity}`;
                boostElement.innerHTML = `
                    <h3>${boost.name}</h3>
                    <p>${boost.description}</p>
                    <p class="boost-price">$${boost.price.toFixed(2)}</p>
                    <button class="buy-btn" onclick="buyBoost(${index})">BUY BOOST</button>
                `;
                boostGrid.appendChild(boostElement);
            });
        }
        
        function switchTab(tabName) {
            document.querySelectorAll('.tab').forEach(tab => tab.classList.remove('active'));
            document.querySelectorAll('.tab-content').forEach(content => content.classList.remove('active'));
            
            document.querySelector(`[onclick="switchTab('${tabName}')"]`).classList.add('active');
            document.getElementById(tabName).classList.add('active');
        }
        
        function updateDisplay() {
            document.getElementById('balance').textContent = gameData.balance.toFixed(2);
            document.getElementById('totalEarned').textContent = gameData.totalEarned.toFixed(2);
            document.getElementById('level').textContent = gameData.level;
            document.getElementById('xp').textContent = gameData.xp;
            
            const xpNeeded = gameData.level * 150; // Increased XP requirement
            document.getElementById('xpNeeded').textContent = xpNeeded;
            document.getElementById('xpBar').style.width = (gameData.xp / xpNeeded * 100) + '%';
            
            for(let i = 1; i <= 4; i++) {
                const multiplierEl = document.getElementById(`multiplier${i}`);
                if(multiplierEl) {
                    multiplierEl.textContent = 'x' + gameData[`multiplier${i}`];
                }
            }
            
            const payoutBtn = document.getElementById('payoutBtn');
            if(payoutBtn) {
                payoutBtn.disabled = gameData.balance < 10;
                if (gameData.balance >= 10) {
                    payoutBtn.textContent = 'REQUEST FAKE PAYOUT ($10.00)';
                }
            }

            document.getElementById('dailyBtn').disabled = gameData.dailyClaimed;
            if (gameData.dailyClaimed) {
                document.getElementById('dailyBtn').textContent = 'CLAIMED TODAY';
            } else {
                document.getElementById('dailyBtn').textContent = 'CLAIM DAILY';
            }
        }
        
        function gainXP(amount) {
            const xpGain = gameData.xpDoubler ? amount * 2 : amount;
            gameData.xp += xpGain;
            const xpNeeded = gameData.level * 150; // Increased difficulty
            if(gameData.xp >= xpNeeded) {
                gameData.xp -= xpNeeded;
                gameData.level++;
                showNotification(`🎉 Level Up! Now level ${gameData.level}`);
                const bonus = gameData.level * 0.25; // Reduced level up bonus
                gameData.balance += bonus;
                gameData.totalEarned += bonus;
                showNotification(`💰 Level up bonus: $${bonus.toFixed(2)}`);
            }
            saveGameData();
        }
        
        function showNotification(message) {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            notification.classList.add('show');
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }
        
        function getTimerReduction() {
            let reduction = 1;
            if (gameData.efficiencyBoost) reduction *= 0.8;
            if (gameData.timeWarp) reduction *= 0.5;
            return reduction;
        }
        
        function startEarning(buttonNum, duration, baseAmount) {
            const button = document.getElementById(`earn${buttonNum}`);
            const timer = document.getElementById(`timer${buttonNum}`);
            const multiplier = gameData[`multiplier${buttonNum}`];
            
            button.disabled = true;
            const reducedDuration = duration * getTimerReduction();
            
            let timeLeft = reducedDuration;
            const interval = setInterval(() => {
                timeLeft -= 100;
                timer.textContent = `⏱️ ${(timeLeft / 1000).toFixed(1)}s`;
                
                if (timeLeft <= 0) {
                    clearInterval(interval);
                    const earned = baseAmount * multiplier;
                    gameData.balance += earned;
                    gameData.totalEarned += earned;
                    gainXP(5);
                    
                    button.disabled = false;
                    timer.textContent = '';
                    updateDisplay();
                    showNotification(`+$${earned.toFixed(2)} earned!`);
                }
            }, 100);
            saveGameData();
        }
        
        function buyBoost(index) {
            const boost = boosts[index];
            if (gameData.balance >= boost.price) {
                gameData.balance -= boost.price;
                
                if(boost.special) {
                    handleSpecialBoost(boost);
                } else {
                    for(let i = 1; i <= 4; i++) {
                        gameData[`multiplier${i}`] = Math.max(gameData[`multiplier${i}`], boost.multiplier);
                    }
                }
                
                updateDisplay();
                showNotification(`${boost.name} purchased! ${boost.description}`);
                saveGameData();
            } else {
                showNotification('Not enough fake money!');
            }
        }
        
        function handleSpecialBoost(boost) {
            switch(boost.special) {
                case 'luck':
                    gameData.luckBoost = true;
                    break;
                case 'xp':
                    gameData.xpDoubler = true;
                    break;
                case 'auto':
                    if(!gameData.autoClicker) {
                        gameData.autoClicker = true;
                        setInterval(() => {
                            gameData.balance += 0.005 * gameData.multiplier1;
                            gameData.totalEarned += 0.005 * gameData.multiplier1;
                            updateDisplay();
                            saveGameData();
                        }, 1000);
                    }
                    break;
                case 'interest':
                    if(!gameData.interestGenerator) {
                        gameData.interestGenerator = true;
                        setInterval(() => {
                            const interest = gameData.balance * 0.005; // Reduced to 0.5%
                            gameData.balance += interest;
                            gameData.totalEarned += interest;
                            if(interest > 0.01) {
                                showNotification(`💰 Interest earned: ${interest.toFixed(2)}`);
                            }
                            updateDisplay();
                            saveGameData();
                        }, 60000);
                    }
                    break;
                case 'efficiency':
                    gameData.efficiencyBoost = true;
                    break;
                case 'timeWarp':
                    gameData.timeWarp = true;
                    break;
            }
        }
        
        function investStock() {
            const amount = parseFloat(document.getElementById('stockAmount').value);
            if(gameData.balance >= amount) {
                gameData.balance -= amount;
                updateDisplay();
                showNotification('📊 Investment started...');
                
                const duration = 60000 * getTimerReduction();
                setTimeout(() => {
                    const lossChance = Math.random();
                    let profit = 0;
                    if (lossChance < 0.4) { // 40% chance to lose
                        showNotification('📉 Investment failed! Lost investment.');
                    } else {
                        const return_multiplier = Math.random() * 2; // 0x-2x return
                        profit = amount * return_multiplier;
                        gameData.balance += profit;
                        gameData.totalEarned += profit - amount;
                        showNotification(`📈 Stock returned: ${profit.toFixed(2)}`);
                    }
                    gainXP(15 * amount);
                    updateDisplay();
                    saveGameData();
                }, duration);
            } else {
                showNotification(`Need $${amount.toFixed(2)} to invest!`);
            }
        }
        
        function startMining() {
            const amount = parseFloat(document.getElementById('miningAmount').value);
            if(gameData.balance >= amount) {
                gameData.balance -= amount;
                updateDisplay();
                const miningTimer = document.getElementById('miningTimer');
                showNotification('⛏️ Mining started...');
                
                let timeLeft = 60000 * getTimerReduction();
                const interval = setInterval(() => {
                    timeLeft -= 1000;
                    miningTimer.textContent = `⏱️ ${Math.ceil(timeLeft / 1000)}s`;
                    
                    if(timeLeft <= 0) {
                        clearInterval(interval);
                        const lossChance = Math.random();
                        let mined = 0;
                        if (lossChance < 0.3) { // 30% chance to lose
                            showNotification('⛏️ Mining failed! Lost investment.');
                        } else {
                            mined = amount * (Math.random() * 2.5); // 0x-2.5x return
                            gameData.balance += mined;
                            gameData.totalEarned += mined - amount;
                            showNotification(`⛏️ Mined: ${mined.toFixed(2)}`);
                        }
                        gainXP(20 * amount);
                        miningTimer.textContent = '';
                        updateDisplay();
                        saveGameData();
                    }
                }, 1000);
            } else {
                showNotification(`Need $${amount.toFixed(2)} to start mining!`);
            }
        }
        
        function spinWheel() {
            if(gameData.balance >= 0.25) {
                gameData.balance -= 0.25;
                updateDisplay();
                
                const outcomes = [0, 0.10, 0.20, 0.30, 0.50, 1.00, 1.50, 2.00];
                const weights = [40, 30, 15, 10, 3, 1.5, 0.4, 0.1]; // Increased chance of low/no rewards
                
                let random = Math.random() * 100;
                let cumulative = 0;
                let winAmount = 0;
                
                for(let i = 0; i < weights.length; i++) {
                    cumulative += weights[i];
                    if(random <= cumulative) {
                        winAmount = outcomes[i];
                        break;
                    }
                }
                
                if(gameData.luckBoost) winAmount *= 1.2; // Reduced luck boost effect
                
                gameData.balance += winAmount;
                gameData.totalEarned += winAmount - 0.25;
                gainXP(10);
                updateDisplay();
                showNotification(`🎰 Spin result: ${winAmount.toFixed(2)}`);
                saveGameData();
            } else {
                showNotification('Need $0.25 to spin!');
            }
        }
        
        function startSurvey() {
            const surveyBtn = document.getElementById('surveyBtn');
            const surveyTimer = document.getElementById('surveyTimer');
            
            surveyBtn.disabled = true;
            showNotification('📝 Starting survey...');
            
            let timeLeft = 20000 * getTimerReduction();
            const interval = setInterval(() => {
                timeLeft -= 1000;
                surveyTimer.textContent = `⏱️ ${Math.ceil(timeLeft / 1000)}s`;
                
                if(timeLeft <= 0) {
                    clearInterval(interval);
                    const earned = 0.15 * gameData.multiplier1;
                    gameData.balance += earned;
                    gameData.totalEarned += earned;
                    gainXP(8);
                    surveyBtn.disabled = false;
                    surveyTimer.textContent = '';
                    updateDisplay();
                    showNotification(`📝 Survey completed: ${earned.toFixed(2)}`);
                    saveGameData();
                }
            }, 1000);
        }
        
        function watchAd() {
            const adBtn = document.getElementById('adBtn');
            const adTimer = document.getElementById('adTimer');
            
            adBtn.disabled = true;
            showNotification('📱 Watching ad...');
            
            let timeLeft = 10000 * getTimerReduction();
            const interval = setInterval(() => {
                timeLeft -= 1000;
                adTimer.textContent = `⏱️ ${Math.ceil(timeLeft / 1000)}s`;
                
                if(timeLeft <= 0) {
                    clearInterval(interval);
                    const earned = 0.05 * gameData.multiplier1;
                    gameData.balance += earned;
                    gameData.totalEarned += earned;
                    gainXP(3);
                    adBtn.disabled = false;
                    adTimer.textContent = '';
                    updateDisplay();
                    showNotification(`📱 Ad watched: ${earned.toFixed(2)}`);
                    saveGameData();
                }
            }, 1000);
        }
        
        function claimDaily() {
            if(!gameData.dailyClaimed) {
                const earned = 2.00 * gameData.multiplier1;
                gameData.balance += earned;
                gameData.totalEarned += earned;
                gameData.dailyClaimed = true;
                gameData.lastDailyClaim = Date.now();
                gainXP(50);
                updateDisplay();
                showNotification(`🎯 Daily bonus claimed: ${earned.toFixed(2)}`);
                
                document.getElementById('dailyBtn').textContent = 'CLAIMED TODAY';
                document.getElementById('dailyBtn').disabled = true;
                
                setTimeout(() => {
                    gameData.dailyClaimed = false;
                    document.getElementById('dailyBtn').textContent = 'CLAIM DAILY';
                    document.getElementById('dailyBtn').disabled = false;
                    updateDisplay();
                    showNotification('🎯 Daily bonus available again!');
                    saveGameData();
                }, 24 * 60 * 60 * 1000); // 24 hours
                saveGameData();
            }
        }
        
        function playGuessGame() {
            const guess = parseInt(document.getElementById('guessInput').value);
            const correct = Math.floor(Math.random() * 10) + 1;
            
            if(guess >= 1 && guess <= 10) {
                if(guess === correct) {
                    let winAmount = 0.50;
                    if(gameData.luckBoost) winAmount *= 1.2;
                    gameData.balance += winAmount;
                    gameData.totalEarned += winAmount;
                    gainXP(25);
                    showNotification(`🎉 Correct! Number was ${correct}. Won ${winAmount.toFixed(2)}`);
                } else {
                    gameData.balance -= 0.15; // Increased loss penalty
                    showNotification(`❌ Wrong! Number was ${correct}. Lost $0.15`);
                }
                updateDisplay();
                document.getElementById('guessInput').value = '';
                saveGameData();
            } else {
                showNotification('Please enter a number between 1 and 10!');
            }
        }
        
        function flipCard(cardIndex) {
            if(gameData.acePosition === cardIndex) {
                let winAmount = 1.00;
                if(gameData.luckBoost) winAmount *= 1.2;
                gameData.balance += winAmount;
                gameData.totalEarned += winAmount;
                gainXP(30);
                showNotification(`🃏 Found the Ace! Won ${winAmount.toFixed(2)}`);
            } else {
                gameData.balance -= 0.35; // Increased loss penalty
                showNotification(`❌ Wrong card! The Ace was at position ${gameData.acePosition + 1}`);
            }
            
            gameData.acePosition = Math.floor(Math.random() * 4);
            updateDisplay();
            saveGameData();
        }
        
        function startClickChallenge() {
            const clickBtn = document.getElementById('clickBtn');
            const clickCountEl = document.getElementById('clickCount');
            const clickTimeEl = document.getElementById('clickTime');
            
            gameData.clickCount = 0;
            let timeLeft = 10;
            
            clickBtn.disabled = true;
            clickBtn.textContent = 'CLICK ME FAST!';
            clickBtn.onclick = () => {
                gameData.clickCount++;
                clickCountEl.textContent = gameData.clickCount;
            };
            
            const interval = setInterval(() => {
                timeLeft--;
                clickTimeEl.textContent = timeLeft;
                
                if(timeLeft <= 0) {
                    clearInterval(interval);
                    const earned = gameData.clickCount * 0.005 * gameData.multiplier1; // Reduced per-click reward
                    gameData.balance += earned;
                    gameData.totalEarned += earned;
                    gainXP(gameData.clickCount);
                    
                    clickBtn.disabled = false;
                    clickBtn.textContent = 'START CHALLENGE';
                    clickBtn.onclick = () => startClickChallenge();
                    clickTimeEl.textContent = '10';
                    
                    updateDisplay();
                    showNotification(`⚡ Challenge complete! ${gameData.clickCount} clicks = ${earned.toFixed(2)}`);
                    saveGameData();
                }
            }, 1000);
        }
        
        function requestPayout() {
            if (gameData.balance >= 10) {
                gameData.balance -= 10;
                gameData.payouts++;
                updateDisplay();
                
                const payoutHistory = document.getElementById('payoutHistory');
                const payoutDiv = document.createElement('div');
                payoutDiv.style.cssText = 'margin-top: 10px; padding: 10px; background: rgba(0,255,0,0.2); border-radius: 5px;';
                payoutDiv.innerHTML = `✅ Fake Payout #${gameData.payouts}: $10.00 - ${new Date().toLocaleString()}`;
                payoutHistory.appendChild(payoutDiv);
                
                showNotification('Fake payout processed! 🎉');
                gainXP(100);
                
                if (gameData.payouts >= 3) {
                    const specialShop = document.createElement('div');
                    specialShop.style.cssText = 'margin-top: 20px; padding: 15px; background: rgba(255,215,0,0.2); border-radius: 10px; border: 2px solid gold;';
                    specialShop.innerHTML = `
                        <h3>🏆 VIP Shop Unlocked!</h3>
                        <p>Spend your fake payouts here:</p>
                        <button onclick="buyFakeItem('Golden Badge', 2)" style="margin: 5px; padding: 10px; background: gold; color: black; border: none; border-radius: 5px; cursor: pointer;">Golden Badge (2 payouts)</button>
                        <button onclick="buyFakeItem('Diamond Trophy', 5)" style="margin: 5px; padding: 10px; background: lightblue; color: black; border: none; border-radius: 5px; cursor: pointer;">Diamond Trophy (5 payouts)</button>
                        <button onclick="buyFakeItem('Platinum Crown', 10)" style="margin: 5px; padding: 10px; background: silver; color: black; border: none; border-radius: 5px; cursor: pointer;">Platinum Crown (10 payouts)</button>
                        <button onclick="buyFakeItem('Legendary Sword', 20)" style="margin: 5px; padding: 10px; background: purple; color: white; border: none; border-radius: 5px; cursor: pointer;">Legendary Sword (20 payouts)</button>
                    `;
                    if (!document.querySelector('.vip-shop')) {
                        specialShop.className = 'vip-shop';
                        payoutHistory.appendChild(specialShop);
                    }
                }
                saveGameData();
            }
        }
        
        function buyFakeItem(item, cost) {
            if (gameData.payouts >= cost) {
                gameData.payouts -= cost;
                showNotification(`🎁 You bought: ${item}! (This is fake too!)`);
                updateDisplay();
                saveGameData();
            } else {
                showNotification('Not enough fake payouts!');
            }
        }
        
        function initGame() {
            loadGameData();
            initializeBoosts();
            updateDisplay();
            gameData.acePosition = Math.floor(Math.random() * 4);
            
            setInterval(() => {
                const particle = document.createElement('div');
                particle.textContent = ['💰', '💎', '⭐', '🎉', '✨', '🚀', '⚡', '🎯'][Math.floor(Math.random() * 8)];
                particle.style.cssText = `
                    position: fixed;
                    font-size: 20px;
                    pointer-events: none;
                    z-index: 999;
                    animation: float 3s ease-out forwards;
                    left: ${Math.random() * window.innerWidth}px;
                    top: ${window.innerHeight}px;
                `;
                document.body.appendChild(particle);
                setTimeout(() => particle.remove(), 3000);
            }, 2000);
        }
        
        const style = document.createElement('style');
        style.textContent = `
            @keyframes float {
                to {
                    transform: translateY(-100vh) rotate(360deg);
                    opacity: 0;
                }
            }
        `;
        document.head.appendChild(style);
        
        initGame();
    </script>
</body>
</html>
