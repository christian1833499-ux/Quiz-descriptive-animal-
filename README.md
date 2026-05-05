# Quiz-descriptive-animal-
Quiz descriptive text
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quiz Descriptive Text - My Favorite Animal</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800;900&family=Source+Sans+3:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        display: ['Outfit', 'sans-serif'],
                        body: ['Source Sans 3', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        :root {
            --bg: #0A1510;
            --bg-mid: #0F1F17;
            --card: #132A1E;
            --card-hover: #193625;
            --border: #1E4D32;
            --accent: #10B981;
            --accent-light: #34D399;
            --gold: #F59E0B;
            --gold-light: #FBBF24;
            --text: #ECFDF5;
            --text-muted: #6B9B85;
            --danger: #EF4444;
            --success: #22C55E;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }
        html { scroll-behavior: smooth; }
        body {
            font-family: 'Source Sans 3', sans-serif;
            background: var(--bg);
            color: var(--text);
            min-height: 100vh;
            overflow-x: hidden;
        }

        /* ===== Animated Background ===== */
        .bg-scene {
            position: fixed; inset: 0; z-index: 0; pointer-events: none;
            background: 
                radial-gradient(ellipse 80% 60% at 20% 10%, rgba(16,185,129,0.08) 0%, transparent 60%),
                radial-gradient(ellipse 60% 50% at 80% 90%, rgba(245,158,11,0.06) 0%, transparent 60%),
                radial-gradient(ellipse 90% 70% at 50% 50%, rgba(16,185,129,0.03) 0%, transparent 80%),
                var(--bg);
        }

        .floating-particle {
            position: fixed;
            border-radius: 50%;
            pointer-events: none;
            z-index: 1;
            animation: floatUp linear infinite;
            opacity: 0;
        }

        @keyframes floatUp {
            0% { opacity: 0; transform: translateY(100vh) scale(0); }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { opacity: 0; transform: translateY(-10vh) scale(1); }
        }

        /* ===== Paw Print Decoration ===== */
        .paw-bg {
            position: fixed;
            font-size: 24px;
            color: rgba(16,185,129,0.04);
            pointer-events: none;
            z-index: 0;
            animation: pawFade 8s ease-in-out infinite alternate;
        }
        @keyframes pawFade {
            0% { opacity: 0.3; transform: scale(1) rotate(0deg); }
            100% { opacity: 0.8; transform: scale(1.1) rotate(10deg); }
        }

        /* ===== Screens ===== */
        .screen {
            display: none;
            position: relative;
            z-index: 10;
            min-height: 100vh;
            padding: 1.5rem;
        }
        .screen.active { display: flex; }

        /* ===== Cards ===== */
        .glass-card {
            background: linear-gradient(135deg, rgba(19,42,30,0.9), rgba(15,31,23,0.95));
            border: 1px solid var(--border);
            border-radius: 1rem;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }
        .glass-card:hover {
            border-color: var(--accent);
            box-shadow: 0 0 30px rgba(16,185,129,0.1);
        }

        /* ===== Buttons ===== */
        .btn-primary {
            background: linear-gradient(135deg, var(--accent), #059669);
            color: white;
            font-family: 'Outfit', sans-serif;
            font-weight: 600;
            padding: 0.875rem 2rem;
            border-radius: 0.75rem;
            border: none;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1rem;
            position: relative;
            overflow: hidden;
        }
        .btn-primary::before {
            content: '';
            position: absolute;
            inset: 0;
            background: linear-gradient(135deg, transparent, rgba(255,255,255,0.15));
            opacity: 0;
            transition: opacity 0.3s;
        }
        .btn-primary:hover::before { opacity: 1; }
        .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 25px rgba(16,185,129,0.3); }
        .btn-primary:active { transform: translateY(0); }
        .btn-primary:disabled {
            opacity: 0.4;
            cursor: not-allowed;
            transform: none !important;
            box-shadow: none !important;
        }

        .btn-gold {
            background: linear-gradient(135deg, var(--gold), #D97706);
            color: #1a1a0a;
        }
        .btn-gold:hover { box-shadow: 0 8px 25px rgba(245,158,11,0.3); }

        .btn-outline {
            background: transparent;
            color: var(--accent);
            border: 2px solid var(--border);
            font-family: 'Outfit', sans-serif;
            font-weight: 500;
            padding: 0.75rem 1.5rem;
            border-radius: 0.75rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .btn-outline:hover {
            border-color: var(--accent);
            background: rgba(16,185,129,0.1);
        }

        /* ===== Option Buttons ===== */
        .option-btn {
            background: var(--card);
            border: 2px solid var(--border);
            border-radius: 0.875rem;
            padding: 1rem 1.25rem;
            text-align: left;
            cursor: pointer;
            transition: all 0.25s ease;
            color: var(--text);
            font-family: 'Source Sans 3', sans-serif;
            font-size: 1rem;
            width: 100%;
            display: flex;
            align-items: flex-start;
            gap: 0.75rem;
            line-height: 1.5;
        }
        .option-btn:hover:not(.selected):not(.correct):not(.wrong) {
            border-color: var(--accent-light);
            background: var(--card-hover);
            transform: translateX(4px);
        }
        .option-btn .opt-letter {
            flex-shrink: 0;
            width: 32px; height: 32px;
            border-radius: 50%;
            background: rgba(16,185,129,0.15);
            color: var(--accent-light);
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: 'Outfit', sans-serif;
            font-weight: 700;
            font-size: 0.875rem;
            transition: all 0.25s;
        }
        .option-btn.selected {
            border-color: var(--accent-light);
            background: rgba(16,185,129,0.12);
        }
        .option-btn.selected .opt-letter {
            background: var(--accent);
            color: white;
        }
        .option-btn.correct {
            border-color: var(--success) !important;
            background: rgba(34,197,94,0.15) !important;
        }
        .option-btn.correct .opt-letter {
            background: var(--success) !important;
            color: white !important;
        }
        .option-btn.wrong {
            border-color: var(--danger) !important;
            background: rgba(239,68,68,0.12) !important;
        }
        .option-btn.wrong .opt-letter {
            background: var(--danger) !important;
            color: white !important;
        }

        /* ===== Progress Bar ===== */
        .progress-track {
            height: 6px;
            background: var(--card);
            border-radius: 3px;
            overflow: hidden;
        }
        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--accent), var(--gold));
            border-radius: 3px;
            transition: width 0.5s ease;
        }

        /* ===== Score Ring ===== */
        .score-ring {
            width: 180px; height: 180px;
            position: relative;
        }
        .score-ring svg { transform: rotate(-90deg); }
        .score-ring circle {
            fill: none;
            stroke-width: 8;
            stroke-linecap: round;
        }
        .score-ring .ring-bg { stroke: var(--border); }
        .score-ring .ring-fill {
            stroke: var(--accent);
            transition: stroke-dashoffset 1.5s ease;
        }
        .score-ring .ring-fill.gold { stroke: var(--gold); }
        .score-ring .ring-fill.red { stroke: var(--danger); }
        .score-ring .score-text {
            position: absolute;
            inset: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        /* ===== Writing Area ===== */
        .writing-area {
            background: var(--bg-mid);
            border: 2px solid var(--border);
            border-radius: 0.875rem;
            padding: 1rem;
            color: var(--text);
            font-family: 'Source Sans 3', sans-serif;
            font-size: 1rem;
            resize: vertical;
            width: 100%;
            min-height: 180px;
            transition: border-color 0.3s;
            line-height: 1.7;
        }
        .writing-area:focus {
            outline: none;
            border-color: var(--accent);
            box-shadow: 0 0 0 3px rgba(16,185,129,0.15);
        }
        .writing-area::placeholder { color: var(--text-muted); }

        /* ===== Toast ===== */
        .toast-container {
            position: fixed;
            top: 1.5rem;
            right: 1.5rem;
            z-index: 9999;
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }
        .toast {
            padding: 0.875rem 1.25rem;
            border-radius: 0.75rem;
            font-family: 'Source Sans 3', sans-serif;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            animation: toastIn 0.4s ease;
            max-width: 360px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }
        .toast.success { background: #065F46; border: 1px solid #10B981; color: #D1FAE5; }
        .toast.error { background: #7F1D1D; border: 1px solid #EF4444; color: #FEE2E2; }
        .toast.info { background: #1E3A5F; border: 1px solid #3B82F6; color: #DBEAFE; }
        .toast.warning { background: #78350F; border: 1px solid #F59E0B; color: #FEF3C7; }
        .toast.removing { animation: toastOut 0.3s ease forwards; }

        @keyframes toastIn {
            from { opacity: 0; transform: translateX(100px); }
            to { opacity: 1; transform: translateX(0); }
        }
        @keyframes toastOut {
            to { opacity: 0; transform: translateX(100px); }
        }

        /* ===== Modal ===== */
        .modal-overlay {
            display: none;
            position: fixed; inset: 0;
            background: rgba(0,0,0,0.7);
            backdrop-filter: blur(4px);
            z-index: 1000;
            align-items: center;
            justify-content: center;
            padding: 1.5rem;
        }
        .modal-overlay.active { display: flex; }
        .modal-content {
            background: var(--card);
            border: 1px solid var(--border);
            border-radius: 1rem;
            max-width: 500px;
            width: 100%;
            padding: 2rem;
            animation: modalIn 0.3s ease;
        }
        @keyframes modalIn {
            from { opacity: 0; transform: scale(0.9) translateY(20px); }
            to { opacity: 1; transform: scale(1) translateY(0); }
        }

        /* ===== Feedback Box ===== */
        .feedback-box {
            padding: 1rem 1.25rem;
            border-radius: 0.75rem;
            margin-top: 1rem;
            animation: feedbackIn 0.4s ease;
            display: none;
        }
        .feedback-box.show { display: block; }
        .feedback-box.correct-fb {
            background: rgba(34,197,94,0.1);
            border: 1px solid rgba(34,197,94,0.3);
            color: #86EFAC;
        }
        .feedback-box.wrong-fb {
            background: rgba(239,68,68,0.1);
            border: 1px solid rgba(239,68,68,0.3);
            color: #FCA5A5;
        }
        @keyframes feedbackIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* ===== Animations ===== */
        .fade-in { animation: fadeIn 0.5s ease; }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(15px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .slide-in-left { animation: slideLeft 0.5s ease; }
        @keyframes slideLeft {
            from { opacity: 0; transform: translateX(-30px); }
            to { opacity: 1; transform: translateX(0); }
        }
        .scale-in { animation: scaleIn 0.4s ease; }
        @keyframes scaleIn {
            from { opacity: 0; transform: scale(0.85); }
            to { opacity: 1; transform: scale(1); }
        }

        /* ===== Timer Pulse ===== */
        .timer-warning { animation: timerPulse 0.8s ease infinite; }
        @keyframes timerPulse {
            0%, 100% { color: var(--danger); }
            50% { color: var(--gold); }
        }

        /* ===== Category Badge ===== */
        .cat-badge {
            display: inline-flex;
            align-items: center;
            gap: 0.375rem;
            padding: 0.25rem 0.75rem;
            border-radius: 999px;
            font-size: 0.75rem;
            font-weight: 600;
            font-family: 'Outfit', sans-serif;
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }
        .cat-structure { background: rgba(16,185,129,0.15); color: var(--accent-light); }
        .cat-grammar { background: rgba(245,158,11,0.15); color: var(--gold-light); }
        .cat-vocab { background: rgba(139,92,246,0.15); color: #C4B5FD; }
        .cat-writing { background: rgba(236,72,153,0.15); color: #F9A8D4; }

        /* ===== Confetti ===== */
        .confetti-piece {
            position: fixed;
            z-index: 9998;
            pointer-events: none;
            animation: confettiFall linear forwards;
        }
        @keyframes confettiFall {
            0% { opacity: 1; transform: translateY(-10vh) rotate(0deg); }
            100% { opacity: 0; transform: translateY(110vh) rotate(720deg); }
        }

        /* ===== Text Passage ===== */
        .text-passage {
            background: rgba(16,185,129,0.05);
            border-left: 4px solid var(--accent);
            border-radius: 0 0.75rem 0.75rem 0;
            padding: 1.25rem 1.5rem;
            font-style: italic;
            line-height: 1.8;
            color: #B8E0D0;
        }
        .text-passage strong {
            color: var(--accent-light);
            font-style: normal;
        }

        /* ===== Sentence Counter ===== */
        .sentence-counter {
            font-size: 0.875rem;
            color: var(--text-muted);
            text-align: right;
            margin-top: 0.375rem;
            transition: color 0.3s;
        }
        .sentence-counter.enough { color: var(--success); }

        /* ===== Word Highlight ===== */
        .hl-green { color: var(--accent-light); font-weight: 600; }
        .hl-gold { color: var(--gold-light); font-weight: 600; }
        .hl-red { color: #FCA5A5; font-weight: 600; }

        /* ===== Scrollbar ===== */
        ::-webkit-scrollbar { width: 6px; }
        ::-webkit-scrollbar-track { background: var(--bg); }
        ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 3px; }
        ::-webkit-scrollbar-thumb:hover { background: var(--accent); }

        /* ===== Responsive ===== */
        @media (max-width: 640px) {
            .screen { padding: 1rem; }
            .score-ring { width: 140px; height: 140px; }
        }

        @media (prefers-reduced-motion: reduce) {
            *, *::before, *::after {
                animation-duration: 0.01ms !important;
                transition-duration: 0.01ms !important;
            }
        }
    </style>
</head>
<body>
    <!-- Animated Background -->
    <div class="bg-scene" aria-hidden="true"></div>
    <div id="particles" aria-hidden="true"></div>
    <div id="pawPrints" aria-hidden="true"></div>

    <!-- Toast Container -->
    <div class="toast-container" id="toastContainer" role="alert" aria-live="polite"></div>

    <!-- ==================== SCREEN: WELCOME ==================== -->
    <section id="screenWelcome" class="screen active flex-col items-center justify-center">
        <div class="max-w-2xl w-full text-center fade-in">
            <!-- Icon -->
            <div class="mb-6">
                <div class="inline-flex items-center justify-center w-24 h-24 rounded-full" style="background: linear-gradient(135deg, rgba(16,185,129,0.2), rgba(245,158,11,0.15)); border: 2px solid var(--border);">
                    <i class="fa-solid fa-paw text-4xl" style="color: var(--accent-light);"></i>
                </div>
            </div>

            <!-- Header Info -->
            <p class="text-sm font-semibold tracking-widest uppercase mb-2" style="color: var(--text-muted);">TEFL — Meeting 1</p>
            <h1 class="font-display text-4xl sm:text-5xl font-900 mb-3 leading-tight" style="background: linear-gradient(135deg, var(--accent-light), var(--gold-light)); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">
                Descriptive Text Quiz
            </h1>
            <p class="font-display text-lg sm:text-xl font-300 mb-8" style="color: var(--text-muted);">
                My Favorite Animal
            </p>

            <!-- Info Card -->
            <div class="glass-card p-6 mb-8 text-left">
                <h2 class="font-display text-lg font-700 mb-4 flex items-center gap-2">
                    <i class="fa-solid fa-circle-info" style="color: var(--accent);"></i>
                    Informasi Quiz
                </h2>
                <div class="grid sm:grid-cols-2 gap-4 text-sm" style="color: var(--text-muted);">
                    <div class="flex items-start gap-3">
                        <i class="fa-solid fa-list-check mt-0.5" style="color: var(--accent);"></i>
                        <div><span class="font-semibold" style="color: var(--text);">10 Soal Pilihan Ganda</span><br>Mencakup struktur, grammar, dan kosakata</div>
                    </div>
                    <div class="flex items-start gap-3">
                        <i class="fa-solid fa-pen-fancy mt-0.5" style="color: var(--gold);"></i>
                        <div><span class="font-semibold" style="color: var(--text);">1 Soal Menulis</span><br>Tulis descriptive text minimal 5 kalimat</div>
                    </div>
                    <div class="flex items-start gap-3">
                        <i class="fa-solid fa-clock mt-0.5" style="color: var(--accent);"></i>
                        <div><span class="font-semibold" style="color: var(--text);">25 Menit</span><br>Waktu untuk menyelesaikan seluruh quiz</div>
                    </div>
                    <div class="flex items-start gap-3">
                        <i class="fa-solid fa-star mt-0.5" style="color: var(--gold);"></i>
                        <div><span class="font-semibold" style="color: var(--text);">Target 80%</span><br>Skor minimum untuk lulus</div>
                    </div>
                </div>
            </div>

            <!-- Name Input -->
            <div class="glass-card p-5 mb-6 text-left">
                <label for="stud
