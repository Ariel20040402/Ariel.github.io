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

        /* 热点位置 - 这些位置需要根据实际图片调整 */
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

        .notes-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .note-card {
            background: var(--white);
            border-radius: 16px;
            padding: 1.5rem;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .note-card:hover { transform: translateY(-5px); box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15); }

        .note-card img {
            width: 100%;
            max-height: 300px;
            object-fit: contain;
            border-radius: 8px;
            margin: 1rem 0;
        }

        .note-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
        }

        .note-title { font-size: 1.3rem; color: var(--primary-dark); font-weight: 600; }

        .note-content { color: #666; font-size: 0.95rem; margin-bottom: 1rem; }
        .note-date { font-size: 0.85rem; color: #999; }

        .add-note-section {
            background: var(--white);
            border-radius: 16px;
            padding: 2rem;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            margin-top: 2rem;
        }

        .add-note-section h3 { color: var(--primary-dark); margin-bottom: 1.5rem; font-size: 1.5rem; }

        .form-group { margin-bottom: 1.5rem; }
        .form-group label { display: block; margin-bottom: 0.5rem; color: var(--text-color); font-weight: 500; }
        .form-group input, .form-group textarea {
            width: 100%;
            padding: 0.8rem;
            border: 2px solid #E0E0E0;
            border-radius: 10px;
            font-size: 1rem;
            font-family: inherit;
            transition: border-color 0.3s ease;
        }
        .form-group input:focus, .form-group textarea:focus { outline: none; border-color: var(--primary-color); }
        .form-group textarea { min-height: 120px; resize: vertical; }

        .empty-state { text-align: center; padding: 4rem 2rem; color: #999; }
        .empty-state i { font-size: 4rem; margin-bottom: 1rem; opacity: 0.5; }

        .btn-xiaohongshu {
            background: linear-gradient(135deg, #FF2442, #FF6B6B);
            color: white;
            padding: 1rem 2rem;
            border: none;
            border-radius: 15px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            margin-top: 2rem;
        }

        .btn-xiaohongshu:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(255, 36, 66, 0.4);
        }

        .sub-footer { text-align: center; padding: 2rem; color: #999; margin-top: 3rem; }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
                flex-direction: column;
                position: absolute;
                top: 60px;
                left: 0;
                width: 100%;
                background-color: var(--primary-color);
                padding: 1rem;
            }
            .nav-links.active { display: flex; }
            .menu-toggle { display: block; }

            .hero h1 { font-size: 2rem; }

            .project-timeline::before { left: 20px; }
            .project-item:nth-child(odd) .project-content,
            .project-item:nth-child(even) .project-content {
                margin-left: 50px;
                margin-right: 0;
                text-align: left;
            }
            .project-item:nth-child(odd) .project-content::before,
            .project-item:nth-child(even) .project-content::before { left: -2.5rem; }

            .guide-character {
                position: fixed;
                bottom: 1rem;
                right: 1rem;
                padding: 0.8rem 1.2rem;
            }
            .guide-character .speech { max-width: 150px; font-size: 0.8rem; }

            .notes-grid { grid-template-columns: 1fr; }
        }

        /* 音乐控制按钮 */
        .music-control {
            position: fixed;
            top: 20px;
            right: 20px;
            cursor: pointer;
            font-size: 2rem;
            z-index: 1000;
            opacity: 0;
            pointer-events: none;
            filter: grayscale(100%) brightness(1.7) contrast(1.1);
            transition: all 0.3s ease;
        }

        .music-control.visible {
            opacity: 1;
            pointer-events: auto;
        }

        .music-control:hover {
            transform: scale(1.1);
        }
    </style>
</head>
<body>
    <!-- 背景音乐 -->
    <audio id="bgm" src="music.mp3" loop></audio>
    
    <!-- 音乐控制按钮 -->
    <div id="musicControl" class="music-control" onclick="toggleMusic()">🔊</div>
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



    <!-- 首页 - 房间 -->
    <div id="homePage" class="page active">
        <div class="room-hero">
            <img src="images/room.jpg" alt="Ariel的房间" class="room-bg" onerror="this.style.display='none'; this.parentElement.style.background='linear-gradient(135deg, var(--cream-1), var(--soft-pink))';">
            
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
                        <textarea id="newThought" placeholder="在这里写下你的碎碎念..." required></textarea>
                        <button type="submit" class="btn-primary" style="margin-top: 1rem; width: 100%;">发布</button>
                    </form>
                </div>
            </div>
        </main>

        <footer>
            Made with 💕 by Ariel | © 2026
        </footer>
    </div>

    <!-- 留言板页面（从首页移入） -->
    <div id="messagesPage" class="page">
        <div class="sub-page-header">
            <div class="back-to-room" onclick="showPage('home')">← 回到房间</div>
            <h1>📬 留言板</h1>
            <p class="subtitle">留下你的足迹吧~</p>
        </div>
        
        <main class="section">
            <div class="message-board">
                <div class="message-form">
                    <h3 style="margin-bottom: 1.5rem; color: var(--text-dark);">留下你的足迹 ✨</h3>
                    <form onsubmit="addMessage(event)">
                        <input type="text" id="visitorName" placeholder="你的名字" required>
                        <textarea id="visitorMessage" placeholder="想对我说的话..." required></textarea>
                        <button type="submit" class="btn-primary">发送留言</button>
                    </form>
                </div>
                <div class="message-list" id="messageList"></div>
            </div>
        </main>

        <footer>
            Made with 💕 by Ariel | © 2026
        </footer>
    </div>
    <!-- 法语学习页面 -->
    <div id="frenchPage" class="page">
        <div class="sub-page-header">
            <div class="back-to-room" onclick="showPage('home')">← 回到房间</div>
            <h1>🇫🇷 法语学习</h1>
            <p class="subtitle">专业学习四年 | TCF C1 | 热爱法语文化</p>
        </div>
        
        <main class="section">
            <h2 class="section-title">📝 我的法语笔记</h2>
            
            <div class="notes-grid" id="frenchNotesGrid"></div>
            
            <div class="add-note-section">
                <h3>➕ 添加新笔记</h3>
                <form onsubmit="addFrenchNote(event)">
                    <div class="form-group">
                        <label for="frenchNoteTitle">标题</label>
                        <input type="text" id="frenchNoteTitle" placeholder="请输入笔记标题" required>
                    </div>
                    <div class="form-group">
                        <label for="frenchNoteContent">内容</label>
                        <textarea id="frenchNoteContent" placeholder="请输入笔记内容" required></textarea>
                    </div>
                    <button type="submit" class="btn-primary">保存笔记</button>
                </form>
            </div>
        </main>
        
        <footer>
            Made with 💕 by Ariel | © 2026
        </footer>
    </div>

    <!-- 英语学习页面 -->
    <div id="englishPage" class="page">
        <div class="sub-page-header">
            <div class="back-to-room" onclick="showPage('home')">← 回到房间</div>
            <h1>🇬🇧 英语学习</h1>
            <p class="subtitle">日常交流无障碍 | 阅读能力优秀</p>
        </div>
        
        <main class="section">
            <h2 class="section-title">📝 我的英语笔记</h2>
            
            <div class="notes-grid" id="englishNotesGrid"></div>
            
            <div class="add-note-section">
                <h3>➕ 添加新笔记</h3>
                <form onsubmit="addEnglishNote(event)">
                    <div class="form-group">
                        <label for="englishNoteTitle">标题</label>
                        <input type="text" id="englishNoteTitle" placeholder="请输入笔记标题" required>
                    </div>
                    <div class="form-group">
                        <label for="englishNoteContent">内容</label>
                        <textarea id="englishNoteContent" placeholder="请输入笔记内容" required></textarea>
                    </div>
                    <button type="submit" class="btn-primary">保存笔记</button>
                </form>
            </div>
        </main>
        
        <footer>
            Made with 💕 by Ariel | © 2026
        </footer>
    </div>

    <!-- 中文思考页面 -->
    <div id="chinesePage" class="page">
        <div class="sub-page-header">
            <div class="back-to-room" onclick="showPage('home')">← 回到房间</div>
            <h1>🇨🇳 中文思考</h1>
            <p class="subtitle">母语 | 写作表达能力突出</p>
        </div>
        
        <main class="section">
            <h2 class="section-title">📝 我的中文笔记</h2>
            
            <div class="notes-grid" id="chineseNotesGrid"></div>
            
            <div class="add-note-section">
                <h3>➕ 添加新笔记</h3>
                <form onsubmit="addChineseNote(event)">
                    <div class="form-group">
                        <label for="chineseNoteTitle">标题</label>
                        <input type="text" id="chineseNoteTitle" placeholder="请输入笔记标题" required>
                    </div>
                    <div class="form-group">
                        <label for="chineseNoteContent">内容</label>
                        <textarea id="chineseNoteContent" placeholder="请输入笔记内容" required></textarea>
                    </div>
                    <button type="submit" class="btn-primary">保存笔记</button>
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
            <p class="subtitle">记录法语学习与生活点滴</p>
        </div>
        
        <main class="section">
            <h2 class="section-title">📝 我的笔记</h2>
            
            <div class="notes-grid" id="xiaohongshuNotesGrid"></div>
            
            <div style="text-align: center;">
                <a href="https://xhslink.com/m/7A5AjuXwBSB" target="_blank" class="btn-xiaohongshu">📕 去小红书上查看更多</a>
            </div>
            
            <div class="add-note-section">
                <h3>➕ 添加新笔记</h3>
                <form onsubmit="addXiaohongshuNote(event)">
                    <div class="form-group">
                        <label for="xiaohongshuNoteTitle">标题</label>
                        <input type="text" id="xiaohongshuNoteTitle" placeholder="请输入笔记标题" required>
                    </div>
                    <div class="form-group">
                        <label for="xiaohongshuNoteContent">内容</label>
                        <textarea id="xiaohongshuNoteContent" placeholder="请输入笔记内容"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="xiaohongshuNoteImage">图片URL（可选）</label>
                        <input type="text" id="xiaohongshuNoteImage" placeholder="请输入图片URL">
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
            <h1>✂️ 手工作品</h1>
            <p class="subtitle">创意手工与艺术创作</p>
        </div>
        
        <main class="section">
            <h2 class="section-title">✂️ 我的手工作品</h2>
            
            <div class="notes-grid" id="handmadeNotesGrid"></div>
            
            <div class="add-note-section">
                <h3>➕ 添加新作品</h3>
                <form onsubmit="addHandmadeNote(event)">
                    <div class="form-group">
                        <label for="handmadeNoteTitle">标题</label>
                        <input type="text" id="handmadeNoteTitle" placeholder="请输入作品标题" required>
                    </div>
                    <div class="form-group">
                        <label for="handmadeNoteContent">内容</label>
                        <textarea id="handmadeNoteContent" placeholder="请输入作品描述"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="handmadeNoteImage">图片URL（可选）</label>
                        <input type="text" id="handmadeNoteImage" placeholder="请输入图片URL">
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
            <h1>🍳 美食分享</h1>
            <p class="subtitle">美食探店与烹饪心得</p>
        </div>
        
        <main class="section">
            <h2 class="section-title">🍳 我的美食分享</h2>
            
            <div class="notes-grid" id="foodNotesGrid"></div>
            
            <div class="add-note-section">
                <h3>➕ 添加新分享</h3>
                <form onsubmit="addFoodNote(event)">
                    <div class="form-group">
                        <label for="foodNoteTitle">标题</label>
                        <input type="text" id="foodNoteTitle" placeholder="请输入美食标题" required>
                    </div>
                    <div class="form-group">
                        <label for="foodNoteContent">内容</label>
                        <textarea id="foodNoteContent" placeholder="请输入美食描述"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="foodNoteImage">图片URL（可选）</label>
                        <input type="text" id="foodNoteImage" placeholder="请输入图片URL">
                    </div>
                    <button type="submit" class="btn-primary">保存分享</button>
                </form>
            </div>
        </main>
        
        <footer>
            Made with 💕 by Ariel | © 2026
        </footer>
    </div>

    <script>
        // 加载动画
        document.addEventListener('DOMContentLoaded', function() {
            const loadingScreen = document.getElementById('loadingScreen');
            const progressBar = document.getElementById('progressBar');
            const enterButton = document.getElementById('enterButton');
            let progress = 0;

            // 进度条动画 (4秒)
            const loadingInterval = setInterval(() => {
                progress += 2.5;
                progressBar.style.width = progress + '%';
                
                if (progress >= 100) {
                    clearInterval(loadingInterval);
                    // 显示ENTER按钮
                    setTimeout(() => {
                        enterButton.classList.add('visible');
                    }, 300);
                }
            }, 100);

            // 点击ENTER按钮
            enterButton.addEventListener('click', function() {
                loadingScreen.classList.add('hidden');
                setTimeout(() => {
                    loadingScreen.style.display = 'none';
                    // 加载动画结束后自动播放音乐
                    playMusic();
                }, 800);
            });
        });

        // 背景音乐控制
        let bgm = null;
        let isMusicPlaying = false;

        function initMusic() {
            bgm = document.getElementById('bgm');
            if (bgm) {
                bgm.loop = true;
                bgm.volume = 0.5;
            }
        }

        function playMusic() {
            if (bgm && !isMusicPlaying) {
                bgm.play().then(() => {
                    isMusicPlaying = true;
                    document.getElementById('musicControl').classList.add('visible');
                    updateMusicIcon();
                }).catch(err => {
                    console.log('音乐播放失败:', err);
                });
            }
        }

        function pauseMusic() {
            if (bgm && isMusicPlaying) {
                bgm.pause();
                isMusicPlaying = false;
                updateMusicIcon();
            }
        }

        function toggleMusic() {
            if (isMusicPlaying) {
                pauseMusic();
            } else {
                playMusic();
            }
        }

        function updateMusicIcon() {
            const control = document.getElementById('musicControl');
            if (control) {
                control.innerHTML = isMusicPlaying ? '🔊' : '🔇';
            }
        }

        // 初始化音乐
        document.addEventListener('DOMContentLoaded', function() {
            initMusic();
        });

        // 页面切换
        function showPage(pageName) {
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById(pageName + 'Page').classList.add('active');
            window.scrollTo(0, 0);
            
            // 加载对应页面的数据
            if (pageName === 'home') {
                // 首页不需要加载数据
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

        function toggleMenu() {
            const navLinks = document.getElementById('navLinks');
            navLinks.classList.toggle('active');
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
            // 如果localStorage为空或为空数组，使用默认数据
            if (!thoughts || thoughts.length === 0) {
                thoughts = [
                    { content: '学法语的好处就是感觉英文变亲切了变顺眼了' },
                    { content: 'Tout vient à point à qui sait attendre.只要耐心等待，什么都能成功。' },
                    { content: '冥冥花正开，飏飏燕新乳。' }
                ];
            }
            const list = document.getElementById('thoughtsList');
            
            list.innerHTML = thoughts.map((thought, index) => `
                <div class="thought-item">
                    <p>${thought.content}</p>
                </div>
            `).join('');
        }

        function addThought(e) {
            e.preventDefault();
            const content = document.getElementById('newThought').value.trim();
            if (!content) return;
            
            const thoughts = JSON.parse(localStorage.getItem('thoughts')) || [];
            thoughts.unshift({
                content,
                date: new Date().toLocaleDateString('zh-CN')
            });
            localStorage.setItem('thoughts', JSON.stringify(thoughts));
            document.getElementById('newThought').value = '';
            loadThoughts();
        }

        // 留言板功能
        function loadMessages() {
            const messages = JSON.parse(localStorage.getItem('messages')) || [];
            const list = document.getElementById('messageList');
            
            if (messages.length === 0) {
                list.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-envelope"></i>
                        <p>还没有留言，快来留下第一条吧！</p>
                    </div>
                `;
                return;
            }
            
            list.innerHTML = messages.map((message, index) => `
                <div class="message-item">
                    <div class="message-header">
                        <span class="message-name">${message.name}</span>
                    </div>
                    <p>${message.message}</p>
                </div>
            `).join('');
        }

        function addMessage(e) {
            e.preventDefault();
            const name = document.getElementById('visitorName').value.trim();
            const message = document.getElementById('visitorMessage').value.trim();
            
            if (!name || !message) return;
            
            const messages = JSON.parse(localStorage.getItem('messages')) || [];
            messages.unshift({
                name,
                message,
                date: new Date().toLocaleDateString('zh-CN')
            });
            localStorage.setItem('messages', JSON.stringify(messages));
            document.getElementById('visitorName').value = '';
            document.getElementById('visitorMessage').value = '';
            loadMessages();
        }

        // 法语笔记功能
        function loadFrenchNotes() {
            const notes = JSON.parse(localStorage.getItem('french_notes')) || [];
            renderNotes(notes, 'frenchNotesGrid');
        }

        function renderNotes(notes, gridId) {
            const grid = document.getElementById(gridId);
            
            if (notes.length === 0) {
                grid.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-book"></i>
                        <p>暂无笔记，点击下方添加第一篇吧！</p>
                    </div>
                `;
                return;
            }
            
            grid.innerHTML = notes.map((note, index) => `
                <div class="note-card">
                    ${note.image ? '<img src="' + note.image + '" alt="' + note.title + '" onerror="this.style.display=\'none\';">' : ''}
                    <div class="note-header">
                        <h3 class="note-title">${note.title}</h3>
                    </div>
                    ${note.content ? '<p class="note-content">' + note.content + '</p>' : ''}
                </div>
            `).join('');
        }

        function addFrenchNote(e) {
            e.preventDefault();
            const title = document.getElementById('frenchNoteTitle').value.trim();
            const content = document.getElementById('frenchNoteContent').value.trim();
            
            if (!title || !content) {
                alert('请填写标题和内容');
                return;
            }
            
            const notes = JSON.parse(localStorage.getItem('french_notes')) || [];
            notes.unshift({
                title,
                content,
                date: new Date().toLocaleDateString('zh-CN')
            });
            localStorage.setItem('french_notes', JSON.stringify(notes));
            e.target.reset();
            loadFrenchNotes();
            alert('笔记保存成功！');
        }

        // 英语笔记功能
        function loadEnglishNotes() {
            const notes = JSON.parse(localStorage.getItem('english_notes')) || [];
            renderNotes(notes, 'englishNotesGrid');
        }

        function addEnglishNote(e) {
            e.preventDefault();
            const title = document.getElementById('englishNoteTitle').value.trim();
            const content = document.getElementById('englishNoteContent').value.trim();
            
            if (!title || !content) {
                alert('请填写标题和内容');
                return;
            }
            
            const notes = JSON.parse(localStorage.getItem('english_notes')) || [];
            notes.unshift({
                title,
                content,
                date: new Date().toLocaleDateString('zh-CN')
            });
            localStorage.setItem('english_notes', JSON.stringify(notes));
            e.target.reset();
            loadEnglishNotes();
            alert('笔记保存成功！');
        }

        // 中文笔记功能
        function loadChineseNotes() {
            const notes = JSON.parse(localStorage.getItem('chinese_notes')) || [];
            renderNotes(notes, 'chineseNotesGrid');
        }

        function addChineseNote(e) {
            e.preventDefault();
            const title = document.getElementById('chineseNoteTitle').value.trim();
            const content = document.getElementById('chineseNoteContent').value.trim();
            
            if (!title || !content) {
                alert('请填写标题和内容');
                return;
            }
            
            const notes = JSON.parse(localStorage.getItem('chinese_notes')) || [];
            notes.unshift({
                title,
                content,
                date: new Date().toLocaleDateString('zh-CN')
            });
            localStorage.setItem('chinese_notes', JSON.stringify(notes));
            e.target.reset();
            loadChineseNotes();
            alert('笔记保存成功！');
        }

        // 小红书笔记功能
        function loadXiaohongshuNotes() {
            let notes = JSON.parse(localStorage.getItem('xiaohongshu_notes'));
            // 如果localStorage为空或为空数组，使用默认数据
            if (!notes || notes.length === 0) {
                notes = [
                    { title: '法专生挑战最近很火的écoute chérie', content: '', image: 'images/法专生挑战最近很火的écoute chérie.jpg' },
                    { title: '法专生挑战最近很火的napoléon', content: '', image: 'images/法专生挑战最近很火的napoléon.jpg' }
                ];
            }
            renderNotes(notes, 'xiaohongshuNotesGrid');
        }

        function addXiaohongshuNote(e) {
            e.preventDefault();
            const title = document.getElementById('xiaohongshuNoteTitle').value.trim();
            const content = document.getElementById('xiaohongshuNoteContent').value.trim();
            const image = document.getElementById('xiaohongshuNoteImage').value.trim();
            
            if (!title) {
                alert('请填写标题');
                return;
            }
            
            const notes = JSON.parse(localStorage.getItem('xiaohongshu_notes')) || [];
            notes.unshift({
                title,
                content,
                image,
                date: new Date().toLocaleDateString('zh-CN')
            });
            localStorage.setItem('xiaohongshu_notes', JSON.stringify(notes));
            e.target.reset();
            loadXiaohongshuNotes();
            alert('笔记保存成功！');
        }

        // 手工作品功能
        function loadHandmadeNotes() {
            let notes = JSON.parse(localStorage.getItem('handmade_notes'));
            // 如果localStorage为空或为空数组，使用默认数据
            if (!notes || notes.length === 0) {
                notes = [
                    { title: '香薰蜡烛', content: '', image: 'images/手工作品1.jpg' },
                    { title: '贝壳包', content: '', image: 'images/手工作品2.jpg' },
                    { title: '毕业桂冠', content: '', image: 'images/手工作品3.jpg' }
                ];
            }
            renderNotes(notes, 'handmadeNotesGrid');
        }

        function addHandmadeNote(e) {
            e.preventDefault();
            const title = document.getElementById('handmadeNoteTitle').value.trim();
            const content = document.getElementById('handmadeNoteContent').value.trim();
            const image = document.getElementById('handmadeNoteImage').value.trim();
            
            if (!title) {
                alert('请填写标题');
                return;
            }
            
            const notes = JSON.parse(localStorage.getItem('handmade_notes')) || [];
            notes.unshift({
                title,
                content,
                image,
                date: new Date().toLocaleDateString('zh-CN')
            });
            localStorage.setItem('handmade_notes', JSON.stringify(notes));
            e.target.reset();
            loadHandmadeNotes();
            alert('作品保存成功！');
        }

        // 美食分享功能
        function loadFoodNotes() {
            let notes = JSON.parse(localStorage.getItem('food_notes'));
            // 如果localStorage为空或为空数组，使用默认数据
            if (!notes || notes.length === 0) {
                notes = [
                    { title: '海鲜汤', content: '', image: 'images/美食分享1.jpg' },
                    { title: '冰淇淋', content: '', image: 'images/美食分享2.jpg' },
                    { title: '鹅肝', content: '', image: 'images/美食分享3.jpg' }
                ];
            }
            renderNotes(notes, 'foodNotesGrid');
        }

        function addFoodNote(e) {
            e.preventDefault();
            const title = document.getElementById('foodNoteTitle').value.trim();
            const content = document.getElementById('foodNoteContent').value.trim();
            const image = document.getElementById('foodNoteImage').value.trim();
            
            if (!title) {
                alert('请填写标题');
                return;
            }
            
            const notes = JSON.parse(localStorage.getItem('food_notes')) || [];
            notes.unshift({
                title,
                content,
                image,
                date: new Date().toLocaleDateString('zh-CN')
            });
            localStorage.setItem('food_notes', JSON.stringify(notes));
            e.target.reset();
            loadFoodNotes();
            alert('分享保存成功！');
        }

        // 初始化加载
        document.addEventListener('DOMContentLoaded', function() {
            loadThoughts();
            loadMessages();
        });
    </script>
</body>
</html>
