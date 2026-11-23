<!DOCTYPE html>
<html lang="uz" class="dark theme-amoled">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <meta name="theme-color" content="#000000">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <title>UzGram — Do'stlar Ijtimoiy Tarmog'i va Messenjer</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        /* ==================== THEME TOKENS (GALICHKA VIP PERKS) ==================== */
        :root {
            --bg-outer: #050505;
            --bg-shell: #000000;
            --bg-card: #121212;
            --bg-elevated: #1a1a1a;
            --border-color: #1f1f1f;
            --text-primary: #ffffff;
            --text-secondary: #9ca3af;
            --accent-color: #0095F6;
        }
        html.theme-amoled {
            --bg-outer: #000000;
            --bg-shell: #000000;
            --bg-card: #0c0c0c;
            --bg-elevated: #151515;
            --border-color: #1a1a1a;
            --text-primary: #ffffff;
            --text-secondary: #9ca3af;
            --accent-color: #0095F6;
        }
        html.theme-midnight {
            --bg-outer: #040914;
            --bg-shell: #071022;
            --bg-card: #0e1a33;
            --bg-elevated: #152547;
            --border-color: #1f335c;
            --text-primary: #f8fafc;
            --text-secondary: #94a3b8;
            --accent-color: #38bdf8;
        }
        html.theme-gold {
            --bg-outer: #090704;
            --bg-shell: #0f0b05;
            --bg-card: #191309;
            --bg-elevated: #241b0d;
            --border-color: #3b2c14;
            --text-primary: #fefce8;
            --text-secondary: #d6c59c;
            --accent-color: #f59e0b;
        }
        html.theme-light {
            --bg-outer: #f1f5f9;
            --bg-shell: #ffffff;
            --bg-card: #f8fafc;
            --bg-elevated: #e2e8f0;
            --border-color: #e2e8f0;
            --text-primary: #0f172a;
            --text-secondary: #475569;
            --accent-color: #0095F6;
        }

        * {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            -webkit-tap-highlight-color: transparent;
            box-sizing: border-box;
        }
        body {
            background-color: var(--bg-outer);
            color: var(--text-primary);
            margin: 0;
            padding: 0;
            overflow-x: hidden;
            transition: background-color 0.25s ease, color 0.25s ease;
        }
        .app-shell {
            max-width: 460px;
            margin: 0 auto;
            min-height: 100vh;
            background-color: var(--bg-shell);
            border-left: 1px solid var(--border-color);
            border-right: 1px solid var(--border-color);
            position: relative;
            display: flex;
            flex-direction: column;
            transition: background-color 0.25s ease;
        }
        @media (max-width: 460px) {
            .app-shell {
                border: none;
                max-width: 100%;
            }
        }
        html.theme-light .app-shell,
        html.theme-light #top-header,
        html.theme-light nav,
        html.theme-light #auth-screen,
        html.theme-light #user-profile-modal,
        html.theme-light #messenger-modal,
        html.theme-light #settings-activity-modal {
            background-color: #ffffff !important;
            color: #0f172a !important;
            border-color: #e2e8f0 !important;
        }
        html.theme-light .text-white {
            color: #0f172a !important;
        }
        html.theme-light .bg-\[\#121212\],
        html.theme-light .bg-\[\#111\],
        html.theme-light .bg-\[\#161616\],
        html.theme-light .bg-\[\#171717\],
        html.theme-light .bg-\[\#181818\],
        html.theme-light .bg-\[\#1c1c1c\] {
            background-color: #f1f5f9 !important;
            border-color: #cbd5e1 !important;
            color: #0f172a !important;
        }

        .story-ring {
            background: linear-gradient(45deg, #f09433 0%, #e6683c 25%, #dc2743 50%, #cc2366 75%, #bc1888 100%);
            padding: 2.5px;
            border-radius: 9999px;
        }
        .vip-avatar-ring {
            background: conic-gradient(from 0deg, #0095F6, #a855f7, #f59e0b, #ec4899, #0095F6);
            padding: 3px;
            border-radius: 9999px;
            animation: vipRingRotate 5s linear infinite;
        }
        @keyframes vipRingRotate {
            to { transform: rotate(360deg); }
        }
        .ig-gradient-btn {
            background: linear-gradient(90deg, #833ab4, #fd1d1d, #fcb045);
        }
        .ig-blue-btn {
            background-color: #0095F6;
        }
        .ig-blue-btn:hover {
            background-color: #1877F2;
        }
        .no-scrollbar::-webkit-scrollbar {
            display: none;
        }
        .no-scrollbar {
            -ms-overflow-style: none;
            scrollbar-width: none;
        }

        @keyframes heartBurst {
            0% { transform: scale(0); opacity: 0; }
            30% { transform: scale(1.3); opacity: 1; }
            70% { transform: scale(1); opacity: 1; }
            100% { transform: scale(1.1); opacity: 0; }
        }
        .animate-heart-burst {
            animation: heartBurst 0.8s ease-out forwards;
        }

        .reels-container {
            scroll-snap-type: y mandatory;
            overflow-y: scroll;
            height: calc(100vh - 112px);
        }
        .reel-item {
            scroll-snap-align: start;
            height: calc(100vh - 112px);
        }

        .ig-verified-badge {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            vertical-align: -0.14em;
            flex-shrink: 0;
        }

        /* ==================== 50 ANIMATED STICKER KEYFRAMES ==================== */
        @keyframes monkeyWave {
            0%, 100% { transform: rotate(0deg) scale(1); }
            20% { transform: rotate(-14deg) scale(1.08); }
            40% { transform: rotate(14deg) scale(1.1); }
            60% { transform: rotate(-10deg) scale(1.06); }
            80% { transform: rotate(10deg) scale(1.04); }
        }
        @keyframes monkeyWinkBounce {
            0%, 100% { transform: translateY(0) scale(1); }
            35% { transform: translateY(-7px) scale(1.14) rotate(-5deg); }
            70% { transform: translateY(-2px) scale(1.04) rotate(4deg); }
        }
        @keyframes monkeyHeartBlow {
            0%, 100% { transform: scale(1); filter: drop-shadow(0 0 4px rgba(244,63,94,0.4)); }
            50% { transform: scale(1.16) translateY(-4px); filter: drop-shadow(0 0 12px rgba(244,63,94,0.85)); }
        }
        @keyframes monkeyLaughShake {
            0%, 100% { transform: translateX(0) rotate(0deg); }
            20% { transform: translateX(-4px) rotate(-6deg) scale(1.08); }
            40% { transform: translateX(4px) rotate(6deg) scale(1.1); }
            60% { transform: translateX(-3px) rotate(-4deg) scale(1.06); }
            80% { transform: translateX(3px) rotate(4deg) scale(1.04); }
        }
        @keyframes stickerFloatBounce {
            0%, 100% { transform: translateY(0) scale(1) rotate(0deg); }
            25% { transform: translateY(-6px) scale(1.08) rotate(-4deg); }
            50% { transform: translateY(0) scale(0.98) rotate(3deg); }
            75% { transform: translateY(-3px) scale(1.05) rotate(-2deg); }
        }
        @keyframes stickerSpinPulse {
            0%, 100% { transform: scale(1) rotate(0deg); filter: drop-shadow(0 0 6px rgba(0,149,246,0.45)); }
            50% { transform: scale(1.14) rotate(8deg); filter: drop-shadow(0 0 14px rgba(253,29,29,0.6)); }
        }
        @keyframes callRingPulse {
            0% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(0, 149, 246, 0.55); }
            70% { transform: scale(1.04); box-shadow: 0 0 0 18px rgba(0, 149, 246, 0); }
            100% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(0, 149, 246, 0); }
        }
        .anim-monkey-wave { display: inline-flex; animation: monkeyWave 1.8s ease-in-out infinite; }
        .anim-monkey-wink { display: inline-flex; animation: monkeyWinkBounce 1.7s ease-in-out infinite; }
        .anim-monkey-heart { display: inline-flex; animation: monkeyHeartBlow 1.5s ease-in-out infinite; }
        .anim-monkey-laugh { display: inline-flex; animation: monkeyLaughShake 1.4s ease-in-out infinite; }
        .anim-sticker-bounce { display: inline-flex; animation: stickerFloatBounce 2.0s ease-in-out infinite; }
        .anim-sticker-pulse { display: inline-flex; animation: stickerSpinPulse 2.2s ease-in-out infinite; }
        .call-ring-pulse { animation: callRingPulse 1.7s infinite; }
    </style>
</head>
<body>

<div class="app-shell" id="app">
    <!-- Toast Notification Banner -->
    <div id="toast-container" class="fixed top-4 left-1/2 -translate-x-1/2 z-[110] w-[92%] max-w-[410px] pointer-events-none flex flex-col gap-2"></div>

    <!-- ==================== 1. AUTHENTICATION SCREEN (ONLY SHOWN IF NOT LOGGED IN OR AFTER EXPLICIT LOGOUT) ==================== -->
    <div id="auth-screen" class="hidden flex-1 flex flex-col justify-center px-6 py-8 bg-black min-h-screen">
        <div class="text-center mb-7">
            <div class="inline-flex items-center justify-center w-16 h-16 rounded-2xl ig-gradient-btn mb-4 shadow-lg shadow-pink-500/20">
                <i class="fa-brands fa-instagram text-3xl text-white"></i>
            </div>
            <h1 class="text-3xl font-extrabold tracking-tight bg-gradient-to-r from-white via-gray-200 to-gray-400 bg-clip-text text-transparent">UzGram</h1>
            <p class="text-xs text-gray-400 mt-1">O'zbekistonning do'stlar ijtimoiy tarmog'i va messenjeri</p>
        </div>

        <!-- Auth Mode Switcher -->
        <div class="flex bg-[#121212] p-1 rounded-xl mb-5 border border-[#262626]">
            <button id="tab-login" type="button" onclick="switchAuthMode('login')" class="flex-1 py-2.5 text-sm font-semibold rounded-lg bg-[#262626] text-white transition">Kirish</button>
            <button id="tab-register" type="button" onclick="switchAuthMode('register')" class="flex-1 py-2.5 text-sm font-semibold rounded-lg text-gray-400 hover:text-white transition">Ro'yxatdan o'tish</button>
        </div>

        <!-- Saved Accounts Quick One-Tap Switcher (for accounts previously created on this device) -->
        <div id="saved-accounts-box" class="hidden mb-5 bg-[#121212] border border-[#262626] rounded-2xl p-3">
            <div class="text-[11px] font-semibold text-gray-400 mb-2">Saqlangan akkauntlar (bir bosishda kirish):</div>
            <div id="saved-accounts-list" class="space-y-1.5"></div>
        </div>

        <!-- Login Form -->
        <form id="login-form" onsubmit="handleLogin(event)" class="space-y-3.5">
            <div>
                <label class="block text-xs text-gray-400 mb-1.5">Email, Telefon raqam yoki @Nik</label>
                <input type="text" id="login-identifier" required placeholder="xxkordinalxx@gmail.com yoki @kamakot"
                    class="w-full bg-[#121212] border border-[#262626] focus:border-[#0095F6] rounded-xl px-4 py-3 text-sm text-white outline-none transition">
            </div>
            <div>
                <label class="block text-xs text-gray-400 mb-1.5">Parol</label>
                <input type="password" id="login-password" required placeholder="Parolingizni kiriting"
                    class="w-full bg-[#121212] border border-[#262626] focus:border-[#0095F6] rounded-xl px-4 py-3 text-sm text-white outline-none transition">
            </div>
            <button type="submit" id="login-btn" class="w-full ig-blue-btn text-white font-semibold py-3.5 rounded-xl text-sm shadow-lg shadow-blue-500/20 transition mt-2">
                Kirish
            </button>
        </form>

        <!-- Register Form -->
        <form id="register-form" onsubmit="handleRegister(event)" class="space-y-3 hidden">
            <div class="flex flex-col items-center mb-1">
                <img id="reg-avatar-preview" src="https://placehold.co/150x150/1a1a1a/ffffff?text=U" class="w-16 h-16 rounded-full object-cover border-2 border-[#0095F6] mb-1.5">
                <label class="text-[11px] text-[#0095F6] font-semibold cursor-pointer">
                    Profil rasmini tanlash (ixtiyoriy)
                    <input type="file" accept="image/*" onchange="handleRegAvatarUpload(event)" class="hidden">
                </label>
            </div>
            <div>
                <label class="block text-xs text-gray-400 mb-1">Ismingiz (To'liq ism)</label>
                <input type="text" id="reg-name" required placeholder="Masalan: Kamronbek"
                    class="w-full bg-[#121212] border border-[#262626] focus:border-[#0095F6] rounded-xl px-4 py-2.5 text-sm text-white outline-none">
            </div>
            <div>
                <label class="block text-xs text-gray-400 mb-1">Nik (@username)</label>
                <div class="relative">
                    <span class="absolute left-4 top-2.5 text-gray-500 text-sm">@</span>
                    <input type="text" id="reg-nick" required placeholder="kamronbek" pattern="[a-zA-Z0-9._]+"
                        class="w-full bg-[#121212] border border-[#262626] focus:border-[#0095F6] rounded-xl pl-8 pr-4 py-2.5 text-sm text-white outline-none lowercase">
                </div>
            </div>
            <div>
                <label class="block text-xs text-gray-400 mb-1">Email yoki Telefon raqam</label>
                <input type="text" id="reg-contact" required placeholder="name@gmail.com yoki +998901234567"
                    class="w-full bg-[#121212] border border-[#262626] focus:border-[#0095F6] rounded-xl px-4 py-2.5 text-sm text-white outline-none">
            </div>
            <div>
                <label class="block text-xs text-gray-400 mb-1">Bio (ixtiyoriy)</label>
                <input type="text" id="reg-bio" placeholder="O'zingiz haqingizda qisqacha..."
                    class="w-full bg-[#121212] border border-[#262626] focus:border-[#0095F6] rounded-xl px-4 py-2.5 text-sm text-white outline-none">
            </div>
            <div>
                <label class="block text-xs text-gray-400 mb-1">Parol (kamida 6 belgi)</label>
                <input type="password" id="reg-password" required minlength="6" placeholder="••••••••"
                    class="w-full bg-[#121212] border border-[#262626] focus:border-[#0095F6] rounded-xl px-4 py-2.5 text-sm text-white outline-none">
            </div>
            <button type="submit" id="reg-btn" class="w-full ig-blue-btn text-white font-semibold py-3.5 rounded-xl text-sm shadow-lg shadow-blue-500/20 transition mt-2">
                Ro'yxatdan o'tish va Kirish
            </button>
        </form>

        <div class="mt-6 text-center">
            <p class="text-[11px] text-gray-500">Bir marta kirganingizdan so'ng sessiya saqlanib qoladi</p>
        </div>
    </div>

    <!-- ==================== 2. MAIN APP INTERFACE ==================== -->
    <div id="main-app" class="hidden flex-1 flex flex-col pb-16">

        <!-- Top Header -->
        <header id="top-header" class="sticky top-0 z-30 bg-black/90 backdrop-blur-md border-b border-[#1c1c1c] px-4 h-14 flex items-center justify-between">
            <div class="flex items-center gap-2">
                <span class="text-xl font-extrabold tracking-tight bg-gradient-to-r from-white to-gray-300 bg-clip-text text-transparent">UzGram</span>
                <span class="text-[10px] bg-[#1c1c1c] text-gray-300 px-2 py-0.5 rounded-full border border-[#2e2e2e]">UZ</span>
            </div>
            <div class="flex items-center gap-4">
                <button type="button" onclick="openModal('notifications-modal')" class="relative p-1.5 text-white hover:text-gray-300 transition">
                    <i class="fa-regular fa-heart text-xl"></i>
                    <span id="notif-badge" class="hidden absolute top-1 right-1 w-2.5 h-2.5 bg-red-500 rounded-full border-2 border-black"></span>
                </button>
                <button type="button" onclick="openMessenger()" class="relative p-1.5 text-white hover:text-gray-300 transition">
                    <i class="fa-brands fa-facebook-messenger text-xl"></i>
                    <span id="chat-badge" class="hidden absolute -top-0.5 -right-1 bg-red-500 text-white text-[10px] font-bold px-1.5 rounded-full">!</span>
                </button>
            </div>
        </header>

        <!-- TAB 1: HOME FEED -->
        <main id="view-home" class="flex-1">
            <div class="border-b border-[#1c1c1c] py-3 px-3">
                <div id="stories-list" class="flex items-center gap-3.5 overflow-x-auto no-scrollbar"></div>
            </div>
            <div id="feed-container" class="divide-y divide-[#1c1c1c]"></div>
        </main>

        <!-- TAB 2: GLOBAL PREFIX & SUBSTRING SEARCH -->
        <main id="view-search" class="hidden flex-1 p-4">
            <div class="relative mb-3">
                <i class="fa-solid fa-magnifying-glass absolute left-3.5 top-3.5 text-gray-400 text-sm"></i>
                <input type="text" id="search-input" oninput="renderSearchUsers()" placeholder="Nik yoki ism yozing (masalan: k yoki d)..."
                    class="w-full bg-[#161616] border border-[#262626] focus:border-[#0095F6] rounded-xl pl-10 pr-20 py-2.5 text-sm text-white outline-none">
                <button type="button" onclick="syncUsersFromCloudNow()" title="Serverdan yangilash"
                    class="absolute right-2 top-1.5 bg-[#222] hover:bg-[#2d2d2d] text-sky-400 text-[11px] font-semibold px-2.5 py-1.5 rounded-lg transition">
                    <i class="fa-solid fa-rotate"></i> Yangilash
                </button>
            </div>

            <div class="flex items-center justify-between mb-3">
                <h3 id="search-section-title" class="text-xs font-semibold text-gray-400 uppercase tracking-wider">Barcha ochilgan akkauntlar</h3>
                <span id="users-count-badge" class="text-xs text-sky-400 font-semibold">0 ta akkaunt</span>
            </div>

            <div id="search-results" class="space-y-2.5"></div>
        </main>

        <!-- TAB 4: REELS -->
        <main id="view-reels" class="hidden flex-1 bg-black">
            <div id="reels-feed" class="reels-container no-scrollbar"></div>
        </main>

        <!-- TAB 5: PROFILE -->
        <main id="view-profile" class="hidden flex-1">
            <div class="p-4">
                <div class="flex items-center justify-between mb-4">
                    <div class="flex items-center gap-1.5">
                        <h2 id="prof-nick-header" class="text-lg font-bold">@username</h2>
                        <span id="prof-verified-header" class="hidden" title="Tasdiqlangan akkaunt"></span>
                    </div>
                    <div class="flex items-center gap-2">
                        <button type="button" onclick="openSettingsAndActivity()" class="text-xs bg-[#161616] hover:bg-[#222] border border-[#2a2a2a] px-3 py-1.5 rounded-lg flex items-center gap-1.5 text-white font-medium transition" title="Sozlamalar va faollik">
                            <i class="fa-solid fa-bars text-sm"></i> Sozlamalar
                        </button>
                    </div>
                </div>

                <!-- Avatar & Stats -->
                <div
