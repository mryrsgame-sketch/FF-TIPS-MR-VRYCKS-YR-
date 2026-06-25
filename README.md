# FF-TIPS-MR-VRYCKS-YR-
```html
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Glitch Master Zone</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts for Bengali and English -->
    <link href="https://fonts.googleapis.com/css2?family=Hind+Siliguri:wght@400;600;700&family=Orbitron:wght@500;800&display=swap" rel="stylesheet">
    <style>
        body {
            background-color: #070a13;
            font-family: 'Hind Siliguri', 'Orbitron', sans-serif;
            color: #ffffff;
            overflow-x: hidden;
            /* স্ক্রল করার ফিল দেওয়ার জন্য হাইট বাড়ানো হয়েছে */
            min-height: 120vh; 
        }

        /* 3D Glass Card with Dynamic Backlight (আগের অরিজিনাল গ্লো ফিরিয়ে আনা হয়েছে) */
        .glass-card {
            background: rgba(17, 25, 40, 0.7);
            backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 24px;
            animation: backlight-shift 6s infinite alternate ease-in-out;
            padding-bottom: 2.5rem; 
        }

        /* Backlight Animation (ফুল পাওয়ার) */
        @keyframes backlight-shift {
            0% { box-shadow: 0 10px 40px -10px rgba(0, 198, 255, 0.4); }
            50% { box-shadow: 0 10px 50px -5px rgba(138, 43, 226, 0.5); }
            100% { box-shadow: 0 10px 40px -10px rgba(0, 255, 136, 0.4); }
        }

        /* Logo Zoom In/Out Animation */
        .logo-anim {
            animation: pulse-logo 3s ease-in-out infinite;
            box-shadow: 0 0 25px rgba(59, 130, 246, 0.6);
        }
        @keyframes pulse-logo {
            0% { transform: scale(1); box-shadow: 0 0 20px rgba(59, 130, 246, 0.5); }
            50% { transform: scale(1.15); box-shadow: 0 0 40px rgba(59, 130, 246, 0.8); }
            100% { transform: scale(1); box-shadow: 0 0 20px rgba(59, 130, 246, 0.5); }
        }

        /* Subscribe Button (আগের হাইলাইটেড রেড থিম) */
        .btn-sub {
            background: linear-gradient(135deg, #cc0000 0%, #8b0000 100%);
            border: 1px solid rgba(255, 50, 50, 0.5);
            animation: sub-glow 2.5s infinite alternate ease-in-out;
            transition: all 0.3s ease;
            font-family: 'Orbitron', sans-serif;
        }
        .btn-sub:hover {
            transform: translateY(-3px) scale(1.02);
            background: linear-gradient(135deg, #ff1a1a 0%, #990000 100%);
        }
        @keyframes sub-glow {
            0% { box-shadow: 0 0 15px rgba(255, 0, 0, 0.5); }
            100% { box-shadow: 0 0 35px rgba(255, 0, 0, 0.9); }
        }

        /* Tips & Tricks Button */
        .btn-tips {
            background: rgba(15, 23, 42, 0.9);
            border: 1px solid rgba(56, 189, 248, 0.6);
            animation: tips-glow 4s infinite alternate ease-in-out;
            transition: all 0.3s ease;
        }
        .btn-tips:hover {
            background: rgba(56, 189, 248, 0.15);
            transform: translateY(-2px);
        }
        @keyframes tips-glow {
            0% { box-shadow: 0 0 10px rgba(56, 189, 248, 0.3); }
            100% { box-shadow: 0 0 25px rgba(56, 189, 248, 0.6); }
        }

        /* Menu Items - দূরে দূরে রাখার জন্য স্পেসিং দেওয়া হয়েছে */
        .btn-menu-item {
            background: rgba(30, 41, 59, 0.6);
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: 0.3s;
            margin-bottom: 1.25rem; /* স্পেসিং */
        }
        .btn-menu-item:hover {
            background: rgba(59, 130, 246, 0.2);
            border-color: rgba(59, 130, 246, 0.4);
            transform: scale(1.02) translateX(5px);
            box-shadow: -5px 0 15px rgba(59, 130, 246, 0.3);
        }

        /* Custom Scrollbar */
        .scroll-container {
            max-height: 60vh; 
            overflow-y: auto;
            padding-right: 12px;
        }
        .scroll-container::-webkit-scrollbar {
            width: 6px;
        }
        .scroll-container::-webkit-scrollbar-track {
            background: rgba(0, 0, 0, 0.2);
            border-radius: 10px;
        }
        .scroll-container::-webkit-scrollbar-thumb {
            background: #3b82f6;
            border-radius: 10px;
        }

        /* Text Color Changing Animation for Titles (আগের মতো লাইট চেঞ্জ হবে) */
        .dynamic-text-color {
            background: linear-gradient(90deg, #00c6ff, #0072ff, #00c6ff, #8a2be2, #00c6ff);
            background-size: 300% 100%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradient-text 5s infinite linear;
        }

        @keyframes gradient-text {
            0% { background-position: 0% 50%; }
            100% { background-position: 100% 50%; }
        }

        /* Language Toggle Button styling */
        .lang-btn {
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }
        .lang-btn:hover {
            background: rgba(59, 130, 246, 0.3);
            border-color: rgba(59, 130, 246, 0.6);
        }
    </style>
</head>
<body class="flex flex-col items-center py-8 px-4 relative">

    <!-- ভাষা পরিবর্তনের বাটন (Language Switcher) -->
    <div class="max-w-xl w-full flex justify-end mb-6 relative z-20">
        <button onclick="toggleLanguage()" class="lang-btn px-5 py-2.5 rounded-xl text-sm font-bold flex items-center gap-2 text-white shadow-md">
            🌐 <span id="lang-text">English</span>
        </button>
    </div>

    <!-- প্রথম স্ক্রিন: ল্যান্ডিং পেজ -->
    <div id="landing-page" class="glass-card max-w-xl w-full p-8 md:p-10 text-center flex flex-col relative z-10 transition-opacity duration-300">
        
        <!-- অ্যানিমেটেড লোগো (আগের সাইজে এবং স্পেস সহ) -->
        <div class="logo-anim mb-10 w-28 h-28 mx-auto rounded-full bg-blue-900/40 flex items-center justify-center text-6xl border-2 border-blue-500/30 mt-4">
            🔥
        </div>
        
        <!-- Title and Subtitle with Spacing -->
        <div class="mb-12">
            <h1 class="text-4xl sm:text-5xl font-bold uppercase mb-4 tracking-tight dynamic-text-color">Glitch Master Zone</h1>
            <p id="sub-title" class="text-blue-300 font-semibold text-lg tracking-wide">সেরা গ্লিচ ও র্যাঙ্ক পুশ ট্রিকস</p>
        </div>
        
        <!-- সাবস্ক্রাইব বাটন (মাঝখানে ফাঁকা জায়গা রাখা হয়েছে) -->
        <div class="mb-10">
            <a href="https://youtube.com/@mrvryksyr?si=RbW9pbYZcZ7staG5" target="_blank" class="btn-sub block w-full py-5 text-white font-bold text-xl rounded-2xl tracking-widest shadow-xl">
                SUBSCRIBE NOW
            </a>
        </div>
        
        <!-- গাইড মেনুতে যাওয়ার বাটন -->
        <div class="mb-12">
            <button onclick="showMenu()" id="view-tips-btn" class="btn-tips block w-full py-5 rounded-2xl font-bold text-blue-100 text-xl tracking-wide">
                গ্লিচ ও ট্রিকস দেখুন 🎯
            </button>
        </div>

        <!-- আপনার ইনফরমেশন কার্ড (সুন্দরভাবে নিচে বসানো হয়েছে) -->
        <div class="text-left bg-black/40 p-6 rounded-2xl border border-gray-700/50 mt-4 shadow-inner">
            <h3 id="info-header" class="text-xl font-bold text-blue-400 mb-4 border-b border-gray-700 pb-3 flex items-center gap-3">
                👤 প্রোফাইল ইনফরমেশন
            </h3>
            <div class="space-y-4 text-base text-gray-300 mt-2">
                <div class="flex justify-between border-b border-gray-800/50 pb-2">
                    <span id="info-name-lbl" class="text-gray-400">নাম:</span>
                    <span class="font-bold text-white tracking-wide">YEADI RAJ</span>
                </div>
                <div class="flex justify-between border-b border-gray-800/50 pb-2">
                    <span id="info-yt-lbl" class="text-gray-400">ইউটিউব চ্যানেল:</span>
                    <span class="font-bold text-red-400 tracking-wide">MR VRYCKS YR</span>
                </div>
                <div class="flex justify-between">
                    <span id="info-uid-lbl" class="text-gray-400">ফ্রি ফায়ার UID:</span>
                    <span class="font-mono font-bold text-yellow-400 tracking-widest text-lg">7457579517</span>
                </div>
            </div>
        </div>
    </div>

    <!-- দ্বিতীয় স্ক্রিন: গাইড মেনু (২০টি অপশন) -->
    <div id="guide-menu" class="glass-card max-w-xl w-full p-8 md:p-10 hidden text-center flex flex-col relative z-10 transition-opacity duration-300">
        
        <h1 id="menu-header" class="text-3xl sm:text-4xl font-bold uppercase mb-10 dynamic-text-color tracking-wide">গ্লিচ গাইড মেনু</h1>
        
        <!-- স্ক্রল কন্টেইনার (প্রতিটা আইটেমের মাঝে স্পেস আছে) -->
        <div id="tricks-list" class="scroll-container overflow-y-auto pr-3 flex-grow text-left">
            <!-- জাভাস্ক্রিপ্ট দিয়ে আইটেম জেনারেট হবে -->
        </div>

        <button onclick="backToHome()" id="back-home-btn" class="mt-8 w-full py-4 rounded-xl border border-gray-600 hover:bg-gray-800 transition font-bold text-gray-300 tracking-wide">
            ← মূল পেজে ফিরে যান
        </button>
    </div>

    <!-- তৃতীয় স্ক্রিন: ট্রিকস ডিটেইলস -->
    <div id="details-view" class="glass-card max-w-xl w-full p-8 md:p-10 hidden text-left flex flex-col relative z-10 transition-opacity duration-300">
        
        <h2 id="trick-title" class="text-2xl sm:text-3xl font-bold text-blue-400 mb-8 border-b border-blue-500/30 pb-5 dynamic-text-color"></h2>
        
        <div class="bg-black/40 p-8 rounded-2xl border border-gray-700/50 mb-10 shadow-inner">
            <div id="trick-content" class="text-gray-200 space-y-6 text-lg font-medium leading-relaxed">
                <!-- কন্টেন্ট আসবে এখানে -->
            </div>
        </div>

        <button onclick="showMenu()" id="back-menu-btn" class="mt-auto w-full py-5 bg-gray-800 border border-blue-500/50 rounded-xl font-bold hover:bg-gray-700 transition text-white text-lg shadow-lg tracking-wide">
            ← মেনুতে ফিরে যান
        </button>
    </div>

    <!-- ফিডব্যাক / যোগাযোগ বাটন (ফ্লোটিং মেসেঞ্জার বাটন) -->
    <button onclick="toggleFeedbackModal()" class="fixed bottom-8 right-8 w-16 h-16 bg-blue-600 hover:bg-blue-500 text-white rounded-full flex items-center justify-center text-3xl shadow-2xl z-30 transition-transform hover:scale-110 active:scale-95">
        💬
    </button>

    <!-- ফিডব্যাক পপ-আপ ফর্ম (Modal) -->
    <div id="feedback-modal" class="fixed inset-0 bg-black/80 backdrop-blur-md z-50 flex items-center justify-center p-4 hidden transition-opacity duration-300">
        <div class="glass-card max-w-md w-full p-8 text-left relative shadow-2xl border border-blue-500/30">
            <!-- বন্ধ করার বাটন -->
            <button onclick="toggleFeedbackModal()" class="absolute top-5 right-5 text-gray-400 hover:text-white text-2xl font-bold transition-colors">✕</button>
            
            <h2 id="feed-title" class="text-2xl font-bold mb-3 text-blue-400 flex items-center gap-2">✉️ ফিডব্যাক পাঠান</h2>
            <p id="feed-desc" class="text-gray-400 text-sm mb-6 leading-relaxed">যেকোনো প্রশ্ন, মতামত বা সাহায্য পেতে সরাসরি মেসেজ পাঠান।</p>
            
            <form id="contact-form" onsubmit="handleFormSubmit(event)" class="space-y-5">
                <div>
                    <label id="feed-name-lbl" class="block text-sm font-semibold text-gray-300 mb-2">আপনার নাম</label>
                    <input type="text" id="sender-name" required class="w-full bg-slate-900 border border-gray-700 rounded-xl px-4 py-3 text-white focus:outline-none focus:border-blue-500 transition-colors shadow-inner" placeholder="যেমন: রাইহান">
                </div>
                <div>
                    <label id="feed-msg-lbl" class="block text-sm font-semibold text-gray-300 mb-2">মেসেজ / মতামত</label>
                    <textarea id="sender-msg" rows="5" required class="w-full bg-slate-900 border border-gray-700 rounded-xl px-4 py-3 text-white focus:outline-none focus:border-blue-500 transition-colors shadow-inner" placeholder="আপনার বার্তাটি এখানে লিখুন..."></textarea>
                </div>
                <button type="submit" id="feed-submit-btn" class="w-full py-4 bg-gradient-to-r from-blue-600 to-blue-500 hover:from-blue-500 hover:to-blue-400 text-white font-bold rounded-xl transition-all shadow-lg tracking-wide text-lg mt-2">
                    মেসেজ পাঠান 🚀
                </button>
            </form>
        </div>
    </div>

    <script>
        // ভাষা স্ট্যাটাস
        let currentLang = 'BN';

        // ভাষা ডিকশনারি
        const translations = {
            BN: {
                subTitle: "সেরা গ্লিচ ও র্যাঙ্ক পুশ ট্রিকস",
                viewTips: "গ্লিচ ও ট্রিকস দেখুন 🎯",
                infoHeader: "👤 প্রোফাইল ইনফরমেশন",
                infoName: "নাম:",
                infoYt: "ইউটিউব চ্যানেল:",
                infoUid: "ফ্রি ফায়ার UID:",
                menuHeader: "গ্লিচ গাইড মেনু",
                backHome: "← মূল পেজে ফিরে যান",
                backMenu: "← মেনুতে ফিরে যান",
                feedTitle: "✉️ ফিডব্যাক পাঠান",
                feedDesc: "যেকোনো প্রশ্ন, মতামত বা সাহায্য পেতে সরাসরি মেসেজ পাঠান।",
                feedName: "আপনার নাম",
                feedMsg: "মেসেজ / মতামত",
                feedSubmit: "মেসেজ পাঠান 🚀",
                placeholderName: "যেমন: রাইহান",
                placeholderMsg: "আপনার বার্তাটি এখানে লিখুন..."
            },
            EN: {
                subTitle: "Best Glitches & Rank Push Tricks",
                viewTips: "View Glitches & Tricks 🎯",
                infoHeader: "👤 Profile Information",
                infoName: "Name:",
                infoYt: "YouTube Channel:",
                infoUid: "Free Fire UID:",
                menuHeader: "Glitch Guide Menu",
                backHome: "← Back to Home Page",
                backMenu: "← Back to Menu",
                feedTitle: "✉️ Send Feedback",
                feedDesc: "Send a direct message for any query, feedback, or support.",
                feedName: "Your Name",
                feedMsg: "Message / Feedback",
                feedSubmit: "Send Message 🚀",
                placeholderName: "e.g., Raihan",
                placeholderMsg: "Write your message here..."
            }
        };

        // ডেটাবেস
        const tricksData = [
            { id: 1, icon: "🕴️", titleBN: "স্যান্টিনো টেলিপোর্ট গ্লিচ", contentBN: "১. প্রথমে আপনার স্যান্টিনো স্কিলটি চালু করুন।<br><br>২. পুতুলটি এমন জায়গায় রাখুন যা দেয়ালের ওপারে বা কাভারের পেছনে থাকে।<br><br>৩. এনিমি যখন আপনার দিকে রাশ করবে, তখন আবার ক্লিক করে টেলিপোর্ট হয়ে পেছনে এসে হেডশট দিন।", titleEN: "Santino Teleport Glitch", contentEN: "1. First, activate your Santino character skill.<br><br>2. Place the mannequin behind a wall or cover.<br><br>3. When an enemy rushes towards you, teleport back instantly to spawn behind them and take an easy headshot." },
            { id: 2, icon: "🧱", titleBN: "ওয়াল হাইড গ্লিচ", contentBN: "১. একটি নির্দিষ্ট দেয়াল বা কন্টেইনারের সামনে যান।<br><br>২. আপনার ইন্টারনেট কানেকশন অফ করে দিন (999+ হওয়া পর্যন্ত)।<br><br>৩. দেয়ালের ভেতর দৌড়ান, এরপর আবার নেট অন করুন। আপনি দেয়ালের ভেতর ঢুকে যাবেন।", titleEN: "Wall Hide Glitch", contentEN: "1. Stand directly in front of a specific wall or container.<br><br>2. Turn off your internet connection and wait for your ping to hit 999+.<br><br>3. Run straight into the wall, then turn on your internet. You will glitch inside the wall." },
            { id: 3, icon: "🏆", titleBN: "র্যাঙ্ক পুশ স্ট্র্যাটেজি", contentBN: "১. সব সময় ফ্লাইট পাথ থেকে দূরে এবং ব্লু-জোন এড়িয়ে নামুন।<br><br>২. ভালো ক্যারেক্টার কম্বো (অ্যালোক + কেলি + মিশা) ব্যবহার করুন।<br><br>৩. শেষ জোনের আগে কোনো অপ্রয়োজনীয় ফাইট নেবেন না, পজিশন হোল্ড করে সারভাইভ করুন।", titleEN: "Rank Push Strategy", contentEN: "1. Always land far away from the flight path and avoid blue zones.<br><br>2. Equip a solid character combo like Alok + Kelly + Misha.<br><br>3. Avoid taking unnecessary early-game fights, focus entirely on survival and holding position." },
            { id: 4, icon: "🚗", titleBN: "মিশা কার ট্রিক", contentBN: "১. মিশা ক্যারেক্টার স্কিল নিয়ে গেমে ঢুকুন।<br><br>২. সব সময় একটি গাড়ি বা বাইক নিজের কাছে রাখুন।<br><br>৩. এনিমি ফায়ার করলে গাড়িতে থাকলে ড্যামেজ কম লাগবে এবং সহজে রোটেশন দেওয়া যাবে।", titleEN: "Misha Car Trick", contentEN: "1. Enter the game with Misha character skill equipped.<br><br>2. Keep a car or motorcycle nearby at all times.<br><br>3. While driving, enemies will find it very hard to auto-aim or damage you, allowing easy rotation." },
            { id: 5, icon: "🎯", titleBN: "ডাবল স্নাইপার ফাস্ট রিলোড", contentBN: "১. সেটিংসে গিয়ে 'Quick Weapon Switch' অন করুন।<br><br>২. একটি স্নাইপার দিয়ে ফায়ার করার সাথে সাথেই সুইচ বাটনে ক্লিক করুন।<br><br>৩. এতে কোনো রিলোড অ্যানিমেশন ছাড়াই দ্রুত ডাবল স্নাইপার চালাতে পারবেন।", titleEN: "Double Sniper Fast Reload", contentEN: "1. Go to game settings and enable 'Quick Weapon Switch'.<br><br>2. Immediately after firing your first sniper, tap the quick switch button.<br><br>3. This cancels the reload animation, letting you shoot continuously." },
            { id: 6, icon: "💣", titleBN: "ইনভিজিবল গ্রেনেড থ্রো", contentBN: "১. গ্রেনেড হাতে নিয়ে কুক (cook) করা শুরু করুন।<br><br>২. থ্রো করার ঠিক ১ সেকেন্ড আগে গ্লু ওয়াল বাটনে চাপ দিন।<br><br>৩. এনিমি গ্রেনেড আসার কোনো সতর্কবার্তা বা শব্দ পাবে না।", titleEN: "Invisible Grenade Throw", contentEN: "1. Take a grenade in hand and start cooking it.<br><br>2. Exactly 1 second before throwing, tap the Gloo Wall button quickly.<br><br>3. The grenade will fly silently without showing any indicator to the enemy." },
            { id: 7, icon: "🚡", titleBN: "জিপলাইন হাইড ট্রিক", contentBN: "১. জিপলাইনের একদম কাছে গিয়ে দাঁড়ান।<br><br>২. 'Use' বাটনে ক্লিক করার সাথে সাথে ইন্টারনেট অফ করে দিন।<br><br>৩. এনিমি আপনাকে দেখতে পাবে না, কিন্তু আপনি সব দেখতে পারবেন (ক্লাসিক মোডের জন্য)।", titleEN: "Zipline Hide Trick", contentEN: "1. Move extremely close to any zipline.<br><br>2. Tap the 'Use' button and instantly turn off your internet.<br><br>3. You will glide invisibly across the map. Great for fun or scoping out enemies." },
            { id: 8, icon: "🦸‍♂️", titleBN: "বেস্ট ক্যারেক্টার কম্বো", contentBN: "১. অ্যাক্টিভ স্কিল: অরিয়ন (Orion) বা কে (K)।<br><br>২. প্যাসিভ স্কিল ১: মিগুয়েল (EP গেইন করার জন্য)।<br><br>৩. প্যাসিভ স্কিল ২: জেই (J.Biebs) ড্যামেজ ব্লক করার জন্য।<br><br>৪. প্যাসিভ স্কিল ৩: কেলি বা সোনিয়া।", titleEN: "Best Character Combo", contentEN: "1. Active Skill: Orion or K.<br><br>2. Passive 1: Miguel (generates instant EP on knocks).<br><br>3. Passive 2: J.Biebs (blocks incoming damage using EP).<br><br>4. Passive 3: Kelly for speed or Sonia." },
            { id: 9, icon: "🗼", titleBN: "টাওয়ার ক্যাম্পিং ট্রিক", contentBN: "১. টাওয়ারের একদম উপরের সিড়িতে ল্যান্ডমাইন বসান।<br><br>২. শুয়ে পড়ে পজিশন নিন যাতে নিচ থেকে কেউ না দেখে।<br><br>৩. কেউ উপরে ওঠার চেষ্টা করলে ল্যান্ডমাইনে ড্যামেজ খাবে, তখন সহজেই ফিনিশ করুন।", titleEN: "Tower Camping Trick", contentEN: "1. Place a landmine right at the top steps of a watchtower.<br><br>2. Prone down completely so you cannot be spotted from below.<br><br>3. Anyone trying to climb up will trigger the mine, letting you finish them off." },
            { id: 10, icon: "👣", titleBN: "সাইলেন্ট মুভমেন্ট", contentBN: "১. হাঁটার সময় মেডিকেট বাটন বারবার ট্যাপ করুন।<br><br>২. অথবা স্কোপ ইন এবং আউট করে হাঁটুন।<br><br>৩. এতে আপনার পায়ের কোনো শব্দ এনিমির কাছে পৌঁছাবে না।", titleEN: "Silent Movement", contentEN: "1. Tap the Medkit button rapidly while walking.<br><br>2. Alternatively, repeatedly scope in and out while moving forward.<br><br>3. This silences your footsteps, making you completely quiet on the radar." },
            { id: 11, icon: "🐶", titleBN: "সঠিক পেট নির্বাচন", contentBN: "১. রাশ গেমপ্লে: 'Rockie' (অ্যাক্টিভ স্কিল কুলডাউন কমায়) বা 'Mr. Waggor' (গ্লু ওয়াল দেয়)।<br><br>২. স্নাইপিং: 'Beaston' (গ্রেনেড/গ্লু ওয়াল অনেক দূরে ফেলা যায়)।", titleEN: "Proper Pet Selection", contentEN: "1. For rush gameplay: Select 'Rockie' to reduce active skill cooldown or 'Mr. Waggor' for Gloo Walls.<br><br>2. For Sniping/Support: Use 'Beaston' to throw utilities much further." },
            { id: 12, icon: "💥", titleBN: "পারফেক্ট ল্যান্ডমাইন ট্রিক", contentBN: "১. এয়ারড্রপের ঠিক নিচে বা ভেন্ডিং মেশিনের সামনে ল্যান্ডমাইন বসান।<br><br>২. ল্যান্ডমাইনের উপর একটি মেডিকেট ড্রপ করে দিন।<br><br>৩. মেডিকেট দেখে এনিমি লোভে পড়ে আসলে ল্যান্ডমাইনে কিল হবে।", titleEN: "Perfect Landmine Trap", contentEN: "1. Plant a landmine directly beneath an airdrop or in front of a vending machine.<br><br>2. Drop a Medkit right on top of the hidden mine.<br><br>3. Greedy enemies rushing for the loot will detonate the mine instantly." },
            { id: 13, icon: "⚡", titleBN: "ফ্লাশ ব্যাং ম্যাজিক", contentBN: "১. রাশ করার আগে এনিমির কাভারের পেছনে ফ্লাশ ব্যাং কুক করে ছুঁড়ে দিন।<br><br>২. এনিমি ২-৩ সেকেন্ডের জন্য ব্লাইন্ড হয়ে যাবে।<br><br>৩. ওই সুযোগে দ্রুত রাশ করে কিল কনফার্ম করুন।", titleEN: "Flashbang Magic", contentEN: "1. Before rushing a house or cover, cook a flashbang and throw it.<br><br>2. The target will be blinded for 2-3 seconds.<br><br>3. Push immediately while they are blind to secure an easy kill." },
            { id: 14, icon: "🗺️", titleBN: "সেফ জোন প্রেডিকশন", contentBN: "১. ম্যাপের 'Info Tool' (জোন প্রেডিক্টর) রাডারের সাহায্যে স্ক্যান করুন।<br><br>২. আগে থেকেই পরবর্তী জোনের মাঝামাঝি বা উঁচুতে পজিশন নিয়ে রাখুন।<br><br>৩. জোন আসার সময় এনিমিরা যখন দৌড়াবে, তখন সহজেই কিল পাবেন।", titleEN: "Safe Zone Prediction", contentEN: "1. Locate and use the 'Info Tool' radar machine on the map.<br><br>2. Move early and capture a high-ground position inside the predicted zone.<br><br>3. Gatekeep enemies rushing inside late to grab easy kills." },
            { id: 15, icon: "🪂", titleBN: "লঞ্চপ্যাড ফ্লাইং গ্লিচ", contentBN: "১. লঞ্চপ্যাডে উঠে টার্গেটটি একদম খাড়া উপরের দিকে সেট করুন।<br><br>২. ইউজ করার সাথে সাথে স্কেটবোর্ড বাটন চাপুন।<br><br>৩. অনেক উপরে উড়ে গিয়ে গাছের ডালে বা ফ্যাক্টরির ছাদে নামতে পারবেন।", titleEN: "Launchpad Flying Glitch", contentEN: "1. Climb onto a launchpad and aim the trajectory directly upwards.<br><br>2. Tap the launch button and immediately trigger your pocket skateboard.<br><br>3. You will fly incredibly high to land safely on factory roofs or tall trees." },
            { id: 16, icon: "🔫", titleBN: "শর্ট রেঞ্জ হেডশট ট্রিক", contentBN: "১. ফায়ার বাটনটি একটু নিচে নামিয়ে রাখুন।<br><br>২. এনিমি সামনে আসলে ফায়ার বাটনটিকে দ্রুত 'J' শেপে উপরের দিকে ড্র্যাগ করুন।<br><br>৩. এতে রিকয়েল কম হবে এবং ডাইরেক্ট হেডশট লাগবে।", titleEN: "Short Range Headshot", contentEN: "1. Reposition your fire button slightly lower on your HUD.<br><br>2. Drag the fire button quickly in a 'J' shape upward towards the enemy.<br><br>3. This keeps crosshair lock steady and delivers a clean, instant headshot." },
            { id: 17, icon: "⛺", titleBN: "রিভাইভ পয়েন্ট ডিফেন্স", contentBN: "১. রিভাইভ দেওয়ার সময় চারদিকে গ্লু ওয়াল দিয়ে প্যাক করুন।<br><br>২. হোমার (Homer) ক্যারেক্টার স্কিল ইউজ করুন, যাতে এনিমি রাশ করলে স্লো হয়ে যায়।<br><br>৩. ডিমিত্রি (Dimitri) অন করে রাখলে কেউ নক হলেও অটো রিভাইভ হবে।", titleEN: "Revive Point Defense", contentEN: "1. Create a 360-degree Gloo Wall shield before reviving teammates.<br><br>2. Deploy a Homer drone to scan and slow down any incoming rushers.<br><br>3. Activate Dimitri's healing zone so downed allies revive automatically." },
            { id: 18, icon: "🏊‍♂️", titleBN: "পানিতে দ্রুত পালানোর ট্রিক", contentBN: "১. কেলি ক্যারেক্টার সাথে রাখুন।<br><br>২. পানিতে লাফ দেওয়ার সাথে সাথে বারবার জাম্প বাটন এবং মিলি (Melee) উইপন সুইচ করুন।<br><br>৩. সাধারণ সাঁতারের চেয়ে অনেক দ্রুত পানি পার হতে পারবেন।", titleEN: "Fast Water Crossing", contentEN: "1. Equip Kelly character in your passive skill slot.<br><br>2. As soon as you jump into the water, spam the jump button while rapidly switching to your melee weapon.<br><br>3. You will swim significantly faster than normal." },
            { id: 19, icon: "🛡️", titleBN: "360° গ্লু ওয়াল ট্রিক", contentBN: "১. সেন্সিটিভিটি (General) ১০০ তে রাখুন।<br><br>২. ফায়ার করে বসার (Crouch) সাথে সাথে স্ক্রিন ডান বা বাম দিকে ঘুরিয়ে গ্লু ওয়াল বাটনে চাপুন।<br><br>৩. এক সেকেন্ডেরও কম সময়ে চারদিকে ওয়াল প্যাক হয়ে যাবে।", titleEN: "360-Degree Gloo Wall", contentEN: "1. Keep your general sensitivity slider set to exactly 100.<br><br>2. Immediately after shooting, crouch down and flick your screen while double-tapping the Gloo Wall.<br><br>3. This encloses you in a protective shell in a split second." },
            { id: 20, icon: "🔥", titleBN: "লাস্ট জোন সারভাইভাল", contentBN: "১. শেষ জোনে পর্যাপ্ত মেডিকেট এবং ইনহেলার রাখুন।<br><br>২. সুপার মেডিকেট (Super Medkit) থাকলে জোনের বাইরে থেকেও হিল ব্যাটেলে জেতা সম্ভব।<br><br>৩. কে (K) ক্যারেক্টার এবং ম্যাক্সিম (Maxim) থাকলে আপনি জোন ড্যামেজকে হার মানাতে পারবেন।", titleEN: "Last Zone Heal Battle", contentEN: "1. Stock up on maximum possible Medkits and Inhalers for the final circles.<br><br>2. Always keep a Super Medkit saved for healing outside the zone damage.<br><br>3. Pair Maxim and K characters together to out-heal any zone intensity." }
        ];

        // ভাষা পরিবর্তন করার ফাংশন
        function toggleLanguage() {
            if (currentLang === 'BN') {
                currentLang = 'EN';
                document.getElementById('lang-text').innerText = 'বাংলা';
            } else {
                currentLang = 'BN';
                document.getElementById('lang-text').innerText = 'English';
            }
            applyLanguage();
        }

        function applyLanguage() {
            const data = translations[currentLang];
            
            document.getElementById('sub-title').innerHTML = data.subTitle;
            document.getElementById('view-tips-btn').innerHTML = data.viewTips;
            
            document.getElementById('info-header').innerHTML = data.infoHeader;
            document.getElementById('info-name-lbl').innerText = data.infoName;
            document.getElementById('info-yt-lbl').innerText = data.infoYt;
            document.getElementById('info-uid-lbl').innerText = data.infoUid;
            
            document.getElementById('menu-header').innerText = data.menuHeader;
            document.getElementById('back-home-btn').innerText = data.backHome;
            document.getElementById('back-menu-btn').innerText = data.backMenu;

            document.getElementById('feed-title').innerText = data.feedTitle;
            document.getElementById('feed-desc').innerText = data.feedDesc;
            document.getElementById('feed-name-lbl').innerText = data.feedName;
            document.getElementById('feed-msg-lbl').innerText = data.feedMsg;
            document.getElementById('feed-submit-btn').innerText = data.feedSubmit;
            document.getElementById('sender-name').placeholder = data.placeholderName;
            document.getElementById('sender-msg').placeholder = data.placeholderMsg;
            
            if (!document.getElementById('guide-menu').classList.contains('hidden')) {
                renderMenu();
            }
        }

        // ২০টি ট্রিকস রেন্ডার করার ফাংশন (স্পেস সহ)
        function renderMenu() {
            const tricksList = document.getElementById('tricks-list');
            tricksList.innerHTML = '';
            
            tricksData.forEach(trick => {
                const btn = document.createElement('button');
                btn.className = 'btn-menu-item w-full py-5 px-6 rounded-2xl font-bold text-lg text-blue-200 flex items-center gap-4';
                btn.onclick = () => showDetail(trick.id);
                
                const titleText = currentLang === 'BN' ? trick.titleBN : trick.titleEN;
                btn.innerHTML = `<span class="text-3xl">${trick.icon}</span> <span class="text-left">${trick.id}. ${titleText}</span>`;
                tricksList.appendChild(btn);
            });
        }

        function showMenu() {
            document.getElementById('landing-page').classList.add('hidden');
            document.getElementById('details-view').classList.add('hidden');
            document.getElementById('guide-menu').classList.remove('hidden');
            renderMenu();
        }

        function showDetail(id) {
            const trick = tricksData.find(t => t.id === id);
            document.getElementById('guide-menu').classList.add('hidden');
            
            const titleText = currentLang === 'BN' ? trick.titleBN : trick.titleEN;
            const contentText = currentLang === 'BN' ? trick.contentBN : trick.contentEN;

            document.getElementById('trick-title').innerHTML = `${trick.icon} ${titleText}`;
            document.getElementById('trick-content').innerHTML = contentText;
            document.getElementById('details-view').classList.remove('hidden');
        }

        function backToHome() {
            document.getElementById('guide-menu').classList.add('hidden');
            document.getElementById('landing-page').classList.remove('hidden');
        }

        // ফিডব্যাক ফর্ম খোলা এবং বন্ধ করা
        function toggleFeedbackModal() {
            const modal = document.getElementById('feedback-modal');
            modal.classList.toggle('hidden');
        }

        // ফিডব্যাক সাবমিট
        function handleFormSubmit(event) {
            event.preventDefault();
            const name = document.getElementById('sender-name').value;
            const message = document.getElementById('sender-msg').value;
            
            const subject = encodeURIComponent(`Feedback from Glitch Master Zone - ${name}`);
            const body = encodeURIComponent(`Hi Yeadi Raj,\n\nMy Name: ${name}\n\nMessage:\n${message}`);
            
            window.location.href = `mailto:mryeadiraj@gmail.com?subject=${subject}&body=${body}`;
            
            document.getElementById('contact-form').reset();
            toggleFeedbackModal();
        }

        window.onload = function() {
            applyLanguage();
        };
    </script>
</body>
</html>


```
