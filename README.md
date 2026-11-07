```html
<!DOCTYPE html>
<html lang="sa">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>श्री नन्दकुमाराष्टकम् | Devotional Chanting Companion</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel+Decorative:wght@700&family=Rozha+One&family=Tiro+Devanagari+Sanskrit:ital@0;1&family=Yatra+One&display=swap" rel="stylesheet">
    <style>
        :root {
            --glow-color: rgba(255, 191, 0, 0.45);
            --gold-gradient: linear-gradient(135deg, #ffd700 0%, #ffae19 50%, #d48806 100%);
            --text-glow: 0 0 16px rgba(255, 215, 0, 0.55), 0 0 35px rgba(255, 140, 0, 0.3);
        }

        body {
            font-family: 'Tiro Devanagari Sanskrit', serif;
            background-color: #060913;
            color: #fdf6e2;
            user-select: none;
            -webkit-user-select: none;
            touch-action: pan-y;
            overflow-x: hidden;
        }

        .font-rozhadevi {
            font-family: 'Rozha One', 'Tiro Devanagari Sanskrit', serif;
        }

        .font-yatra {
            font-family: 'Yatra One', cursive;
        }

        /* Pulsing Aura Behind Card */
        @keyframes divinePulse {
            0%, 100% {
                transform: scale(1) rotate(0deg);
                opacity: 0.5;
                filter: blur(28px);
            }
            50% {
                transform: scale(1.08) rotate(180deg);
                opacity: 0.85;
                filter: blur(38px);
            }
        }

        @keyframes diyaFlicker {
            0%, 100% { transform: scale(1) translateY(0); opacity: 0.95; }
            25% { transform: scale(1.06, 0.96) translateY(-1px); opacity: 0.8; }
            50% { transform: scale(0.95, 1.05) translateY(1px); opacity: 1; }
            75% { transform: scale(1.03, 0.98) translateY(-0.5px); opacity: 0.88; }
        }

        .divine-aura {
            animation: divinePulse 10s ease-in-out infinite alternate;
            background: radial-gradient(circle, rgba(255,183,3,0.38) 0%, rgba(217,119,6,0.2) 45%, rgba(67,24,255,0.08) 75%, transparent 100%);
        }

        .diya-flame {
            animation: diyaFlicker 1.8s ease-in-out infinite;
            transform-origin: bottom center;
        }

        .gold-border-glow {
            box-shadow: 0 0 25px rgba(245, 158, 11, 0.28), inset 0 0 15px rgba(255, 215, 0, 0.12);
            border: 1px solid rgba(245, 158, 11, 0.45);
        }

        .refrain-highlight {
            color: #ffd15c;
            text-shadow: 0 0 12px rgba(255, 209, 92, 0.45);
        }

        /* Custom scrollbar for full text mode */
        ::-webkit-scrollbar {
            width: 4px;
        }
        ::-webkit-scrollbar-track {
            background: rgba(10, 15, 29, 0.8);
        }
        ::-webkit-scrollbar-thumb {
            background: #d97706;
            border-radius: 4px;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between relative bg-[#040813] text-amber-50">

    <!-- Ambient Glow Backdrops -->
    <div class="fixed inset-0 pointer-events-none z-0 overflow-hidden">
        <div class="absolute -top-24 left-1/2 -translate-x-1/2 w-96 h-96 divine-aura rounded-full"></div>
        <div class="absolute bottom-10 left-1/2 -translate-x-1/2 w-[30rem] h-[30rem] divine-aura rounded-full" style="animation-delay: -5s;"></div>
        <!-- Temple Silhouette pattern overlay -->
        <div class="absolute inset-0 opacity-10 bg-[radial-gradient(#f59e0b_1px,transparent_1px)] [background-size:24px_24px]"></div>
    </div>

    <!-- Top Navigation & Controls Header -->
    <header class="relative z-20 px-4 pt-3 pb-2 flex flex-col gap-2 max-w-xl mx-auto w-full">
        <!-- Status Bar: Screen Awake Badge + Audio/Controls -->
        <div class="flex items-center justify-between text-xs">
            <!-- Wake Lock Status Indicator -->
            <button id="wakeLockBtn" onclick="toggleWakeLock()" class="flex items-center gap-1.5 px-2.5 py-1 rounded-full bg-amber-950/70 border border-amber-500/40 text-amber-300 transition-all active:scale-95 shadow-[0_0_12px_rgba(245,158,11,0.2)]">
                <span id="wakePulse" class="w-2 h-2 rounded-full bg-emerald-400 animate-ping"></span>
                <span id="wakeStatusText" class="font-medium tracking-wide">स्क्रीन जाग्रत (Screen ON)</span>
                <svg id="wakeIcon" class="w-3.5 h-3.5 text-amber-400" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4 8a4 4 0 11-8 0 4 4 0 018 0zm-.464 4.95l.707.707a1 1 0 001.414-1.414l-.707-.707a1 1 0 00-1.414 1.414zm2.12-10.607a1 1 0 010 1.414l-.706.707a1 1 0 11-1.414-1.414l.707-.707a1 1 0 011.414 0zM17 11a1 1 0 100-2h-1a1 1 0 100 2h1zm-7 4a1 1 0 011 1v1a1 1 0 11-2 0v-1a1 1 0 011-1zM5.05 6.464A1 1 0 106.465 5.05l-.708-.707a1 1 0 00-1.414 1.414l.707.707zm1.414 8.486l-.707.707a1 1 0 01-1.414-1.414l.707-.707a1 1 0 011.414 1.414zM4 11a1 1 0 100-2H3a1 1 0 000 2h1z"/>
                </svg>
            </button>

            <!-- Quick Utilities (Font Size & Sound Toggle) -->
            <div class="flex items-center gap-1.5 bg-slate-900/80 px-2 py-1 rounded-full border border-amber-500/20">
                <button onclick="adjustFontSize(-1)" class="w-7 h-7 flex items-center justify-center text-xs font-bold text-amber-200 hover:text-white rounded active:bg-amber-800/50" title="अक्षर छोटा करें">अ-</button>
                <span class="w-[1px] h-3 bg-amber-500/30"></span>
                <button onclick="adjustFontSize(1)" class="w-7 h-7 flex items-center justify-center text-sm font-bold text-amber-200 hover:text-white rounded active:bg-amber-800/50" title="अक्षर बड़ा करें">अ+</button>
                <span class="w-[1px] h-3 bg-amber-500/30"></span>
                <!-- Bell Sound Toggle -->
                <button id="soundToggleBtn" onclick="toggleSound()" class="w-7 h-7 flex items-center justify-center text-amber-300 active:scale-95" title="घंटी ध्वनि">
                    <svg id="soundIcon" class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
                        <path d="M12 22c1.1 0 2-.9 2-2h-4c0 1.1.9 2 2 2zm6-6v-5c0-3.07-1.63-5.64-4.5-6.32V4c0-.83-.67-1.5-1.5-1.5s-1.5.67-1.5 1.5v.68C7.64 5.36 6 7.92 6 11v5l-2 2v1h16v-1l-2-2zm-2 1H8v-6c0-2.48 1.51-4.5 4-4.5s4 2.02 4 4.5v6z"/>
                    </svg>
                </button>
            </div>
        </div>

        <!-- Title Banner with Sacred Diya -->
        <div class="text-center pt-1 relative">
            <!-- Animated Diya Flame -->
            <div class="flex justify-center items-center mb-1">
                <div class="relative flex flex-col items-center">
                    <div class="w-3.5 h-5 bg-gradient-to-t from-orange-500 via-amber-400 to-yellow-200 rounded-full diya-flame shadow-[0_0_15px_#f59e0b]"></div>
                    <div class="w-7 h-2 bg-gradient-to-r from-amber-800 via-amber-600 to-amber-800 rounded-full -mt-1 border-t border-amber-400/50 shadow-md"></div>
                </div>
            </div>
            
            <h1 class="font-yatra text-2xl sm:text-3xl text-transparent bg-clip-text bg-gradient-to-r from-amber-200 via-yellow-300 to-amber-400 tracking-wider drop-shadow-[0_2px_10px_rgba(245,158,11,0.6)]">
                ॥ श्री नन्दकुमाराष्टकम् ॥
            </h1>
            <p class="text-[11px] text-amber-300/70 tracking-widest uppercase font-sans mt-0.5">
                श्री महाप्रभु वल्लभाचार्य विरचितम्
            </p>
        </div>

        <!-- Mode Tabs: Single Verse vs All Verses -->
        <div class="flex bg-slate-950/80 p-1 rounded-xl border border-amber-500/30 text-xs font-semibold mt-1 max-w-xs mx-auto w-full">
            <button id="modeSingleBtn" onclick="setMode('single')" class="flex-1 py-1.5 rounded-lg transition-all text-center bg-gradient-to-r from-amber-600 to-yellow-600 text-slate-950 font-bold shadow-md">
                श्लोक दर्शन (Single)
            </button>
            <button id="modeAllBtn" onclick="setMode('all')" class="flex-1 py-1.5 rounded-lg transition-all text-center text-amber-300 hover:text-white">
                सम्पूर्ण पाठ (Scroll)
            </button>
        </div>
    </header>

    <!-- Main Content Area -->
    <main class="relative z-10 flex-1 flex flex-col justify-center px-3 py-1 max-w-xl mx-auto w-full">

        <!-- VIEW 1: SINGLE VERSE CARD (Focused Meditation) -->
        <div id="singleVerseView" class="w-full flex flex-col items-center">
            
            <!-- Shloka Number Badge -->
            <div class="flex items-center gap-2 mb-2">
                <span class="h-[1px] w-6 bg-gradient-to-r from-transparent to-amber-500"></span>
                <span id="shlokaBadge" class="text-xs font-bold text-amber-300 tracking-widest uppercase px-3 py-0.5 bg-amber-950/60 rounded-full border border-amber-500/40 shadow-[0_0_8px_rgba(245,158,11,0.2)]">
                    श्लोक १ / ८
                </span>
                <span class="h-[1px] w-6 bg-gradient-to-l from-transparent to-amber-500"></span>
            </div>

            <!-- Verse Card with Glow and Touch Swipe Support -->
            <div id="cardContainer" class="w-full relative overflow-hidden rounded-2xl p-5 sm:p-7 gold-border-glow bg-gradient-to-b from-slate-900/90 via-[#0d1326]/90 to-slate-950/95 backdrop-blur-md transition-all duration-300 shadow-2xl min-h-[290px] flex flex-col justify-center text-center">
                
                <!-- Peacock Feather subtle SVG Watermark in background -->
                <div class="absolute right-3 top-3 opacity-10 pointer-events-none">
                    <svg class="w-20 h-20 text-amber-400" viewBox="0 0 100 100" fill="currentColor">
                        <path d="M50 0 C60 25 85 40 85 65 C85 85 65 100 50 100 C35 100 15 85 15 65 C15 40 40 25 50 0 Z"/>
                    </svg>
                </div>

                <!-- Verse Sanskrit Text -->
                <div id="verseContent" class="space-y-3 leading-relaxed transition-opacity duration-200" style="font-size: 1.25rem;">
                    <!-- Injected dynamically -->
                </div>

                <!-- Quick Swipe Hint -->
                <div class="mt-4 pt-3 border-t border-amber-500/20 flex items-center justify-between text-[11px] text-amber-400/60 font-sans">
                    <button onclick="prevVerse()" class="hover:text-amber-300 transition-colors flex items-center gap-1">
                        ◀ पिछला (Prev)
                    </button>
                    <span class="text-amber-500/40">स्वाइप करें (Swipe)</span>
                    <button onclick="nextVerse()" class="hover:text-amber-300 transition-colors flex items-center gap-1">
                        अगला (Next) ▶
                    </button>
                </div>
            </div>

            <!-- 1 to 8 Quick Navigation Buttons -->
            <div class="flex items-center justify-center gap-1.5 sm:gap-2 mt-3.5 w-full">
                <!-- Dynamically generated verse pills -->
                <div id="versePills" class="flex gap-1.5 overflow-x-auto py-1 px-1"></div>
            </div>
        </div>

        <!-- VIEW 2: ALL VERSES (Continuous Sacred Reading) -->
        <div id="allVersesView" class="hidden w-full max-h-[64vh] overflow-y-auto space-y-4 pr-1 rounded-2xl">
            <!-- Dynamically populated all 8 verses -->
        </div>

    </main>

    <!-- Bottom Chanting Jaap Mala Counter & Controls -->
    <footer class="relative z-20 px-4 py-3 max-w-xl mx-auto w-full bg-slate-950/90 border-t border-amber-500/30 rounded-t-2xl shadow-[0_-8px_25px_rgba(0,0,0,0.7)] backdrop-blur-md">
        <div class="flex items-center justify-between gap-3">
            
            <!-- Left: Jaap Count Display -->
            <div class="flex flex-col">
                <span class="text-[10px] text-amber-300/70 font-sans uppercase tracking-wider">जाप गणना (Count)</span>
                <div class="flex items-baseline gap-1.5">
                    <span id="counterDisplay" class="text-3xl font-black text-amber-300 drop-shadow-[0_0_10px_rgba(255,191,0,0.5)]">0</span>
                    <span id="targetDisplay" class="text-xs text-amber-500/80">/ free</span>
                </div>
            </div>

            <!-- Target Rounds Selector -->
            <div class="flex items-center gap-1 bg-slate-900/90 p-1 rounded-lg border border-amber-500/20 text-xs">
                <button onclick="setTarget(11)" class="target-chip px-2 py-1 rounded text-amber-200/80 active:bg-amber-600 active:text-white" data-target="11">11</button>
                <button onclick="setTarget(21)" class="target-chip px-2 py-1 rounded text-amber-200/80 active:bg-amber-600 active:text-white" data-target="21">21</button>
                <button onclick="setTarget(108)" class="target-chip px-2 py-1 rounded text-amber-200/80 active:bg-amber-600 active:text-white" data-target="108">108</button>
                <button onclick="setTarget(0)" class="target-chip px-2 py-1 rounded bg-amber-500/30 text-amber-300 font-bold" data-target="0">∞</button>
            </div>

            <!-- Chanting Tap Button (Big Golden Touch Trigger) -->
            <div class="flex items-center gap-2">
                <button id="tapBtn" onclick="incrementJaap()" class="relative group px-5 py-2.5 rounded-xl bg-gradient-to-r from-amber-500 via-yellow-400 to-amber-600 text-slate-950 font-bold text-base shadow-[0_0_20px_rgba(245,158,11,0.5)] active:scale-90 transition-all flex items-center gap-1.5">
                    <svg class="w-5 h-5 text-slate-950" fill="currentColor" viewBox="0 0 24 24">
                        <circle cx="12" cy="12" r="9" stroke="currentColor" stroke-width="2" fill="none"/>
                        <circle cx="12" cy="12" r="4" fill="currentColor"/>
                    </svg>
                    <span>जपें (Tap)</span>
                </button>
                
                <!-- Reset Counter -->
                <button onclick="resetJaap()" class="w-8 h-8 rounded-lg bg-slate-900 border border-amber-500/20 text-amber-400 flex items-center justify-center active:scale-95 text-xs" title="पुनः प्रारंभ करें">
                    ↺
                </button>
            </div>

        </div>
    </footer>

    <!-- Notification Toast for Screen Wake / Target Achieved -->
    <div id="toast" class="fixed top-4 left-1/2 -translate-x-1/2 z-50 px-4 py-2 rounded-xl bg-amber-950/90 border border-amber-400 text-amber-200 text-xs shadow-2xl backdrop-blur-md opacity-0 pointer-events-none transition-all duration-300 transform -translate-y-2 text-center">
        स्क्रीन सदैव जाग्रत है
    </div>

    <script>
        // Sacred 8 Verses of Sri Nandakumarashtakam
        const shlokas = [
            {
                id: 1,
                line1: "सुन्दरगोपालम् उरवनमालं नयनविशालं दुःखहरम् ।",
                line2: "वृन्दावनचन्द्रमानन्दकन्दं परमानन्दं धरणिधरम् ॥",
                line3: "वल्लभघनश्यामं पूर्णकामम् अत्यभिरामं प्रीतिकरम् ।",
                refrain: "भज नन्दकुमारं सर्वसुखसारं तत्त्वविचारं ब्रह्मपरम् ॥ १॥"
            },
            {
                id: 2,
                line1: "सुन्दरवारिजवदनं निर्जितमदनं आनन्दसदनं मुकुटधरम् ।",
                line2: "गुञ्जाकृतिहारं विपिनविहारं परमोदारं चीरहरम् ॥",
                line3: "वल्लभपटपीतं कृतउपवीतं करनवनीतं विबुधवरम् ।",
                refrain: "भज नन्दकुमारं सर्वसुखसारं तत्त्वविचारं ब्रह्मपरम् ॥ २॥"
            },
            {
                id: 3,
                line1: "शोभितमुखधूलं यमुनाकूलं निपट अतूलं सुखदतरम् ।",
                line2: "मुखमण्डितरेणुं चारितधेनुं वादितवेणुं मधुरसुरम् ॥",
                line3: "वल्लभमतिविमलं शुभपदकमलं नखरुचिमलं तिमिरहरम् ।",
                refrain: "भज नन्दकुमारं सर्वसुखसारं तत्त्वविचारं ब्रह्मपरम् ॥ ३॥"
            },
            {
                id: 4,
                line1: "शिरमुकुटसुदेशं कुञ्चितकेशं नटवरवेषं कामवरम् ।",
                line2: "मायाकृतमनुजं हलधर-अनुजं प्रतिहतदनुजं भारहरम् ॥",
                line3: "वल्लभव्रजपालं सुभगसुचालं हितमनुकालं भाववरम् ।",
                refrain: "भज नन्दकुमारं सर्वसुखसारं तत्त्वविचारं ब्रह्मपरम् ॥ ४॥"
            },
            {
                id: 5,
                line1: "इन्दीवरभासं प्रकटसुरासं कुसुमविकासं वंशधरम् ।",
                line2: "हृतमन्मथमानं रूपनिधानं कृतकलगानं चित्तहरम् ॥",
                line3: "वल्लभमृदुहासं कुञ्जनिवासं विविधविलासं केलिकरम् ।",
                refrain: "भज नन्दकुमारं सर्वसुखसारं तत्त्वविचारं ब्रह्मपरम् ॥ ५॥"
            },
            {
                id: 6,
                line1: "अतिपरप्रवीणं पालितदीनं भक्ताधीनं कर्मकरम् ।",
                line2: "मोहनमतिधीरं फणिबलवीरं हतपरवीरं तरलतरम् ॥",
                line3: "वल्लभव्रजरमणं वारिजवदनं हलधरशमनं शैलधरम् ।",
                refrain: "भज नन्दकुमारं सर्वसुखसारं तत्त्वविचारं ब्रह्मपरम् ॥ ६॥"
            },
            {
                id: 7,
                line1: "जलधरद्युति-अङ्गं ललितत्रिभङ्गं बहुकृतरङ्गं रसिकवरम् ।",
                line2: "गोकुलपरिवारं मदनाकारं कुञ्जविहारं गूढतरम् ॥",
                line3: "वल्लभव्रजचन्द्रं सुभगसुछन्दं कृतआनन्दं भ्रान्तिहरम् ।",
                refrain: "भज नन्दकुमारं सर्वसुखसारं तत्त्वविचारं ब्रह्मपरम् ॥ ७॥"
            },
            {
                id: 8,
                line1: "वन्दितयुगचरणं पावनकरणं जगदुद्धरणं विमलधरम् ।",
                line2: "कालियशिरगमनं कृतफणिनमनं घातितयमनं मृदुलतरम् ॥",
                line3: "वल्लभदुःखहरणं निर्मलचरणम् अशरणशरणं मुक्तिकरम् ।",
                refrain: "भज नन्दकुमारं सर्वसुखसारं तत्त्वविचारं ब्रह्मपरम् ॥ ८॥"
            }
        ];

        // App States
        let currentVerseIndex = 0;
        let viewMode = 'single'; // 'single' or 'all'
        let currentFontSizeRem = 1.25;
        let jaapCount = 0;
        let targetCount = 0; // 0 is infinite/free
        let isSoundEnabled = true;
        let wakeLock = null;
        let audioCtx = null;

        // --- 1. SCREEN WAKE LOCK IMPLEMENTATION ---
        async function requestWakeLock() {
            try {
                if ('wakeLock' in navigator) {
                    wakeLock = await navigator.wakeLock.request('screen');
                    updateWakeUI(true);
                    
                    wakeLock.addEventListener('release', () => {
                        updateWakeUI(false);
                    });
                } else {
                    updateWakeUI(false, "WakeLock unsupported");
                }
            } catch (err) {
                console.warn('Wake Lock request error:', err);
                updateWakeUI(false);
            }
        }

        async function toggleWakeLock() {
            if (wakeLock !== null) {
                await wakeLock.release();
                wakeLock = null;
                updateWakeUI(false);
                showToast("स्क्रीन लॉक अनुमति सामान्य (Screen Dim Restored)");
            } else {
                await requestWakeLock();
                showToast("स्क्रीन सदैव जाग्रत रहेगी (Screen will remain lit)");
            }
        }

        function updateWakeUI(isActive) {
            const statusText = document.getElementById('wakeStatusText');
            const pulse = document.getElementById('wakePulse');
            const btn = document.getElementById('wakeLockBtn');
            
            if (isActive) {
                statusText.innerText = "स्क्रीन जाग्रत (Awake)";
                pulse.className = "w-2 h-2 rounded-full bg-emerald-400 animate-ping";
                btn.classList.add('border-emerald-500/50', 'text-emerald-300');
                btn.classList.remove('border-amber-500/40', 'text-amber-300');
            } else {
                statusText.innerText = "स्क्रीन विश्राम (Normal)";
                pulse.className = "w-2 h-2 rounded-full bg-amber-500";
                btn.classList.remove('border-emerald-500/50', 'text-emerald-300');
                btn.classList.add('border-amber-500/40', 'text-amber-300');
            }
        }

        // Re-request wake lock when user switches tabs or unlocks phone
        document.addEventListener('visibilitychange', async () => {
            if (wakeLock !== null && document.visibilityState === 'visible') {
                await requestWakeLock();
            }
        });

        // --- 2. SACRED TEMPLE BELL AUDIO (Web Audio API Synthesizer) ---
        function playTempleBell() {
            if (!isSoundEnabled) return;
            try {
                if (!audioCtx) {
                    const AudioContext = window.AudioContext || window.webkitAudioContext;
                    audioCtx = new AudioContext();
                }
                if (audioCtx.state === 'suspended') {
                    audioCtx.resume();
                }

                const now = audioCtx.currentTime;
                // Harmonic partials for a rich bronze Tibetan / Temple bell resonance
                const fundamental = 587.33; // D5 pitch - bright divine frequency
                const partials = [1, 2.02, 3.01, 4.25, 5.43];
                const gains = [0.4, 0.25, 0.18, 0.08, 0.04];

                partials.forEach((ratio, idx) => {
                    const osc = audioCtx.createOscillator();
                    const gain = audioCtx.createGain();
                    
                    osc.type = idx === 0 ? 'sine' : 'triangle';
                    osc.frequency.setValueAtTime(fundamental * ratio, now);

                    // Strike and natural exponential decay
                    gain.gain.setValueAtTime(0, now);
                    gain.gain.linearRampToValueAtTime(gains[idx], now + 0.015);
                    gain.gain.exponentialRampToValueAtTime(0.0001, now + (idx === 0 ? 2.8 : 1.6));

                    osc.connect(gain);
                    gain.connect(audioCtx.destination);

                    osc.start(now);
                    osc.stop(now + 3.0);
                });
            } catch (e) {
                console.error("Audio trigger error:", e);
            }
        }

        function toggleSound() {
            isSoundEnabled = !isSoundEnabled;
            const icon = document.getElementById('soundIcon');
            const btn = document.getElementById('soundToggleBtn');
            if (isSoundEnabled) {
                btn.classList.remove('opacity-40');
                showToast("घंटी ध्वनि चालू (Sound ON)");
            } else {
                btn.classList.add('opacity-40');
                showToast("घंटी ध्वनि बंद (Sound Muted)");
            }
        }

        // --- 3. VERSE RENDERING AND NAVIGATION ---
        function renderSingleVerse(index) {
            const v = shlokas[index];
            const content = document.getElementById('verseContent');
            const badge = document.getElementById('shlokaBadge');
            
            // Fade effect
            content.style.opacity = '0';
            setTimeout(() => {
                badge.innerText = `श्लोक ${v.id} / ${shlokas.length}`;
                content.innerHTML = `
                    <p class="text-amber-100 font-medium tracking-wide drop-shadow-sm">${v.line1}</p>
                    <p class="text-amber-100 font-medium tracking-wide drop-shadow-sm">${v.line2}</p>
                    <p class="text-amber-100 font-medium tracking-wide drop-shadow-sm">${v.line3}</p>
                    <p class="refrain-highlight font-bold tracking-wide pt-1.5 border-t border-amber-500/20">${v.refrain}</p>
                `;
                content.style.fontSize = `${currentFontSizeRem}rem`;
                content.style.opacity = '1';
                updateVersePills();
            }, 150);
        }

        function renderAllVerses() {
            const container = document.getElementById('allVersesView');
            container.innerHTML = shlokas.map((v) => `
                <div class="p-4 rounded-xl bg-slate-900/80 border border-amber-500/30 text-center space-y-1.5 shadow-lg">
                    <span class="inline-block text-[11px] font-bold text-amber-300/80 uppercase px-2 py-0.5 bg-amber-950/70 rounded-full border border-amber-500/30 mb-1">
                        ॥ श्लोक ${v.id} ॥
                    </span>
                    <p class="text-amber-100">${v.line1}</p>
                    <p class="text-amber-100">${v.line2}</p>
                    <p class="text-amber-100">${v.line3}</p>
                    <p class="refrain-highlight font-semibold text-sm pt-1">${v.refrain}</p>
                </div>
            `).join('');
            container.style.fontSize = `${currentFontSizeRem * 0.95}rem`;
        }

        function createPills() {
            const pillsContainer = document.getElementById('versePills');
            pillsContainer.innerHTML = '';
            shlokas.forEach((_, idx) => {
                const btn = document.createElement('button');
                btn.className = `w-8 h-8 rounded-full text-xs font-bold transition-all flex items-center justify-center border`;
                btn.innerText = (idx + 1);
                btn.onclick = () => goToVerse(idx);
                btn.id = `pill-${idx}`;
                pillsContainer.appendChild(btn);
            });
            updateVersePills();
        }

        function updateVersePills() {
            shlokas.forEach((_, idx) => {
                const pill = document.getElementById(`pill-${idx}`);
                if (!pill) return;
                if (idx === currentVerseIndex) {
                    pill.className = "w-8 h-8 rounded-full text-xs font-bold transition-all flex items-center justify-center bg-gradient-to-r from-amber-400 to-yellow-500 text-slate-950 border-amber-300 shadow-[0_0_10px_rgba(255,215,0,0.7)] scale-110";
                } else {
                    pill.className = "w-8 h-8 rounded-full text-xs font-bold transition-all flex items-center justify-center bg-slate-900/90 text-amber-300/70 border-amber-500/30 hover:border-amber-400";
                }
            });
        }

        function nextVerse() {
            currentVerseIndex = (currentVerseIndex + 1) % shlokas.length;
            renderSingleVerse(currentVerseIndex);
            triggerHaptic(10);
        }

        function prevVerse() {
            currentVerseIndex = (currentVerseIndex - 1 + shlokas.length) % shlokas.length;
            renderSingleVerse(currentVerseIndex);
            triggerHaptic(10);
        }

        function goToVerse(idx) {
            currentVerseIndex = idx;
            renderSingleVerse(currentVerseIndex);
            triggerHaptic(15);
        }

        // --- 4. TOUCH SWIPE DETECTION ---
        let touchStartX = 0;
        let touchEndX = 0;
        const card = document.getElementById('cardContainer');

        card.addEventListener('touchstart', (e) => {
            touchStartX = e.changedTouches[0].screenX;
        }, { passive: true });

        card.addEventListener('touchend', (e) => {
            touchEndX = e.changedTouches[0].screenX;
            handleGesture();
        }, { passive: true });

        function handleGesture() {
            const diff = touchEndX - touchStartX;
            if (Math.abs(diff) > 40) { // minimum threshold for swipe
                if (diff < 0) {
                    nextVerse(); // Swiped left -> next
                } else {
                    prevVerse(); // Swiped right -> prev
                }
            }
        }

        // --- 5. JAAP / CHANTING COUNTER ---
        function incrementJaap() {
            jaapCount++;
            document.getElementById('counterDisplay').innerText = jaapCount;
            playTempleBell();
            triggerHaptic(30);

            // Animate button bounce
            const btn = document.getElementById('tapBtn');
            btn.classList.add('scale-95');
            setTimeout(() => btn.classList.remove('scale-95'), 120);

            // Check target
            if (targetCount > 0 && jaapCount === targetCount) {
                showToast(`शुभम्! ${targetCount} मन्त्र पूर्ण हुए (Target Completed)`);
                triggerHaptic([100, 50, 100]);
            }
        }

        function resetJaap() {
            if (jaapCount === 0) return;
            jaapCount = 0;
            document.getElementById('counterDisplay').innerText = '0';
            showToast("जाप संख्या रीसेट हुई (Reset)");
            triggerHaptic(20);
        }

        function setTarget(count) {
            targetCount = count;
            document.getElementById('targetDisplay').innerText = count === 0 ? '/ free' : `/ ${count}`;
            
            // Update Chip UI
            document.querySelectorAll('.target-chip').forEach(btn => {
                if (parseInt(btn.getAttribute('data-target')) === count) {
                    btn.className = "target-chip px-2 py-1 rounded bg-amber-500/30 text-amber-300 font-bold border border-amber-400/40";
                } else {
                    btn.className = "target-chip px-2 py-1 rounded text-amber-200/80 hover:text-white";
                }
            });
            triggerHaptic(15);
        }

        // --- 6. UTILITIES (Font, Mode, Toast, Haptics) ---
        function adjustFontSize(delta) {
            currentFontSizeRem = Math.max(1.0, Math.min(1.8, currentFontSizeRem + delta * 0.1));
            document.getElementById('verseContent').style.fontSize = `${currentFontSizeRem}rem`;
            const allView = document.getElementById('allVersesView');
            if (allView) allView.style.fontSize = `${currentFontSizeRem * 0.95}rem`;
            triggerHaptic(10);
        }

        function setMode(mode) {
            viewMode = mode;
            const singleView = document.getElementById('singleVerseView');
            const allView = document.getElementById('allVersesView');
            const singleBtn = document.getElementById('modeSingleBtn');
            const allBtn = document.getElementById('modeAllBtn');

            if (mode === 'single') {
                singleView.classList.remove('hidden');
                allView.classList.add('hidden');
                singleBtn.className = "flex-1 py-1.5 rounded-lg transition-all text-center bg-gradient-to-r from-amber-600 to-yellow-600 text-slate-950 font-bold shadow-md";
                allBtn.className = "flex-1 py-1.5 rounded-lg transition-all text-center text-amber-300 hover:text-white";
            } else {
                singleView.classList.add('hidden');
                allView.classList.remove('hidden');
                renderAllVerses();
                allBtn.className = "flex-1 py-1.5 rounded-lg transition-all text-center bg-gradient-to-r from-amber-600 to-yellow-600 text-slate-950 font-bold shadow-md";
                singleBtn.className = "flex-1 py-1.5 rounded-lg transition-all text-center text-amber-300 hover:text-white";
            }
            triggerHaptic(15);
        }

        function triggerHaptic(duration) {
            if ('vibrate' in navigator) {
                try {
                    navigator.vibrate(duration);
                } catch(e) {}
            }
        }

        let toastTimer = null;
        function showToast(message) {
            const toast = document.getElementById('toast');
            toast.innerText = message;
            toast.classList.remove('opacity-0', '-translate-y-2');
            toast.classList.add('opacity-100', 'translate-y-0');

            clearTimeout(toastTimer);
            toastTimer = setTimeout(() => {
                toast.classList.add('opacity-0', '-translate-y-2');
                toast.classList.remove('opacity-100', 'translate-y-0');
            }, 2600);
        }

        // First user gesture initialization for audio & wake-lock
        window.addEventListener('click', () => {
            if (!audioCtx) {
                const AudioContext = window.AudioContext || window.webkitAudioContext;
                audioCtx = new AudioContext();
            }
        }, { once: true });

        // On Page Load
        window.onload = function () {
            createPills();
            renderSingleVerse(0);
            requestWakeLock();
        };
    </script>
</body>
</html>
```
