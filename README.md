<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ariel's Personal Website</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --cream-1: #F7EFE3;
            --cream-2: #FAF4EA;
            --cream-3: #EFE1CF;
            --soft-pink: #FFE4E1;
            --wood-light: #D4B896;
            --text-soft: #6B5B4F;
            --text-dark: #4A3F35;
            --white: #FFFFFF;
            --shadow-soft: rgba(107, 91, 79, 0.15);
        }

        html, body {
            width: 100%;
            margin: 0;
            padding: 0;
            overflow-x: hidden;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, 'Microsoft YaHei', 'PingFang SC', sans-serif;
        }

        /* 加载动画页面 */
        .loading-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, var(--cream-1), var(--soft-pink));
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 10000;
            transition: opacity 0.8s ease;
        }

        .loading-screen.hidden {
            opacity: 0;
            pointer-events: none;
        }

        .loading-title {
            font-size: 2.5rem;
            color: var(--text-dark);
            margin-bottom: 2rem;
            font-weight: 500;
            animation: pulse 2s ease-in-out infinite;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        .progress-container {
            width: 60%;
            max-width: 400px;
            height: 12px;
            background: rgba(212, 184, 150, 0.3);
            border-radius: 10px;
            overflow: hidden;
            margin-bottom: 2rem;
        }

        .progress-bar {
            height: 100%;
            background: var(--wood-light);
            width: 0%;
            border-radius: 10px;
            transition: width 0.3s ease;
        }

        .emojis-container {
            display: flex;
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .emoji {
            font-size: 3rem;
            animation: bounce 1.5s ease-in-out infinite;
        }

        .emoji:nth-child(1) { animation-delay: 0s; }
        .emoji:nth-child(2) { animation-delay: 0.2s; }
        .emoji:nth-child(3) { animation-delay: 0.4s; }
        .emoji:nth-child(4) { animation-delay: 0.6s; }
        .emoji:nth-child(5) { animation-delay: 0.8s; }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .enter-button {
            padding: 1rem 3rem;
            font-size: 1.5rem;
            background: var(--white);
            color: var(--text-dark);
            border: 2px solid var(--wood-light);
            border-radius: 50px;
            cursor: pointer;
            font-weight: 500;
            box-shadow: 0 4px 15px var(--shadow-soft);
            transition: all 0.3s ease;
            opacity: 0;
            transform: translateY(20px);
        }

        .enter-button.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .enter-button:hover {
            transform: scale(1.05);
            box-shadow: 0 6px 20px var(--shadow-soft);
            background: var(--cream-1);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Microsoft YaHei UI', 'PingFang SC', 'Noto Sans SC', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--cream-1);
            color: var(--text-soft);
            line-height: 1.6;
        }

        nav {
            display: none;
        }

        .page {
            display: none;
            min-height: 100vh;
            background-color: var(--cream-2);
        }

        .page.active {
            display: block;
        }

        /* 房间首页 */
        .room-hero {
            position: relative;
            width: 100%;
            height: 100vh;
            overflow: hidden;
        }

        .room-bg {
            width: 100%;
            height: 100%;
            object-fit: cover;
            object-position: center;
        }

        .room-title {
            position: absolute;
            top: 30px;
            left: 30px;
            font-size: 1.1rem;
            color: var(--text-soft);
            font-weight: 400;
            padding: 15px 25px;
            background: rgba(255, 255, 255, 0.75);
            border-radius: 20px;
            border: 1px solid var(--cream-3);
            box-shadow: 0 4px 15px var(--shadow-soft);
            z-index: 100;
        }

        /* 返回按钮 */
        .back-to-room {
            position: fixed;
            top: 20px;
            left: 20px;
            padding: 10px 20px;
            background: rgba(255, 255, 255, 0.85);
            border: 2px solid var(--cream-3);
            border-radius: 20px;
            color: var(--text-dark);
            font-size: 0.95rem;
            cursor: pointer;
            box-shadow: 0 4px 15px var(--shadow-soft);
            transition: all 0.3s ease;
            z-index: 1000;
        }

        .back-to-room:hover {
            background: var(--cream-1);
            transform: scale(1.05);
        }

        /* 音乐播放器控制按钮 - 单独喇叭样式 */
        .music-control {
            position: fixed;
            top: 20px;
            right: 20px;
            width: 48px;
            height: 48px;
            background: transparent;
            border: none;
            cursor: pointer;
            z-index: 1000;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 0;
        }

        .music-control:hover {
            transform: scale(1.15);
        }

        .music-control i {
            font-size: 1.8rem;
            color: #FAF4EA;
            text-shadow: 0 2px 8px rgba(107, 91, 79, 0.3);
        }

        /* 热点区域 */
        .hotspot {
            position: absolute;
            cursor: pointer;
            z-index: 50;
        }

        .hotspot-btn {
            position: absolute;
            padding: 12px 24px;
            background: rgba(255, 255, 255, 0.85);
            border: 2px solid var(--cream-3);
            border-radius: 25px;
            color: var(--text-dark);
            font-size: 0.95rem;
            font-weight: 500;
            cursor: pointer;
            opacity: 0;
            transform: translateY(10px);
            transition: all 0.4s ease;
            box-shadow: 0 4px 15px var(--shadow-soft);
            white-space: nowrap;
            z-index: 60;
        }

        .hotspot:hover .hotspot-btn {
            opacity: 1;
            transform: translateY(0);
        }

        .hotspot-btn:hover {
            background: var(--cream-1);
            transform: scale(1.05);
        }

        /* 热点位置 */
        #hotspot-notebook { top: 85%; left: 35%; width: 120px; height: 80px; }
        #hotspot-notebook .hotspot-btn { top: -60px; left: 0px; }

        #hotspot-cake { top: 50%; left: 67%; width: 80px; height: 80px; }
        #hotspot-cake .hotspot-btn { top: -50px; left: 0px; }

        #hotspot-bookshelf { top: 55%; left: 35%; width: 180px; height: 130px; }
        #hotspot-bookshelf .hotspot-btn { top: -50px; left: 0px; transform: translateX(0) translateY(0); }
        #hotspot-bookshelf:hover .hotspot-btn { transform: translateX(0) translateY(0); }

        #hotspot-globe { top: 40%; left: 32%; width: 80px; height: 80px; }
        #hotspot-globe .hotspot-btn { top: -50px; left: 0px; }

        #hotspot-computer { top: 72%; left: 15%; width: 180px; height: 110px; }
        #hotspot-computer .hotspot-btn { top: -50px; left: 0px; }

        #hotspot-candle { top: 88%; left: 15%; width: 100px; height: 140px; }
        #hotspot-candle .hotspot-btn { top: 0px; left: -80px; }

        #hotspot-girl { top: 27%; left: 61%; width: 80px; height: 220px; }
        #hotspot-girl .hotspot-btn { top: 0px; left: -100px; }

        .section {
            padding: 4rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
            width: 100%;
        }

        .section-title {
            font-size: 2rem;
            color: var(--text-dark);
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .language-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
        }

        .language-card {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 4px 15px var(--shadow-soft);
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
            border: 2px solid var(--cream-3);
        }

        .language-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 8px 25px var(--shadow-soft);
        }

        .language-card .flag { font-size: 3.5rem; margin-bottom: 1rem; }
        .language-card h3 { color: var(--text-dark); margin-bottom: 0.5rem; font-size: 1.3rem; }

        .level {
            background: linear-gradient(135deg, var(--soft-pink), var(--cream-3));
            color: var(--text-dark);
            padding: 0.4rem 1rem;
            border-radius: 20px;
            font-size: 0.85rem;
            display: inline-block;
            margin-bottom: 1rem;
            font-weight: 500;
        }

        .language-card p { color: var(--text-soft); font-size: 0.95rem; }

        .lang-code {
            font-size: 2.8rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
            font-family: 'Arial Black', sans-serif;
        }

        .lang-code.fr { color: #8B5CF6; }
        .lang-code.gb { color: #4A90D9; }
        .lang-code.cn { color: #FF6B6B; }

        .project-timeline { position: relative; }

        .project-timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 4px;
            background: linear-gradient(180deg, var(--wood-light), var(--soft-pink));
            transform: translateX(-50%);
            border-radius: 2px;
        }

        .project-item { position: relative; margin-bottom: 3rem; display: flex; justify-content: center; }

        .project-item:nth-child(odd) .project-content { margin-right: calc(50% + 2rem); text-align: right; }
        .project-item:nth-child(even) .project-content { margin-left: calc(50% + 2rem); }

        .project-content {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 4px 15px var(--shadow-soft);
            max-width: 450px;
            border: 2px solid var(--cream-3);
            position: relative;
        }

        .project-content::before {
            content: '';
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            width: 20px;
            height: 20px;
            background-color: var(--wood-light);
            border-radius: 50%;
            border: 4px solid var(--white);
            box-shadow: 0 3px 8px var(--shadow-soft);
        }

        .project-item:nth-child(odd) .project-content::before { right: -2.5rem; }
        .project-item:nth-child(even) .project-content::before { left: -2.5rem; }

        .project-content h3 { color: var(--text-dark); margin-bottom: 0.5rem; font-size: 1.3rem; }
        .project-content .date {
            color: var(--wood-light);
            font-size: 0.9rem;
            margin-bottom: 1rem;
            font-weight: 500;
        }
        .project-content p { color: var(--text-soft); font-size: 0.95rem; line-height: 1.7; }

        .travel-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; }

        .travel-card {
            background-color: var(--white);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 4px 15px var(--shadow-soft);
            transition: all 0.3s ease;
            position: relative;
        }

        .travel-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 8px 25px var(--shadow-soft);
        }

        .travel-image {
            height: 260px;
            background: linear-gradient(135deg, var(--cream-3), var(--soft-pink));
            overflow: hidden;
            position: relative;
        }

        .travel-image img { width: 100%; height: 100%; object-fit: cover; }

        .image-counter {
            position: absolute;
            left: 10px;
            bottom: 10px;
            background-color: rgba(255, 255, 255, 0.9);
            color: var(--text-dark);
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 500;
        }

        .travel-arrow-overlay {
            position: absolute;
            right: 12px;
            bottom: 12px;
            cursor: pointer;
            opacity: 0;
            color: var(--text-dark);
            font-size: 2rem;
            text-shadow: 2px 2px 4px rgba(107, 91, 79, 0.3);
            transition: all 0.3s ease;
        }

        .travel-card:hover .travel-arrow-overlay { opacity: 1; }
        .travel-arrow-overlay:hover { transform: translateX(5px); }

        .travel-info { padding: 1.5rem; }
        .travel-info h3 { color: var(--text-dark); margin-bottom: 0.5rem; font-size: 1.2rem; }
        .travel-info p { color: var(--text-soft); font-size: 0.95rem; }

        .works-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 2rem; }

        .work-card {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 4px 15px var(--shadow-soft);
            border: 2px solid var(--cream-3);
            transition: all 0.3s ease;
            cursor: pointer;
            text-align: center;
        }

        .work-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 8px 25px var(--shadow-soft);
        }

        .work-card .work-icon { font-size: 3.5rem; margin-bottom: 1rem; }
        .work-card h3 { color: var(--text-dark); margin-bottom: 0.5rem; font-size: 1.2rem; }
        .work-card p { color: var(--text-soft); font-size: 0.95rem; }

        .thoughts-container { max-width: 800px; margin: 0 auto; }

        .thought-item {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 4px 15px var(--shadow-soft);
            border: 2px solid var(--cream-3);
            margin-bottom: 2rem;
            position: relative;
        }

        .thought-item::before {
            content: '💬';
            position: absolute;
            top: -15px;
            left: 20px;
            font-size: 1.8rem;
        }

        .thought-item p { color: var(--text-soft); line-height: 1.8; font-size: 1rem; }

        .add-thought-form {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 4px 15px var(--shadow-soft);
            border: 2px solid var(--cream-3);
            margin-top: 2rem;
        }

        .add-thought-form textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid var(--cream-3);
            border-radius: 15px;
            font-family: inherit;
            font-size: 1rem;
            min-height: 100px;
            resize: vertical;
            background-color: var(--cream-1);
            transition: all 0.3s ease;
            color: var(--text-soft);
        }

        .add-thought-form textarea:focus {
            outline: none;
            border-color: var(--wood-light);
            box-shadow: 0 0 0 3px rgba(212, 184, 150, 0.2);
        }

        .message-board { max-width: 800px; margin: 0 auto; }

        .message-form {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 4px 15px var(--shadow-soft);
            border: 2px solid var(--cream-3);
            margin-bottom: 2rem;
        }

        .message-form input, .message-form textarea {
            width: 100%;
            padding: 1rem;
            margin-bottom: 1rem;
            border: 2px solid var(--cream-3);
            border-radius: 15px;
            font-family: inherit;
            font-size: 1rem;
            background-color: var(--cream-1);
            transition: all 0.3s ease;
            color: var(--text-soft);
        }

        .message-form input:focus, .message-form textarea:focus {
            outline: none;
            border-color: var(--wood-light);
            box-shadow: 0 0 0 3px rgba(212, 184, 150, 0.2);
        }

        .message-form button {
            background: linear-gradient(135deg, var(--wood-light), var(--soft-pink));
            color: var(--text-dark);
            border: none;
            padding: 1rem 2rem;
            border-radius: 30px;
            font-size: 1rem;
            cursor: pointer;
            font-weight: 500;
            width: 100%;
            box-shadow: 0 4px 12px var(--shadow-soft);
        }

        .message-list { display: flex; flex-direction: column; gap: 1.5rem; }

        .message-item {
            background-color: var(--white);
            padding: 1.5rem;
            border-radius: 15px;
            box-shadow: 0 4px 12px var(--shadow-soft);
            border: 2px solid var(--cream-3);
        }

        .message-item .message-header { display: flex; justify-content: flex-start; margin-bottom: 1rem; }
        .message-item .message-name { font-weight: bold; color: var(--text-dark); font-size: 1.1rem; }
        .message-item p { color: var(--text-soft); font-size: 1rem; }

        footer {
            background: linear-gradient(135deg, var(--cream-3), var(--cream-1));
            color: var(--text-dark);
            text-align: center;
            padding: 2rem;
            margin-top: 4rem;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--wood-light), var(--soft-pink));
            color: var(--text-dark);
            padding: 1rem 2rem;
            border: none;
            border-radius: 10px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px var(--shadow-soft);
        }

        /* 笔记卡片样式 */
        .notes-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
        }

        .note-card {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 4px 15px var(--shadow-soft);
            border: 2px solid var(--cream-3);
            transition: all 0.3s ease;
        }

        .note-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px var(--shadow-soft);
        }

        .note-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 15px;
            margin-bottom: 1rem;
        }

        .note-card .note-header {
            margin-bottom: 1rem;
        }

        .note-card .note-title {
            color: var(--text-dark);
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
        }

        .note-card .note-content {
            color: var(--text-soft);
            line-height: 1.6;
        }

        .add-note-section {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 4px 15px var(--shadow-soft);
            border: 2px solid var(--cream-3);
            margin-top: 2rem;
        }

        .add-note-section h3 {
            color: var(--text-dark);
            margin-bottom: 1.5rem;
        }

        .add-note-section .form-group {
            margin-bottom: 1.5rem;
        }

        .add-note-section label {
            display: block;
            color: var(--text-dark);
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .add-note-section input,
        .add-note-section textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid var(--cream-3);
            border-radius: 15px;
            font-family: inherit;
            font-size: 1rem;
            background-color: var(--cream-1);
            transition: all 0.3s ease;
            color: var(--text-soft);
        }

        .add-note-section input:focus,
        .add-note-section textarea:focus {
            outline: none;
            border-color: var(--wood-light);
            box-shadow: 0 0 0 3px rgba(212, 184, 150, 0.2);
        }

        .btn-xiaohongshu {
            background: linear-gradient(135deg, #ff6b81, #ff8fa3);
            color: white;
            padding: 1rem 2rem;
            border: none;
            border-radius: 30px;
            font-size: 1rem;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .btn-xiaohongshu:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(255, 107, 129, 0.4);
        }

        .empty-state {
            text-align: center;
            padding: 3rem;
            color: var(--text-soft);
        }

        .empty-state i {
            font-size: 4rem;
            margin-bottom: 1rem;
            color: var(--wood-light);
        }

        /* 子页面样式 */
        .sub-page-header {
            background: linear-gradient(135deg, var(--cream-3), var(--cream-1));
            padding: 80px 2rem 40px;
            text-align: center;
            color: var(--text-dark);
        }

        .back-button {
            display: inline-block;
            color: var(--text-dark);
            text-decoration: none;
            font-size: 1.1rem;
            margin-bottom: 1rem;
            padding: 0.5rem 1rem;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 20px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .back-button:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateX(-5px);
        }

        @media (max-width: 768px) {
            .project-timeline::before { left: 20px; }
            .project-item:nth-child(odd) .project-content,
            .project-item:nth-child(even) .project-content {
                margin-left: 50px;
                margin-right: 0;
                text-align: left;
            }
            .project-item:nth-child(odd) .project-content::before,
            .project-item:nth-child(even) .project-content::before { left: -2.5rem; }

            .notes-grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <!-- 加载动画 -->
    <div id="loadingScreen" class="loading-screen">
        <h1 class="loading-title">Welcome to Ariel's World</h1>
        <div class="progress-container">
            <div id="progressBar" class="progress-bar"></div>
        </div>
        <div class="emojis-container">
            <span class="emoji">🎂</span>
            <span class="emoji">🌟</span>
            <span class="emoji">🧚‍♀️</span>
            <span class="emoji">🥰</span>
            <span class="emoji">🫧</span>
        </div>
        <button id="enterButton" class="enter-button">ENTER</button>
    </div>

    <!-- 背景音乐播放器 -->
    <audio id="bgmPlayer" src="花日马林巴.mp3" loop></audio>
    <button id="musicControl" class="music-control" style="display: none;">
        <i id="musicIcon" class="fas fa-volume-up"></i>
    </button>

    <!-- 首页 - 房间 -->
    <div id="homePage" class="page active">
        <div class="room-hero">
            <img src="images/room.jpg" alt="Ariel的房间" class="room-bg" onerror="this.style.display='none'; this.parentElement.style.background='linear-gradient(135deg, var(--cream-1), var(--soft-pink))';">
            <div class="room-effects" aria-hidden="true">
                <div class="animated-curtains">
                    <span class="curtain-panel curtain-left"></span>
                    <span class="curtain-panel curtain-right"></span>
                </div>
                <span class="room-breeze"></span>
                <span class="girl-eyes"></span>
                <div class="coffee-steam">
                    <span></span>
                    <span></span>
                    <span></span>
                </div>
                <span class="candle-flame"></span>
            </div>
            
            <div class="room-title">
                欢迎来到Ariel的房间，试试看点击不同的物件吧~ ✨
            </div>

            <!-- 热点1：红色笔记本 -> 小红书笔记 -->
            <div class="hotspot" id="hotspot-notebook">
                <button class="hotspot-btn" onclick="showPage('xiaohongshu')">📕 小红书笔记</button>
            </div>

            <!-- 热点2：床上的小蛋糕 -> 美食分享 -->
            <div class="hotspot" id="hotspot-cake">
                <button class="hotspot-btn" onclick="showPage('food')">🍰 美食分享</button>
            </div>

            <!-- 热点3：桌上的香薰蜡烛 -> 手工作品 -->
            <div class="hotspot" id="hotspot-candle">
                <button class="hotspot-btn" onclick="showPage('handmade')">🕯️ 手工作品</button>
            </div>

            <!-- 热点4：床边书架 -> 语言学习 -->
            <div class="hotspot" id="hotspot-bookshelf">
                <button class="hotspot-btn" onclick="showPage('language')">📖 语言学习</button>
            </div>

            <!-- 热点5：地球仪 -> 探索世界 -->
            <div class="hotspot" id="hotspot-globe">
                <button class="hotspot-btn" onclick="showPage('travel')">🌍 探索世界</button>
            </div>

            <!-- 热点6：电脑 -> 项目经历 -->
            <div class="hotspot" id="hotspot-computer">
                <button class="hotspot-btn" onclick="showPage('projects')">💻 项目经历</button>
            </div>

            <!-- 热点7：女孩和思考云 -> 碎碎念 -->
            <div class="hotspot" id="hotspot-girl">
                <button class="hotspot-btn" onclick="showPage('thoughts')">💭 碎碎念</button>
            </div>
        </div>
    </div>

    <!-- 语言学习页面 -->
    <div id="languagePage" class="page">
        <div class="sub-page-header">
            <div class="back-to-room" onclick="showPage('home')">← 回到房间</div>
            <h1>📖 语言学习</h1>
            <p class="subtitle">法语TCF C1 | 雅思7.5 | 终身学习者</p>
        </div>
        
        <main class="section">
            <div class="language-cards">
                <div class="language-card" onclick="showPage('french')">
                    <div class="flag">🇫🇷</div>
                    <div class="lang-code fr">FR</div>
                    <h3>法语学习</h3>
                    <span class="level">TCF C1</span>
                    <p>专业学习四年，热爱法语文化</p>
                </div>
                <div class="language-card" onclick="showPage('english')">
                    <div class="flag">🇬🇧</div>
                    <div class="lang-code gb">GB</div>
                    <h3>英语学习</h3>
                    <span class="level">雅思7.5</span>
                    <p>日常交流无障碍，阅读能力优秀</p>
                </div>
                <div class="language-card" onclick="showPage('chinese')">
                    <div class="flag">🇨🇳</div>
                    <div class="lang-code cn">CN</div>
                    <h3>中文思考</h3>
                    <span class="level">母语</span>
                    <p>写作表达能力突出</p>
                </div>
            </div>
        </main>

        <footer>
            Made with 💕 by Ariel | © 2026
        </footer>
    </div>

    <!-- 项目经历页面 -->
    <div id="projectsPage" class="page">
        <div class="sub-page-header">
            <div class="back-to-room" onclick="showPage('home')">← 回到房间</div>
            <h1>💼 项目经历</h1>
            <p class="subtitle">产品经理实习经历</p>
        </div>
        
        <main class="section">
            <div class="project-timeline">
                <div class="project-item">
                    <div class="project-content">
                        <h3>美团推广通/智选展位产品</h3>
                        <div class="date">2025.12 - 2026.03</div>
                        <p><strong>部门</strong>：本地核心商业-商业化增值部<br>
                        <strong>项目背景</strong>：医美行业夜间咨询量占比28%，客单价较高但商户客服未能承接。<br>
                        <strong>核心方案</strong>：开发夜间留咨机器人，在推广通页面新增宣传位，按CPS计费。<br>
                        <strong>技术实现</strong>：采用RAG技术搭建知识库，限制输出80字以内。<br>
                        <strong>项目结果</strong>：夜间广告收入增长67%，商户ROI提升13.5%。</p>
                    </div>
                </div>
                <div class="project-item">
                    <div class="project-content">
                        <h3>百度AI品专广告（百事通）</h3>
                        <div class="date">2024.12 - 2025.02</div>
                        <p><strong>部门</strong>：商业产品部<br>
                        <strong>项目背景</strong>：传统品专广告投放效率低、效果差、体验不达标。<br>
                        <strong>核心方案</strong>：引入AIGC驱动创意优选，构建品牌资产库。<br>
                        <strong>技术实现</strong>：调用百度擎舵生成素材，建立质量打分和排序逻辑。<br>
                        <strong>项目结果</strong>：点击率+10%，转化率+8%，年覆盖收入3亿元。</p>
                    </div>
                </div>
            </div>
        </main>

        <footer>
            Made with 💕 by Ariel | © 2026
        </footer>
    </div>

    <!-- 探索世界页面 -->
    <div id="travelPage" class="page">
        <div class="sub-page-header">
            <div class="back-to-room" onclick="showPage('home')">← 回到房间</div>
            <h1>🌍 探索世界</h1>
            <p class="subtitle">旅行记忆与美好瞬间</p>
        </div>
        
        <main class="section">
            <div class="travel-grid">
                <div class="travel-card" onclick="switchTravelImage(this)">
                    <div class="travel-image">
                        <img src="images/巴黎1.jpg" alt="巴黎" class="travel-main-image" onerror="this.style.display='none';">
                        <div class="travel-arrow-overlay">→</div>
                        <div class="image-counter">1/3</div>
                    </div>
                    <div class="travel-info">
                        <h3>🇫🇷 巴黎</h3>
                        <p>浪漫之都，埃菲尔铁塔、卢浮宫、塞纳河畔...</p>
                    </div>
                    <div class="travel-images" style="display: none;">
                        <img src="images/巴黎1.jpg" alt="巴黎">
                        <img src="images/巴黎2.jpg" alt="巴黎">
                        <img src="images/巴黎3.jpg" alt="巴黎">
                    </div>
                </div>

                <div class="travel-card" onclick="switchTravelImage(this)">
                    <div class="travel-image">
                        <img src="images/尼斯照片1.jpg" alt="尼斯" class="travel-main-image" onerror="this.style.display='none';">
                        <div class="travel-arrow-overlay">→</div>
                        <div class="image-counter">1/2</div>
                    </div>
                    <div class="travel-info">
                        <h3>🇫🇷 尼斯</h3>
                        <p>蔚蓝海岸，阳光沙滩，地中海风情</p>
                    </div>
                    <div class="travel-images" style="display: none;">
                        <img src="images/尼斯照片1.jpg" alt="尼斯">
                        <img src="images/尼斯照片2.jpg" alt="尼斯">
                    </div>
                </div>

                <div class="travel-card" onclick="switchTravelImage(this)">
                    <div class="travel-image">
                        <img src="images/巴塞罗那1.jpg" alt="巴塞罗那" class="travel-main-image" onerror="this.style.display='none';">
                        <div class="travel-arrow-overlay">→</div>
                        <div class="image-counter">1/3</div>
                    </div>
                    <div class="travel-info">
                        <h3>🇪🇸 巴塞罗那</h3>
                        <p>高迪的建筑艺术，地中海畔的热情城市</p>
                    </div>
                    <div class="travel-images" style="display: none;">
                        <img src="images/巴塞罗那1.jpg" alt="巴塞罗那">
                        <img src="images/巴塞罗那2.jpg" alt="巴塞罗那">
                        <img src="images/巴塞罗那3.jpg" alt="巴塞罗那">
                    </div>
                </div>

                <div class="travel-card" onclick="switchTravelImage(this)">
                    <div class="travel-image">
                        <img src="images/意大利照片1.jpg" alt="意大利" class="travel-main-image" onerror="this.style.display='none';">
                        <div class="travel-arrow-overlay">→</div>
                        <div class="image-counter">1/2</div>
                    </div>
                    <div class="travel-info">
                        <h3>🇮🇹 意大利</h3>
                        <p>米兰大教堂充满圣经故事，想要天天吃gelato！🍦</p>
                    </div>
                    <div class="travel-images" style="display: none;">
                        <img src="images/意大利照片1.jpg" alt="意大利">
                        <img src="images/意大利照片2.jpg" alt="意大利">
                    </div>
                </div>

                <div class="travel-card" onclick="switchTravelImage(this)">
                    <div class="travel-image">
                        <img src="images/摩洛哥照片1.jpg" alt="摩纳哥" class="travel-main-image" onerror="this.style.display='none';">
                        <div class="travel-arrow-overlay">→</div>
                        <div class="image-counter">1/2</div>
                    </div>
                    <div class="travel-info">
                        <h3>🇲🇨 摩纳哥</h3>
                        <p>满街豪车，参观摩纳哥王宫，感受奢华之都的魅力</p>
                    </div>
                    <div class="travel-images" style="display: none;">
                        <img src="images/摩洛哥照片1.jpg" alt="摩纳哥">
                        <img src="images/摩洛哥照片2.jpg" alt="摩纳哥">
                    </div>
                </div>

                <div class="travel-card" onclick="switchTravelImage(this)">
                    <div class="travel-image">
                        <img src="images/图卢兹1.jpg" alt="图卢兹" class="travel-main-image" onerror="this.style.display='none';">
                        <div class="travel-arrow-overlay">→</div>
                        <div class="image-counter">1/2</div>
                    </div>
                    <div class="travel-info">
                        <h3>🇫🇷 图卢兹</h3>
                        <p>玫瑰之城，航空航天的重镇</p>
                    </div>
                    <div class="travel-images" style="display: none;">
                        <img src="images/图卢兹1.jpg" alt="图卢兹">
                        <img src="images/图卢兹2.jpg" alt="图卢兹">
                    </div>
                </div>

                <div class="travel-card" onclick="switchTravelImage(this)">
                    <div class="travel-image">
                        <img src="images/比利时1.jpg" alt="比利时" class="travel-main-image" onerror="this.style.display='none';">
                        <div class="travel-arrow-overlay">→</div>
                        <div class="image-counter">1/2</div>
                    </div>
                    <div class="travel-info">
                        <h3>🇧🇪 比利时</h3>
                        <p>巧克力与华夫饼的国度</p>
                    </div>
                    <div class="travel-images" style="display: none;">
                        <img src="images/比利时1.jpg" alt="比利时">
                        <img src="images/比利时2.jpg" alt="比利时">
                    </div>
                </div>
            </div>
        </main>

        <footer>
            Made with 💕 by Ariel | © 2026
        </footer>
    </div>

    <!-- 碎碎念页面 -->
    <div id="thoughtsPage" class="page">
        <div class="sub-page-header">
            <div class="back-to-room" onclick="showPage('home')">← 回到房间</div>
            <h1>💭 Ariel的碎碎念</h1>
            <p class="subtitle">日常思考与感悟</p>
        </div>
        
        <main class="section">
            <div class="thoughts-container">
                <div id="thoughtsList"></div>
                <div class="add-thought-form">
                    <h3>分享你的想法 ✨</h3>
                    <form onsubmit="addThought(event)">
                        <textarea id="thoughtInput" placeholder="写下你的想法..."></textarea>
                        <br>
                        <button type="submit" class="btn-primary">发布</button>
                    </form>
                </div>
            </div>
        </main>

        <footer>
            Made with 💕 by Ariel | © 2026
        </footer>
    </div>

    <!-- 留言板页面 -->
    <div id="messagesPage" class="page">
        <div class="sub-page-header">
            <div class="back-to-room" onclick="showPage('home')">← 回到房间</div>
            <h1>📬 留言板</h1>
            <p class="subtitle">留下你的足迹</p>
        </div>
        
        <main class="section">
            <div class="message-board">
                <form class="message-form" id="messageForm">
                    <input type="text" id="nameInput" placeholder="你的名字" required>
                    <textarea id="messageInput" placeholder="写下你想说的话..." rows="4" required></textarea>
                    <button type="submit">发送留言</button>
                </form>
                <div class="message-list" id="messageList"></div>
            </div>
        </main>

        <footer>
            Made with 💕 by Ariel | © 2026
        </footer>
    </div>

    <!-- 法语笔记页面 -->
    <div id="frenchPage" class="page">
        <div class="sub-page-header">
            <div class="back-to-room" onclick="showPage('language')">← 返回语言学习</div>
            <h1>🇫🇷 法语学习笔记</h1>
            <p class="subtitle">法语TCF C1水平</p>
        </div>
        
        <main class="section">
            <div id="frenchNotes"></div>
            <div class="add-note-section">
                <h3>添加法语笔记 ✏️</h3>
                <form onsubmit="addFrenchNote(event)">
                    <div class="form-group">
                        <label for="frenchTitle">标题</label>
                        <input type="text" id="frenchTitle" placeholder="笔记标题">
                    </div>
                    <div class="form-group">
                        <label for="frenchContent">内容</label>
                        <textarea id="frenchContent" placeholder="笔记内容"></textarea>
                    </div>
                    <button type="submit" class="btn-primary">保存笔记</button>
                </form>
            </div>
        </main>

        <footer>
            Made with 💕 by Ariel | © 2026
        </footer>
    </div>

    <!-- 英语笔记页面 -->
    <div id="englishPage" class="page">
        <div class="sub-page-header">
            <div class="back-to-room" onclick="showPage('language')">← 返回语言学习</div>
            <h1>🇬🇧 英语学习笔记</h1>
            <p class="subtitle">雅思7.5</p>
        </div>
        
        <main class="section">
            <div id="englishNotes"></div>
            <div class="add-note-section">
                <h3>添加英语笔记 ✏️</h3>
                <form onsubmit="addEnglishNote(event)">
                    <div class="form-group">
                        <label for="englishTitle">标题</label>
                        <input type="text" id="englishTitle" placeholder="笔记标题">
                    </div>
                    <div class="form-group">
                        <label for="englishContent">内容</label>
                        <textarea id="englishContent" placeholder="笔记内容"></textarea>
                    </div>
                    <button type="submit" class="btn-primary">保存笔记</button>
                </form>
            </div>
        </main>

        <footer>
            Made with 💕 by Ariel | © 2026
        </footer>
    </div>

    <!-- 中文笔记页面 -->
    <div id="chinesePage" class="page">
        <div class="sub-page-header">
            <div class="back-to-room" onclick="showPage('language')">← 返回语言学习</div>
            <h1>🇨🇳 中文思考笔记</h1>
            <p class="subtitle">母语水平</p>
        </div>
        
        <main class="section">
            <div id="chineseNotes"></div>
            <div class="add-note-section">
                <h3>添加中文笔记 ✏️</h3>
                <form onsubmit="addChineseNote(event)">
                    <div class="form-group">
                        <label for="chineseTitle">标题</label>
                        <input type="text" id="chineseTitle" placeholder="笔记标题">
                    </div>
                    <div class="form-group">
                        <label for="chineseContent">内容</label>
                        <textarea id="chineseContent" placeholder="笔记内容"></textarea>
                    </div>
                    <button type="submit" class="btn-primary">保存笔记</button>
                </form>
            </div>
        </main>

        <footer>
            Made with 💕 by Ariel | © 2026
        </footer>
    </div>

    <!-- 手工作品页面 -->
    <div id="handmadePage" class="page">
        <div class="sub-page-header">
            <div class="back-to-room" onclick="showPage('home')">← 回到房间</div>
            <h1>🧶 手工作品</h1>
            <p class="subtitle">DIY手工制作</p>
        </div>
        
        <main class="section">
            <div id="handmadeNotes"></div>
            <div class="add-note-section">
                <h3>分享手工作品 ✏️</h3>
                <form onsubmit="addHandmadeNote(event)">
                    <div class="form-group">
                        <label for="handmadeTitle">作品名称</label>
                        <input type="text" id="handmadeTitle" placeholder="作品名称">
                    </div>
                    <div class="form-group">
                        <label for="handmadeContent">作品描述</label>
                        <textarea id="handmadeContent" placeholder="描述你的作品"></textarea>
                    </div>
                    <button type="submit" class="btn-primary">保存作品</button>
                </form>
            </div>
        </main>

        <footer>
            Made with 💕 by Ariel | © 2026
        </footer>
    </div>

    <!-- 美食分享页面 -->
    <div id="foodPage" class="page">
        <div class="sub-page-header">
            <div class="back-to-room" onclick="showPage('home')">← 回到房间</div>
            <h1>🍰 美食分享</h1>
            <p class="subtitle">美食探索与烹饪分享</p>
        </div>
        
        <main class="section">
            <div id="foodNotes"></div>
            <div class="add-note-section">
                <h3>分享美食 ✏️</h3>
                <form onsubmit="addFoodNote(event)">
                    <div class="form-group">
                        <label for="foodTitle">美食名称</label>
                        <input type="text" id="foodTitle" placeholder="美食名称">
                    </div>
                    <div class="form-group">
                        <label for="foodContent">美食描述</label>
                        <textarea id="foodContent" placeholder="描述这道美食"></textarea>
                    </div>
                    <button type="submit" class="btn-primary">保存美食</button>
                </form>
            </div>
        </main>

        <footer>
            Made with 💕 by Ariel | © 2026
        </footer>
    </div>

    <!-- 小红书笔记页面 -->
    <div id="xiaohongshuPage" class="page">
        <div class="sub-page-header">
            <div class="back-to-room" onclick="showPage('home')">← 回到房间</div>
            <h1>📕 小红书笔记</h1>
            <p class="subtitle">记录生活点滴</p>
        </div>
        
        <main class="section">
            <div id="xiaohongshuNotes"></div>
            <div class="add-note-section">
                <h3>发布小红书笔记 ✏️</h3>
                <form onsubmit="addXiaohongshuNote(event)">
                    <div class="form-group">
                        <label for="xiaohongshuTitle">笔记标题</label>
                        <input type="text" id="xiaohongshuTitle" placeholder="笔记标题">
                    </div>
                    <div class="form-group">
                        <label for="xiaohongshuContent">笔记内容</label>
                        <textarea id="xiaohongshuContent" placeholder="写下你的笔记内容"></textarea>
                    </div>
                    <button type="submit" class="btn-xiaohongshu">发布笔记</button>
                </form>
            </div>
        </main>

        <footer>
            Made with 💕 by Ariel | © 2026
        </footer>
    </div>

    <script>
        // 背景音乐控制
        const bgmPlayer = document.getElementById('bgmPlayer');
        const musicControl = document.getElementById('musicControl');
        const musicIcon = document.getElementById('musicIcon');

        function toggleMusic() {
            if (bgmPlayer.paused) {
                bgmPlayer.play();
                musicIcon.className = 'fas fa-volume-up';
            } else {
                bgmPlayer.pause();
                musicIcon.className = 'fas fa-volume-mute';
            }
        }

        // 加载动画
        document.addEventListener('DOMContentLoaded', function() {
            const loadingScreen = document.getElementById('loadingScreen');
            const progressBar = document.getElementById('progressBar');
            const enterButton = document.getElementById('enterButton');
            let progress = 0;

            const loadingInterval = setInterval(() => {
                progress += 2.5;
                progressBar.style.width = progress + '%';
                
                if (progress >= 100) {
                    clearInterval(loadingInterval);
                    setTimeout(() => {
                        enterButton.classList.add('visible');
                    }, 300);
                }
            }, 100);

            enterButton.addEventListener('click', function() {
                loadingScreen.classList.add('hidden');
                setTimeout(() => {
                    loadingScreen.style.display = 'none';
                    // 显示音乐控制按钮
                    musicControl.style.display = 'flex';
                    // 尝试播放背景音乐
                    bgmPlayer.play().catch(e => {
                        console.log('自动播放被阻止，用户需要先交互');
                    });
                }, 800);
            });
        });

        // 音乐控制按钮点击
        musicControl.addEventListener('click', toggleMusic);

        // 页面切换
        function showPage(pageName) {
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById(pageName + 'Page').classList.add('active');
            window.scrollTo(0, 0);
            
            // 确保音乐控制按钮始终显示
            musicControl.style.display = 'flex';
            
            // 加载对应页面的数据
            if (pageName === 'home') {
            } else if (pageName === 'french') {
                loadFrenchNotes();
            } else if (pageName === 'english') {
                loadEnglishNotes();
            } else if (pageName === 'chinese') {
                loadChineseNotes();
            } else if (pageName === 'xiaohongshu') {
                loadXiaohongshuNotes();
            } else if (pageName === 'handmade') {
                loadHandmadeNotes();
            } else if (pageName === 'food') {
                loadFoodNotes();
            } else if (pageName === 'thoughts') {
                loadThoughts();
            } else if (pageName === 'messages') {
                loadMessages();
            }
        }

        // 探索世界图片切换
        function switchTravelImage(card) {
            const imagesContainer = card.querySelector('.travel-images');
            const mainImage = card.querySelector('.travel-main-image');
            const counter = card.querySelector('.image-counter');
            
            if (!imagesContainer || !mainImage) return;
            
            const images = imagesContainer.querySelectorAll('img');
            if (images.length === 0) return;
            
            let currentIndex = 0;
            for (let i = 0; i < images.length; i++) {
                if (images[i].src === mainImage.src) {
                    currentIndex = i;
                    break;
                }
            }
            
            const nextIndex = (currentIndex + 1) % images.length;
            mainImage.src = images[nextIndex].src;
            counter.textContent = `${nextIndex + 1}/${images.length}`;
        }

        // 碎碎念功能
        function loadThoughts() {
            let thoughts = JSON.parse(localStorage.getItem('thoughts'));
            if (!thoughts || thoughts.length === 0) {
                thoughts = [
                    { content: '学法语的好处就是感觉英文变亲切了变顺眼了' },
                    { content: 'Tout vient à point à qui sait attendre.只要耐心等待，什么都能成功。' },
                    { content: '冥冥花正开，飏飏燕新乳。' }
                ];
            }
            
            const thoughtsList = document.getElementById('thoughtsList');
            thoughtsList.innerHTML = thoughts.map(thought => `
                <div class="thought-item">
                    <p>${thought.content}</p>
                </div>
            `).join('');
        }

        function addThought(event) {
            event.preventDefault();
            const input = document.getElementById('thoughtInput');
            const content = input.value.trim();
            
            if (!content) return;
            
            let thoughts = JSON.parse(localStorage.getItem('thoughts')) || [];
            thoughts.push({ content });
            localStorage.setItem('thoughts', JSON.stringify(thoughts));
            
            const thoughtsList = document.getElementById('thoughtsList');
            const newThought = document.createElement('div');
            newThought.className = 'thought-item';
            newThought.innerHTML = `<p>${content}</p>`;
            thoughtsList.insertBefore(newThought, thoughtsList.firstChild);
            
            input.value = '';
        }

        // 留言板功能
        function loadMessages() {
            let messages = JSON.parse(localStorage.getItem('messages'));
            if (!messages || messages.length === 0) {
                messages = [
                    { name: '小明', content: '加油！你的法语学习分享真的很有帮助！🎉' },
                    { name: '法语爱好者', content: '希望能看到更多关于法国文化的内容！😊' }
                ];
            }
            
            const messageList = document.getElementById('messageList');
            messageList.innerHTML = messages.map(msg => `
                <div class="message-item">
                    <div class="message-header">
                        <span class="message-name">${msg.name}</span>
                    </div>
                    <p>${msg.content}</p>
                </div>
            `).join('');
        }

        document.getElementById('messageForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const name = document.getElementById('nameInput').value.trim();
            const content = document.getElementById('messageInput').value.trim();
            
            if (!name || !content) return;
            
            let messages = JSON.parse(localStorage.getItem('messages')) || [];
            messages.push({ name, content });
            localStorage.setItem('messages', JSON.stringify(messages));
            
            const messageList = document.getElementById('messageList');
            const newMessage = document.createElement('div');
            newMessage.className = 'message-item';
            newMessage.innerHTML = `
                <div class="message-header">
                    <span class="message-name">${name}</span>
                </div>
                <p>${content}</p>
            `;
            messageList.insertBefore(newMessage, messageList.firstChild);
            
            document.getElementById('nameInput').value = '';
            document.getElementById('messageInput').value = '';
        });

        // 笔记功能通用函数
        function loadNotes(storageKey, containerId, defaultNotes) {
            let notes = JSON.parse(localStorage.getItem(storageKey));
            if (!notes || notes.length === 0) {
                notes = defaultNotes;
            }
            
            const container = document.getElementById(containerId);
            if (notes.length === 0) {
                container.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-sticky-note"></i>
                        <p>暂无笔记，快来添加吧！</p>
                    </div>
                `;
            } else {
                container.innerHTML = `
                    <div class="notes-grid">
                        ${notes.map(note => `
                            <div class="note-card">
                                <div class="note-header">
                                    <div class="note-title">${note.title}</div>
                                </div>
                                <div class="note-content">${note.content}</div>
                            </div>
                        `).join('')}
                    </div>
                `;
            }
        }

        function addNote(event, storageKey, titleId, contentId, containerId, defaultNotes) {
            event.preventDefault();
            
            const title = document.getElementById(titleId).value.trim();
            const content = document.getElementById(contentId).value.trim();
            
            if (!title || !content) return;
            
            let notes = JSON.parse(localStorage.getItem(storageKey)) || defaultNotes;
            notes.push({ title, content });
            localStorage.setItem(storageKey, JSON.stringify(notes));
            
            document.getElementById(titleId).value = '';
            document.getElementById(contentId).value = '';
            
            loadNotes(storageKey, containerId, defaultNotes);
        }

        // 法语笔记
        function loadFrenchNotes() {
            const defaultNotes = [
                { title: '法语动词变位', content: '法语动词分为三组，第一组动词以-er结尾，第二组以-ir结尾，第三组是不规则动词...' },
                { title: 'TCF考试准备', content: 'TCF考试分为听力、语法、阅读三个部分，建议提前三个月准备...' }
            ];
            loadNotes('frenchNotes', 'frenchNotes', defaultNotes);
        }

        function addFrenchNote(event) {
            const defaultNotes = [
                { title: '法语动词变位', content: '法语动词分为三组，第一组动词以-er结尾，第二组以-ir结尾，第三组是不规则动词...' },
                { title: 'TCF考试准备', content: 'TCF考试分为听力、语法、阅读三个部分，建议提前三个月准备...' }
            ];
            addNote(event, 'frenchNotes', 'frenchTitle', 'frenchContent', 'frenchNotes', defaultNotes);
        }

        // 英语笔记
        function loadEnglishNotes() {
            const defaultNotes = [
                { title: '雅思备考技巧', content: '雅思听力要注意同义替换，阅读要掌握略读技巧...' },
                { title: '商务英语', content: '商务邮件要简洁明了，注意正式用语...' }
            ];
            loadNotes('englishNotes', 'englishNotes', defaultNotes);
        }

        function addEnglishNote(event) {
            const defaultNotes = [
                { title: '雅思备考技巧', content: '雅思听力要注意同义替换，阅读要掌握略读技巧...' },
                { title: '商务英语', content: '商务邮件要简洁明了，注意正式用语...' }
            ];
            addNote(event, 'englishNotes', 'englishTitle', 'englishContent', 'englishNotes', defaultNotes);
        }

        // 中文笔记
        function loadChineseNotes() {
            const defaultNotes = [
                { title: '写作技巧', content: '好的文章要有清晰的结构，开头引人入胜，结尾回味无穷...' },
                { title: '诗词欣赏', content: '中国古典诗词博大精深，蕴含着丰富的文化内涵...' }
            ];
            loadNotes('chineseNotes', 'chineseNotes', defaultNotes);
        }

        function addChineseNote(event) {
            const defaultNotes = [
                { title: '写作技巧', content: '好的文章要有清晰的结构，开头引人入胜，结尾回味无穷...' },
                { title: '诗词欣赏', content: '中国古典诗词博大精深，蕴含着丰富的文化内涵...' }
            ];
            addNote(event, 'chineseNotes', 'chineseTitle', 'chineseContent', 'chineseNotes', defaultNotes);
        }

        // 手工作品笔记
        function loadHandmadeNotes() {
            const defaultNotes = [
                { title: '钩针编织杯垫', content: '用牛奶棉线钩织的可爱杯垫，简单又实用，适合初学者...' },
                { title: '羊毛毡小动物', content: '戳戳乐羊毛毡，制作可爱的小动物摆件...' }
            ];
            loadNotes('handmadeNotes', 'handmadeNotes', defaultNotes);
        }

        function addHandmadeNote(event) {
            const defaultNotes = [
                { title: '钩针编织杯垫', content: '用牛奶棉线钩织的可爱杯垫，简单又实用，适合初学者...' },
                { title: '羊毛毡小动物', content: '戳戳乐羊毛毡，制作可爱的小动物摆件...' }
            ];
            addNote(event, 'handmadeNotes', 'handmadeTitle', 'handmadeContent', 'handmadeNotes', defaultNotes);
        }

        // 美食笔记
        function loadFoodNotes() {
            const defaultNotes = [
                { title: '提拉米苏', content: '经典意式甜点，浓郁咖啡与马斯卡彭的完美结合...' },
                { title: '舒芙蕾', content: '法式云朵般的甜品，口感轻盈细腻...' }
            ];
            loadNotes('foodNotes', 'foodNotes', defaultNotes);
        }

        function addFoodNote(event) {
            const defaultNotes = [
                { title: '提拉米苏', content: '经典意式甜点，浓郁咖啡与马斯卡彭的完美结合...' },
                { title: '舒芙蕾', content: '法式云朵般的甜品，口感轻盈细腻...' }
            ];
            addNote(event, 'foodNotes', 'foodTitle', 'foodContent', 'foodNotes', defaultNotes);
        }

        // 小红书笔记
        function loadXiaohongshuNotes() {
            const defaultNotes = [
                { title: '今日份穿搭', content: '简约风格，舒适又时尚...' },
                { title: '周末探店', content: '发现一家超棒的咖啡店...' }
            ];
            loadNotes('xiaohongshuNotes', 'xiaohongshuNotes', defaultNotes);
        }

        function addXiaohongshuNote(event) {
            const defaultNotes = [
                { title: '今日份穿搭', content: '简约风格，舒适又时尚...' },
                { title: '周末探店', content: '发现一家超棒的咖啡店...' }
            ];
            addNote(event, 'xiaohongshuNotes', 'xiaohongshuTitle', 'xiaohongshuContent', 'xiaohongshuNotes', defaultNotes);
        }
    </script>
</body>
</html>
