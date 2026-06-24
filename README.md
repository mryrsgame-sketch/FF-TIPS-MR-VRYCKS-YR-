# FF-TIPS-MR-VRYCKS-YR-
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>প্রো গেমার গ্লিচ জোন</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Rajdhani:wght@600;700&family=Hind+Siliguri:wght@400;600&display=swap');
        body { font-family: 'Hind Siliguri', sans-serif; background: #0f172a; color: white; }
        h1, h2, .gaming-font { font-family: 'Rajdhani', sans-serif; }
        
        .glass-card { background: rgba(30, 41, 59, 0.7); backdrop-filter: blur(20px); border: 1px solid rgba(255, 255, 255, 0.1); border-radius: 40px; box-shadow: 0 20px 50px rgba(0,0,0,0.5); }
        .btn-main { background: linear-gradient(90deg, #2563eb, #7c3aed); box-shadow: 0 0 25px rgba(37, 99, 235, 0.6); transition: 0.3s; }
        .btn-main:hover { transform: scale(1.03); box-shadow: 0 0 40px rgba(37, 99, 235, 0.9); }
        .btn-menu { background: rgba(255,255,255,0.05); border: 1px solid #3b82f6; transition: 0.3s; }
        .btn-menu:hover { background: #3b82f6; }
    </style>
</head>
<body class="p-6 flex items-center justify-center min-h-screen">

    <!-- প্রথম স্ক্রিন: ল্যান্ডিং পেজ -->
    <div id="landing-page" class="glass-card max-w-lg w-full p-10 text-center">
        <div class="mb-8 w-24 h-24 mx-auto rounded-full bg-blue-500/20 flex items-center justify-center text-5xl">🔥</div>
        <h1 class="text-5xl font-bold uppercase mb-4 tracking-tighter">Glitch Master Zone</h1>
        <p class="text-blue-400 mb-8 font-semibold">স্যান্টিনো গ্লিচ ও র‍্যাঙ্ক পুশ ট্রিকস</p>
        
        <!-- আপনার ইউটিউব লিংক এখানে সেট করা হয়েছে -->
        <a href="https://youtube.com/@mrvryksyr?si=RbW9pbYZcZ7staG5" target="_blank" class="btn-main block w-full py-5 text-white font-bold text-xl rounded-2xl mb-6 uppercase">
            সাবস্ক্রাইব করুন
        </a>
        
        <!-- গাইড মেনুতে যাওয়ার বাটন -->
        <button onclick="showMenu()" class="block w-full py-4 border border-blue-500/50 rounded-2xl font-bold hover:bg-blue-500/20 transition">
            গ্লিচ ও ট্রিকস দেখুন ⚔️
        </button>
    </div>

    <!-- দ্বিতীয় স্ক্রিন: গাইড মেনু -->
    <div id="guide-menu" class="glass-card max-w-lg w-full p-10 hidden text-center">
        <h1 class="text-4xl font-bold uppercase mb-8">গ্লিচ গাইড মেনু</h1>
        <div class="space-y-4">
            <button onclick="showDetail(1)" class="btn-menu w-full py-4 rounded-xl font-bold text-lg">১. স্যান্টিনো টেলিপোর্ট গ্লিচ</button>
            <button onclick="showDetail(2)" class="btn-menu w-full py-4 rounded-xl font-bold text-lg">২. ওয়াল হাইড গ্লিচ</button>
            <button onclick="showDetail(3)" class="btn-menu w-full py-4 rounded-xl font-bold text-lg">৩. র‍্যাঙ্ক পুশ স্ট্র্যাটেজি</button>
        </div>
        <button onclick="backToHome()" class="mt-8 w-full py-3 text-gray-400 hover:text-white transition">← মূল পেজে ফিরে যান</button>
    </div>

    <!-- তৃতীয় স্ক্রিন: ট্রিকস ডিটেইলস -->
    <div id="details-view" class="glass-card max-w-lg w-full p-10 hidden text-left">
        <h2 id="trick-title" class="text-3xl font-bold text-blue-400 mb-6 text-center gaming-font"></h2>
        <div id="trick-content" class="text-gray-300 space-y-4 mb-8"></div>
        <button onclick="showMenu()" class="w-full py-4 bg-red-600 rounded-xl font-bold hover:bg-red-700 transition">ফিরে যান (Back)</button>
    </div>

    <script>
        const tricks = {
            1: { title: "স্যান্টিনো টেলিপোর্ট গ্লিচ", content: "১. প্রথমে আপনার স্যান্টিনো স্কিলটি চালু করুন।<br>২. পুতুলটি এমন জায়গায় রাখুন যা দেয়ালের ওপারে।<br>৩. এনিমি যখন পুতুলের দিকে ফোকাস করবে, তখন আবার ক্লিক করে টেলিপোর্ট হয়ে পেছনে এসে হেডশট দিন।" },
            2: { title: "ওয়াল হাইড গ্লিচ", content: "১. একটি নির্দিষ্ট দেয়ালের সামনে যান।<br>২. জাম্প এবং গ্লু ওয়াল বাটন একসাথে চাপুন।<br>৩. আপনার ক্যারেক্টারটি দেয়ালের ভেতরে ঢুকে যাবে যা এনিমি দেখতে পাবে না।" },
            3: { title: "র‍্যাঙ্ক পুশ স্ট্র্যাটেজি", content: "১. সব সময় ব্লু-জোন থেকে দূরে নামুন।<br>২. ভালো ক্যারেক্টার কম্বো (অ্যালোক + কেলি) ব্যবহার করুন।<br>৩. শেষ জোনের আগে কোনো ফাইট নেবেন না, সারভাইভ করুন।" }
        };

        function showMenu() {
            document.getElementById('landing-page').classList.add('hidden');
            document.getElementById('details-view').classList.add('hidden');
            document.getElementById('guide-menu').classList.remove('hidden');
        }

        function showDetail(id) {
            document.getElementById('guide-menu').classList.add('hidden');
            document.getElementById('trick-title').innerText = tricks[id].title;
            document.getElementById('trick-content').innerHTML = tricks[id].content;
            document.getElementById('details-view').classList.remove('hidden');
        }

        function backToHome() {
            document.getElementById('guide-menu').classList.add('hidden');
            document.getElementById('landing-page').classList.remove('hidden');
        }
    </script>
</body>
</html>
