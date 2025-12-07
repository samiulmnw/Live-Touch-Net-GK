<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>ULTIMATE STREAM & STORE | V18.0 PRO</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Baloo+Da+2:wght@500;700;800&family=Rajdhani:wght@700;800;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    
    <style>
        /* ========================================================================= */
        /* ১. গ্লোবাল স্টাইলস এবং ভেরিয়েবলস */
        /* ========================================================================= */
        :root {
            --color-deep-blue: #020710;          
            --color-accent-aqua: #00ffc3;        
            --color-accent-gold: #FFC72C;  
            --color-fire-orange: #ff4500; /* Free Fire Color */
            --color-text-light: #ECF0F1;
            
            --ultimate-glow: 
                0 0 15px var(--color-accent-aqua), 
                0 0 60px var(--color-accent-aqua); 
            
            --fire-glow:
                0 0 15px var(--color-fire-orange),
                0 0 40px var(--color-accent-gold);

            --bg-image: url('https://images.unsplash.com/photo-1542751371-adc38448a05e?fit=crop&w=1920&h=1080&q=80');
        }
        
        * { box-sizing: border-box; }

        body {
            font-family: 'Baloo Da 2', sans-serif; 
            margin: 0;
            padding: 0;
            min-height: 100vh;
            background-color: var(--color-deep-blue);
            color: var(--color-text-light);
            overflow-x: hidden;
            
            /* ব্যাকগ্রাউন্ড সেটআপ */
            background-image: 
                linear-gradient(to top, var(--color-deep-blue) 0%, rgba(2, 7, 16, 0.9) 60%, rgba(2, 7, 16, 0.95) 100%),
                var(--bg-image);
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
        }

        /* স্ক্রিন ট্রানজিশন এনিমেশন */
        .screen-section {
            display: none; /* ডিফল্ট হাইড */
            animation: fadeIn 0.5s ease-in-out;
            width: 100%;
            min-height: 100vh;
            padding-bottom: 80px;
        }

        .screen-section.active {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* ========================================================================= */
        /* ২. হোম স্ক্রিন (TOUCH NET IP TV) ডিজাইন */
        /* ========================================================================= */
        .header-section {
            padding-top: 40px;
            text-align: center;
            width: 95%;
        }
        .header-section h1 {
            font-family: 'Rajdhani', sans-serif;
            font-size: 3.5rem; 
            font-weight: 900;
            color: var(--color-text-light); 
            text-transform: uppercase;
            text-shadow: var(--ultimate-glow); 
            letter-spacing: 3px;
            margin: 0;
        }
        .subtitle {
            font-size: 1.2rem; 
            color: var(--color-accent-gold);
            margin-bottom: 30px; 
            font-weight: 700;
            text-shadow: 0 0 5px var(--color-accent-gold);
        }

        .main-card-container {
            width: 90%;
            max-width: 500px;
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        /* কমন কার্ড স্টাইল */
        .glass-card {
            background: rgba(255, 255, 255, 0.05); 
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.1); 
            border-radius: 20px;
            padding: 25px; 
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            transition: transform 0.3s ease, border-color 0.3s ease;
        }
        .glass-card:hover {
            transform: translateY(-5px);
            border-color: rgba(255, 255, 255, 0.3);
        }

        /* লাইভ টিভি বাটন */
        .launch-btn {
            background: var(--color-accent-aqua);
            border: none;
            border-radius: 10px; 
            padding: 15px 30px; 
            color: var(--color-deep-blue);
            font-weight: 900;
            font-size: 1.2em; 
            text-transform: uppercase;
            box-shadow: 0 0 15px var(--color-accent-aqua);
            transition: all 0.3s ease;
            cursor: pointer;
            width: 100%;
        }
        .launch-btn:active { transform: scale(0.95); }

        /* ফ্রি ফায়ার স্পেশাল কার্ড */
        .ff-card {
            border: 1px solid var(--color-fire-orange);
            background: linear-gradient(145deg, rgba(255, 69, 0, 0.1), rgba(0, 0, 0, 0.6));
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }
        .ff-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,199,44,0.1) 0%, transparent 70%);
            animation: spin 10s linear infinite;
        }
        @keyframes spin { 100% { transform: rotate(360deg); } }

        .ff-content {
            position: relative;
            z-index: 2;
        }
        .ff-icon {
            font-size: 3rem;
            color: var(--color-fire-orange);
            margin-bottom: 10px;
            filter: drop-shadow(0 0 10px var(--color-fire-orange));
        }
        .ff-title {
            font-family: 'Rajdhani', sans-serif;
            font-size: 2rem;
            font-weight: 800;
            color: #fff;
            margin: 0;
            text-shadow: 0 0 10px var(--color-fire-orange);
        }
        .ff-sub {
            color: var(--color-accent-gold);
            font-size: 0.9rem;
            font-weight: 700;
        }
        .click-hint {
            margin-top: 15px;
            font-size: 0.8rem;
            color: #aaa;
            animation: pulse 1.5s infinite;
        }
        @keyframes pulse { 0%, 100% { opacity: 0.5; } 50% { opacity: 1; } }

        /* ========================================================================= */
        /* ৩. টপ আপ স্টোর (GK TOP UP) ডিজাইন */
        /* ========================================================================= */
        .topup-header {
            width: 100%;
            padding: 15px 20px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            background: rgba(0,0,0,0.6);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid var(--color-fire-orange);
            position: sticky;
            top: 0;
            z-index: 50;
        }
        .back-btn {
            background: none;
            border: 1px solid rgba(255,255,255,0.3);
            color: white;
            padding: 5px 15px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
        }
        .store-title {
            color: var(--color-accent-gold);
            font-family: 'Rajdhani', sans-serif;
            font-size: 1.5rem;
            font-weight: 800;
        }

        .products-container {
            width: 95%;
            max-width: 1000px;
            padding: 20px 0;
        }
        
        .section-badge {
            background: linear-gradient(90deg, transparent, var(--color-fire-orange), transparent);
            text-align: center;
            padding: 8px;
            margin: 20px 0;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 2px;
            border-radius: 4px;
        }

        .grid-layout {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
            gap: 15px;
        }

        .item-card {
            background: rgba(20, 33, 61, 0.7);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 12px;
            padding: 15px;
            text-align: center;
            position: relative;
            transition: 0.3s;
        }
        .item-card:hover {
            border-color: var(--color-accent-aqua);
            transform: translateY(-5px);
            background: rgba(20, 33, 61, 0.9);
        }

        .item-icon svg {
            width: 40px; 
            height: 40px; 
            filter: drop-shadow(0 0 5px cyan);
            margin-bottom: 10px;
        }
        .item-name { font-size: 0.9rem; font-weight: 700; margin-bottom: 5px; }
        .item-price { font-size: 1.2rem; color: var(--color-accent-gold); font-weight: 800; display: block; margin-bottom: 10px; }
        
        .buy-now-btn {
            width: 100%;
            background: linear-gradient(90deg, #fca311, #d00000);
            border: none;
            color: white;
            padding: 8px;
            border-radius: 5px;
            font-weight: bold;
            cursor: pointer;
            font-size: 0.8rem;
        }

        /* মোডাল ডিজাইন */
        .modal-overlay {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.9);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        .modal-box {
            background: #1e1e1e;
            width: 100%;
            max-width: 400px;
            border-radius: 15px;
            padding: 25px;
            border: 1px solid var(--color-accent-gold);
            position: relative;
            animation: zoomIn 0.3s;
        }
        @keyframes zoomIn { from {transform: scale(0.8); opacity: 0;} to {transform: scale(1); opacity: 1;} }

        .close-icon {
            position: absolute;
            top: 15px; right: 20px;
            font-size: 1.5rem;
            cursor: pointer;
            color: #aaa;
        }

        .form-input {
            width: 100%;
            padding: 12px;
            margin-bottom: 15px;
            background: #000;
            border: 1px solid #444;
            color: white;
            border-radius: 5px;
        }
        .confirm-order-btn {
            width: 100%;
            padding: 12px;
            background: #25D366; /* WhatsApp Green */
            color: white;
            border: none;
            border-radius: 5px;
            font-weight: bold;
            font-size: 1rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        /* ফুটার */
        footer {
            position: fixed;
            bottom: 0; left: 0; right: 0;
            background: rgba(2, 7, 16, 0.95);
            border-top: 1px solid var(--color-accent-gold);
            padding: 10px;
            text-align: center;
            font-size: 0.8rem;
            color: #aaa;
            z-index: 100;
        }
    </style>
</head>
<body>

    <div id="home-screen" class="screen-section active">
        <div class="header-section">
            <h1>TOUCH NET IP TV</h1>
            <p class="subtitle">প্রিমিয়াম স্ট্রিমিং এবং গেমিং হাব</p>
        </div>

        <div class="main-card-container">
            <div class="glass-card">
                <p style="color: var(--color-accent-aqua); font-weight: bold; margin-bottom: 15px; font-size: 1.2rem;">লাইভ টিভি চ্যানেল</p>
                <button class="launch-btn" id="stream-button">LAUNCH LIVE TV</button>
            </div>

            <div class="glass-card ff-card" onclick="switchScreen('topup-screen')">
                <div class="ff-content">
                    <i class="fas fa-fire-alt ff-icon"></i>
                    <h2 class="ff-title">FREE FIRE TOP UP</h2>
                    <p class="ff-sub">DIAMOND & MEMBERSHIP SHOP</p>
                    <div class="click-hint">CLICK TO OPEN STORE</div>
                </div>
            </div>
        </div>
    </div>

    <div id="topup-screen" class="screen-section">
        <div class="topup-header">
            <button class="back-btn" onclick="switchScreen('home-screen')">
                <i class="fas fa-arrow-left"></i> BACK
            </button>
            <div class="store-title">GK PREMIUM SHOP</div>
            <div style="width: 60px;"></div> </div>

        <div class="products-container">
            <div class="section-badge">Regular Diamond</div>
            <div class="grid-layout">
                <div class="item-card">
                    <div class="item-icon">
                        <svg viewBox="0 0 24 24"><path fill="#00ffff" d="M12 2L2 8L12 22L22 8L12 2Z"/></svg>
                    </div>
                    <div class="item-name">115 Diamond</div>
                    <div class="item-price">৳ ৮৯</div>
                    <button class="buy-now-btn" onclick="openModal('115 Diamond', '89')">BUY NOW</button>
                </div>
                <div class="item-card">
                    <div class="badge" style="position: absolute; top:0; right:0; background:red; font-size:10px; padding:2px 5px;">HOT</div>
                    <div class="item-icon">
                        <svg viewBox="0 0 24 24"><path fill="#00ffff" d="M12 2L2 8L12 22L22 8L12 2Z"/></svg>
                    </div>
                    <div class="item-name">240 Diamond</div>
                    <div class="item-price">৳ ১৬৯</div>
                    <button class="buy-now-btn" onclick="openModal('240 Diamond', '169')">BUY NOW</button>
                </div>
                <div class="item-card">
                    <div class="item-icon">
                        <svg viewBox="0 0 24 24"><path fill="#00ffff" d="M12 2L2 8L12 22L22 8L12 2Z"/></svg>
                    </div>
                    <div class="item-name">355 Diamond</div>
                    <div class="item-price">৳ ২৫৯</div>
                    <button class="buy-now-btn" onclick="openModal('355 Diamond', '259')">BUY NOW</button>
                </div>
                <div class="item-card">
                    <div class="item-icon">
                        <svg viewBox="0 0 24 24"><path fill="#00ffff" d="M12 2L2 8L12 22L22 8L12 2Z"/></svg>
                    </div>
                    <div class="item-name">610 Diamond</div>
                    <div class="item-price">৳ ৪৪৯</div>
                    <button class="buy-now-btn" onclick="openModal('610 Diamond', '449')">BUY NOW</button>
                </div>
            </div>

            <div class="section-badge">Pass & Membership</div>
            <div class="grid-layout">
                <div class="item-card">
                    <div class="item-icon">
                        <svg viewBox="0 0 24 24"><path fill="#FFD700" d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm-8 10l-2-4h4l-2 4z"/></svg>
                    </div>
                    <div class="item-name">Weekly Membership</div>
                    <div class="item-price">৳ ১৫৯</div>
                    <button class="buy-now-btn" onclick="openModal('Weekly Membership', '159')">BUY NOW</button>
                </div>
                <div class="item-card">
                    <div class="item-icon">
                        <svg viewBox="0 0 24 24"><path fill="#FFC72C" d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 15l-4-4 1.41-1.41L11 14.17l5.59-5.59L18 10l-7 7z"/></svg>
                    </div>
                    <div class="item-name">Monthly Membership</div>
                    <div class="item-price">৳ ৭৯৯</div>
                    <button class="buy-now-btn" onclick="openModal('Monthly Membership', '799')">BUY NOW</button>
                </div>
                <div class="item-card">
                    <div class="item-icon">
                        <svg viewBox="0 0 24 24"><path fill="#ff4500" d="M12 2L4 20H20L12 2Z"/></svg>
                    </div>
                    <div class="item-name">Level Up Pass</div>
                    <div class="item-price">৳ ১৮৯</div>
                    <button class="buy-now-btn" onclick="openModal('Level Up Pass', '189')">BUY NOW</button>
                </div>
            </div>
        </div>
    </div>

    <div id="paymentModal" class="modal-overlay">
        <div class="modal-box">
            <span class="close-icon" onclick="closeModal()">&times;</span>
            <h3 style="color: var(--color-accent-gold); text-align: center; margin-top: 0;">CONFIRM ORDER</h3>
            
            <div style="background: #2b2b2b; padding: 10px; border-radius: 5px; border-left: 3px solid var(--color-accent-gold); margin-bottom: 20px;">
                <div style="display: flex; justify-content: space-between;">
                    <span style="color: #ccc;">Item:</span>
                    <span id="modal-pack" style="color: var(--color-accent-aqua); font-weight: bold;"></span>
                </div>
                <div style="display: flex; justify-content: space-between; margin-top: 5px;">
                    <span style="color: #ccc;">Price:</span>
                    <span style="color: white; font-weight: bold;">৳ <span id="modal-price"></span></span>
                </div>
                <hr style="border-color: #444; margin: 10px 0;">
                <div style="text-align: center;">
                    <small style="color: #aaa;">Send Money (Bkash/Nagad)</small><br>
                    <span style="font-size: 1.2rem; color: var(--color-accent-gold); font-weight: bold; letter-spacing: 1px;">01873228584</span>
                </div>
            </div>

            <form onsubmit="processOrder(event)">
                <input type="number" id="uid" class="form-input" placeholder="Enter Player UID (Game ID)" required>
                <input type="number" id="lastDigits" class="form-input" placeholder="Sender Number (Last 3 Digits)" required>
                <input type="text" id="trxid" class="form-input" placeholder="Transaction ID (TrxID)" required>
                
                <button type="submit" class="confirm-order-btn">
                    <i class="fab fa-whatsapp"></i> Confirm on WhatsApp
                </button>
            </form>
        </div>
    </div>

    <footer>
        <p>Project Created by: <strong>SH HIMEL</strong> | All Right Reserved © 2028</p>
    </footer>

    <script>
        // ১. স্ক্রিন সুইচিং লজিক (হোম <-> টপ আপ)
        function switchScreen(screenId) {
            // সব স্ক্রিন থেকে active ক্লাস সরিয়ে ফেলা
            document.querySelectorAll('.screen-section').forEach(screen => {
                screen.classList.remove('active');
            });
            // নির্দিষ্ট স্ক্রিনে active ক্লাস যোগ করা
            document.getElementById(screenId).classList.add('active');
            
            // স্ক্রিন টপে নিয়ে যাওয়া
            window.scrollTo(0, 0);
        }

        // ২. লাইভ টিভি বাটন লজিক
        const streamBtn = document.getElementById('stream-button');
        streamBtn.addEventListener('click', function() {
            this.textContent = "CONNECTING SERVER...";
            this.style.background = "#FFC72C"; // গোল্ড কালার
            
            setTimeout(() => {
                window.location.href = 'http://redforce.live/'; 
            }, 1000); 
        });

        // ৩. অর্ডার মোডাল এবং হোয়াটসঅ্যাপ লজিক
        let selectedItem = "";
        let selectedPrice = "";
        const adminPhone = "8801873228584"; 

        function openModal(item, price) {
            selectedItem = item;
            selectedPrice = price;
            document.getElementById('modal-pack').innerText = item;
            document.getElementById('modal-price').innerText = price;
            document.getElementById('paymentModal').style.display = 'flex';
        }

        function closeModal() {
            document.getElementById('paymentModal').style.display = 'none';
        }

        // মোডালের বাইরে ক্লিক করলে বন্ধ হবে
        window.onclick = function(e) {
            if (e.target == document.getElementById('paymentModal')) {
                closeModal();
            }
        }

        function processOrder(e) {
            e.preventDefault();
            const uid = document.getElementById('uid').value;
            const lastDigits = document.getElementById('lastDigits').value;
            const trxid = document.getElementById('trxid').value;

            // মেসেজ ফরম্যাটিং
            const text = `*✅ NEW TOPUP ORDER* %0A` +
                         `-----------------------------%0A` +
                         `💎 *Pack:* ${selectedItem} %0A` +
                         `💰 *Price:* ${selectedPrice} TK %0A` +
                         `-----------------------------%0A` +
                         `🎮 *UID:* ${uid} %0A` +
                         `📱 *Sender Last 3:* ${lastDigits} %0A` +
                         `🧾 *TrxID:* ${trxid} %0A` +
                         `-----------------------------%0A` +
                         `Please verify and send diamonds fast!`;

            // হোয়াটসঅ্যাপ ওপেন
            window.open(`https://wa.me/${adminPhone}?text=${text}`, '_blank');
            
            closeModal();
            // ইনপুট রিসেট
            document.getElementById('uid').value = '';
            document.getElementById('lastDigits').value = '';
            document.getElementById('trxid').value = '';
        }
    </script>

</body>
</html>
