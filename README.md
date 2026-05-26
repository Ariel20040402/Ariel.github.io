<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ariel's Personal Website</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #4A90D9;
            --primary-light: #E8F4FD;
            --primary-dark: #2E5C8A;
            --secondary-color: #FFB6C1;
            --accent-color: #FFE4E1;
            --bg-color: #F8FCFF;
            --text-color: #333333;
            --white: #FFFFFF;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
        }

        nav {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: var(--primary-color);
            padding: 1rem 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(74, 144, 217, 0.3);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--white);
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 1rem;
        }

        .nav-links a {
            color: var(--white);
            text-decoration: none;
            font-weight: 500;
            padding: 0.5rem 1rem;
            border-radius: 20px;
            transition: all 0.3s ease;
        }

        .nav-links a:hover {
            background-color: rgba(255, 255, 255, 0.2);
        }

        .menu-toggle { display: none; color: var(--white); font-size: 1.5rem; cursor: pointer; }

        .hero {
            padding: 100px 2rem 50px;
            background: linear-gradient(135deg, var(--primary-color), var(--primary-light));
            text-align: center;
        }

        .avatar-placeholder {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            background-color: var(--white);
            margin: 0 auto 2rem;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 8px 20px rgba(74, 144, 217, 0.3);
            border: 5px solid var(--white);
            overflow: hidden;
        }

        .avatar-placeholder img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 50%;
        }

        .hero h1 {
            font-size: 2.5rem;
            color: var(--white);
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(46, 92, 138, 0.3);
        }

        .hero p {
            font-size: 1.1rem;
            color: rgba(255, 255, 255, 0.9);
            margin-bottom: 1.5rem;
        }

        .tags {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 0.8rem;
        }

        .tag {
            background-color: var(--white);
            color: var(--primary-color);
            padding: 0.5rem 1.2rem;
            border-radius: 25px;
            font-size: 0.9rem;
            box-shadow: 0 2px 8px rgba(74, 144, 217, 0.2);
        }

        .guide-character {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            background: linear-gradient(135deg, var(--primary-color), var(--primary-light));
            padding: 1rem 1.5rem;
            border-radius: 25px;
            box-shadow: 0 6px 20px rgba(74, 144, 217, 0.3);
            display: flex;
            align-items: center;
            gap: 1rem;
            cursor: pointer;
            z-index: 1000;
            animation: float 3s ease-in-out infinite;
        }

        .guide-character .character { font-size: 2rem; }

        .guide-character .speech {
            background-color: var(--white);
            padding: 0.6rem 1.2rem;
            border-radius: 15px;
            font-size: 0.9rem;
            color: var(--primary-dark);
            max-width: 200px;
            position: relative;
        }

        .guide-character .speech::before {
            content: '';
            position: absolute;
            right: -8px;
            top: 50%;
            transform: translateY(-50%);
            border-left: 8px solid var(--white);
            border-top: 6px solid transparent;
            border-bottom: 6px solid transparent;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-8px); }
        }

        .section {
            padding: 4rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            font-size: 2rem;
            color: var(--primary-dark);
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            border-radius: 2px;
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
            box-shadow: 0 4px 15px rgba(74, 144, 217, 0.1);
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
            border: 2px solid var(--primary-light);
        }

        .language-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 8px 25px rgba(74, 144, 217, 0.2);
        }

        .language-card .flag { font-size: 3.5rem; margin-bottom: 1rem; }
        .language-card h3 { color: var(--primary-dark); margin-bottom: 0.5rem; font-size: 1.3rem; }

        .level {
            background: linear-gradient(135deg, var(--secondary-color), var(--accent-color));
            color: var(--primary-dark);
            padding: 0.4rem 1rem;
            border-radius: 20px;
            font-size: 0.85rem;
            display: inline-block;
            margin-bottom: 1rem;
            font-weight: bold;
        }

        .language-card p { color: var(--text-color); font-size: 0.95rem; }

        .lang-code {
            font-size: 2.8rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
            font-family: 'Arial Black', sans-serif;
        }

        .lang-code.fr { color: #8B5CF6; }
        .lang-code.gb { color: #4A90D9; }
        .lang-code.cn { color: #FF6B6B; }

        .notes-section {
            margin-top: 2rem;
            padding: 2rem;
            background-color: var(--white);
            border-radius: 20px;
            display: none;
            box-shadow: 0 6px 20px rgba(74, 144, 217, 0.1);
        }

        .notes-section.active { display: block; }

        .notes-section h3 {
            color: var(--primary-dark);
            margin-bottom: 1.5rem;
            font-size: 1.4rem;
        }

        .notes-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .note-card {
            background-color: var(--primary-light);
            border-radius: 15px;
            padding: 1.5rem;
            box-shadow: 0 4px 12px rgba(74, 144, 217, 0.1);
            transition: all 0.3s ease;
        }

        .note-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(74, 144, 217, 0.15);
        }

        .note-card h4 { color: var(--primary-dark); margin-bottom: 0.5rem; font-size: 1.1rem; }
        .note-card p { color: var(--text-color); font-size: 0.95rem; margin-bottom: 0.5rem; }
        .note-card img {
            max-width: 100%;
            max-height: 200px;
            object-fit: contain;
            border-radius: 12px;
            margin: 0.5rem 0;
        }
        .note-card .date { font-size: 0.85rem; color: var(--primary-color); }

        .note-actions { display: flex; gap: 0.5rem; margin-top: 1rem; }

        .btn-small {
            padding: 0.5rem 1rem;
            border: 2px solid var(--primary-color);
            border-radius: 10px;
            cursor: pointer;
            font-size: 0.85rem;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .btn-delete {
            background-color: var(--white);
            color: #FF6B6B;
            border-color: #FF6B6B;
        }

        .add-form {
            background-color: var(--primary-light);
            padding: 1.5rem;
            border-radius: 15px;
            margin-top: 1rem;
        }

        .add-form h4 { color: var(--primary-dark); margin-bottom: 1rem; font-size: 1.1rem; }

        .form-group { margin-bottom: 1rem; }

        .form-group label {
            display: block;
            margin-bottom: 0.3rem;
            color: var(--text-color);
            font-weight: 500;
            font-size: 0.95rem;
        }

        .form-group input, .form-group textarea {
            width: 100%;
            padding: 0.7rem;
            border: 2px solid var(--primary-color);
            border-radius: 10px;
            font-size: 0.95rem;
            font-family: inherit;
            background-color: var(--white);
            transition: all 0.3s ease;
        }

        .form-group input:focus, .form-group textarea:focus {
            outline: none;
            box-shadow: 0 0 0 3px rgba(74, 144, 217, 0.2);
        }

        .form-group textarea { min-height: 80px; resize: vertical; }

        .btn-primary {
            background: linear-gradient(135deg, var(--primary-color), var(--primary-dark));
            color: var(--white);
            padding: 0.8rem 1.8rem;
            border: none;
            border-radius: 15px;
            font-size: 1rem;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s ease;
            box-shadow: 0 4px 12px rgba(74, 144, 217, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(74, 144, 217, 0.4);
        }

        .project-timeline { position: relative; }

        .project-timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 4px;
            background: linear-gradient(180deg, var(--primary-color), var(--secondary-color));
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
            box-shadow: 0 4px 15px rgba(74, 144, 217, 0.1);
            max-width: 450px;
            border: 2px solid var(--primary-light);
            position: relative;
        }

        .project-content::before {
            content: '';
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            width: 20px;
            height: 20px;
            background-color: var(--primary-color);
            border-radius: 50%;
            border: 4px solid var(--white);
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.15);
        }

        .project-item:nth-child(odd) .project-content::before { right: -2.5rem; }
        .project-item:nth-child(even) .project-content::before { left: -2.5rem; }

        .project-content h3 { color: var(--primary-dark); margin-bottom: 0.5rem; font-size: 1.3rem; }
        .project-content .date {
            color: var(--primary-color);
            font-size: 0.9rem;
            margin-bottom: 1rem;
            font-weight: 500;
        }
        .project-content p { color: var(--text-color); font-size: 0.95rem; line-height: 1.7; }

        .travel-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; }

        .travel-card {
            background-color: var(--white);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(74, 144, 217, 0.1);
            transition: all 0.3s ease;
            position: relative;
        }

        .travel-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 8px 25px rgba(74, 144, 217, 0.15);
        }

        .travel-image {
            height: 260px;
            background: linear-gradient(135deg, var(--primary-color), var(--primary-light));
            overflow: hidden;
            position: relative;
        }

        .travel-image img { width: 100%; height: 100%; object-fit: cover; }

        .image-counter {
            position: absolute;
            left: 10px;
            bottom: 10px;
            background-color: rgba(255, 255, 255, 0.9);
            color: var(--primary-dark);
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
            color: var(--white);
            font-size: 2rem;
            text-shadow: 2px 2px 4px rgba(46, 92, 138, 0.8);
            transition: all 0.3s ease;
        }

        .travel-card:hover .travel-arrow-overlay { opacity: 1; }
        .travel-arrow-overlay:hover { transform: translateX(5px); }

        .travel-info { padding: 1.5rem; }
        .travel-info h3 { color: var(--primary-dark); margin-bottom: 0.5rem; font-size: 1.2rem; }
        .travel-info p { color: var(--text-color); font-size: 0.95rem; }

        .works-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 2rem; }

        .work-card {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 4px 15px rgba(74, 144, 217, 0.1);
            border: 2px solid var(--primary-light);
            transition: all 0.3s ease;
            cursor: pointer;
            text-align: center;
        }

        .work-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 8px 25px rgba(74, 144, 217, 0.15);
        }

        .work-card .work-icon { font-size: 3.5rem; margin-bottom: 1rem; }
        .work-card h3 { color: var(--primary-dark); margin-bottom: 0.5rem; font-size: 1.2rem; }
        .work-card p { color: var(--text-color); font-size: 0.95rem; }

        .thoughts-container { max-width: 800px; margin: 0 auto; }

        .thought-item {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 4px 15px rgba(74, 144, 217, 0.1);
            border: 2px solid var(--primary-light);
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

        .thought-item .date {
            color: var(--primary-color);
            font-size: 0.9rem;
            margin-bottom: 1rem;
            font-weight: 500;
        }
        .thought-item p { color: var(--text-color); line-height: 1.8; font-size: 1rem; }

        .add-thought-form {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 4px 15px rgba(74, 144, 217, 0.1);
            border: 2px solid var(--primary-light);
            margin-top: 2rem;
        }

        .add-thought-form textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid var(--primary-light);
            border-radius: 15px;
            font-family: inherit;
            font-size: 1rem;
            min-height: 100px;
            resize: vertical;
            background-color: var(--bg-color);
            transition: all 0.3s ease;
        }

        .add-thought-form textarea:focus {
            outline: none;
            border-color: var(--primary-color);
            box-shadow: 0 0 0 3px rgba(74, 144, 217, 0.2);
        }

        .message-board { max-width: 800px; margin: 0 auto; }

        .message-form {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 4px 15px rgba(74, 144, 217, 0.1);
            border: 2px solid var(--primary-light);
            margin-bottom: 2rem;
        }

        .message-form input, .message-form textarea {
            width: 100%;
            padding: 1rem;
            margin-bottom: 1rem;
            border: 2px solid var(--primary-light);
            border-radius: 15px;
            font-family: inherit;
            font-size: 1rem;
            background-color: var(--bg-color);
            transition: all 0.3s ease;
        }

        .message-form input:focus, .message-form textarea:focus {
            outline: none;
            border-color: var(--primary-color);
            box-shadow: 0 0 0 3px rgba(74, 144, 217, 0.2);
        }

        .message-form button {
            background: linear-gradient(135deg, var(--primary-color), var(--primary-dark));
            color: var(--white);
            border: none;
            padding: 1rem 2rem;
            border-radius: 30px;
            font-size: 1rem;
            cursor: pointer;
            font-weight: 500;
            width: 100%;
            box-shadow: 0 4px 12px rgba(74, 144, 217, 0.3);
        }

        .message-list { display: flex; flex-direction: column; gap: 1.5rem; }

        .message-item {
            background-color: var(--white);
            padding: 1.5rem;
            border-radius: 15px;
            box-shadow: 0 4px 12px rgba(74, 144, 217, 0.1);
            border: 2px solid var(--primary-light);
        }

        .message-item .message-header { display: flex; justify-content: space-between; margin-bottom: 1rem; }
        .message-item .message-name { font-weight: bold; color: var(--primary-dark); font-size: 1.1rem; }
        .message-item .message-date { font-size: 0.85rem; color: var(--primary-color); }
        .message-item p { color: var(--text-color); font-size: 1rem; }

        footer {
            background: linear-gradient(135deg, var(--primary-dark), var(--primary-color));
            color: var(--white);
            text-align: center;
            padding: 2rem;
            margin-top: 4rem;
        }

        .empty-state {
            text-align: center;
            padding: 3rem 2rem;
            color: var(--text-color);
            background-color: var(--bg-color);
            border-radius: 20px;
            border: 2px dashed var(--primary-light);
        }

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
        }
    </style>
</head>
<body>
    <nav>
        <div class="nav-container">
            <div class="logo">Ariel's World</div>
            <div class="menu-toggle" onclick="toggleMenu()"><i class="fas fa-bars"></i></div>
            <ul class="nav-links" id="navLinks">
                <li><a href="#home">🏠 首页</a></li>
                <li><a href="#language">📖 语言学习</a></li>
                <li><a href="#projects">💼 项目经历</a></li>
                <li><a href="#travel">🌍 探索世界</a></li>
                <li><a href="#works">🎨 个人作品</a></li>
                <li><a href="#thoughts">💭 碎碎念</a></li>
                <li><a href="#messages">📬 留言板</a></li>
            </ul>
        </div>
    </nav>

    <section id="home" class="hero">
        <div class="avatar-placeholder">
            <img src="images/首页照片.jpg" alt="Ariel" onerror="this.style.display='none'; this.parentElement.innerHTML='👩‍🎓';">
        </div>
        <h1>成长中的法专生 · Ariel</h1>
        <p>湖南师范大学外国语言文学专业 | 法语TCF C1 | 雅思7.5 | 自媒体博主</p>
        <div class="tags">
            <span class="tag">🌍 语言爱好者</span>
            <span class="tag">📚 终身学习</span>
            <span class="tag">🎬 内容创作</span>
        </div>
    </section>

    <div class="guide-character">
        <div class="character">👧</div>
        <div class="speech">你好，我是Ariel，欢迎来到我的个人网页！</div>
    </div>

    <section id="language" class="section">
        <h2 class="section-title">📖 语言学习</h2>
        <div class="language-cards">
            <div class="language-card" onclick="toggleNotes('french')">
                <div class="flag">🇫🇷</div>
                <div class="lang-code fr">FR</div>
                <h3>法语学习</h3>
                <span class="level">TCF C1</span>
                <p>专业学习四年，热爱法语文化</p>
            </div>
            <div class="language-card" onclick="toggleNotes('english')">
                <div class="flag">🇬🇧</div>
                <div class="lang-code gb">GB</div>
                <h3>英文学习</h3>
                <span class="level">雅思7.5</span>
                <p>日常交流无障碍，阅读能力优秀</p>
            </div>
            <div class="language-card" onclick="toggleNotes('chinese')">
                <div class="flag">🇨🇳</div>
                <div class="lang-code cn">CN</div>
                <h3>中文思考</h3>
                <span class="level">母语</span>
                <p>写作表达能力突出</p>
            </div>
        </div>

        <div class="notes-section" id="frenchNotes">
            <h3>🇫🇷 法语学习笔记</h3>
            <div class="notes-grid" id="frenchNotesGrid"></div>
            <div class="add-form">
                <h4>➕ 添加新笔记</h4>
                <form onsubmit="addNote('french'); return false;">
                    <div class="form-group">
                        <label>标题</label>
                        <input type="text" id="frenchTitle" placeholder="笔记标题" required>
                    </div>
                    <div class="form-group">
                        <label>内容</label>
                        <textarea id="frenchContent" placeholder="笔记内容"></textarea>
                    </div>
                    <button type="submit" class="btn-primary">保存</button>
                </form>
            </div>
        </div>

        <div class="notes-section" id="englishNotes">
            <h3>🇬🇧 英语学习笔记</h3>
            <div class="notes-grid" id="englishNotesGrid"></div>
            <div class="add-form">
                <h4>➕ 添加新笔记</h4>
                <form onsubmit="addNote('english'); return false;">
                    <div class="form-group">
                        <label>标题</label>
                        <input type="text" id="englishTitle" placeholder="笔记标题" required>
                    </div>
                    <div class="form-group">
                        <label>内容</label>
                        <textarea id="englishContent" placeholder="笔记内容"></textarea>
                    </div>
                    <button type="submit" class="btn-primary">保存</button>
                </form>
            </div>
        </div>

        <div class="notes-section" id="chineseNotes">
            <h3>🇨🇳 中文思考笔记</h3>
            <div class="notes-grid" id="chineseNotesGrid"></div>
            <div class="add-form">
                <h4>➕ 添加新笔记</h4>
                <form onsubmit="addNote('chinese'); return false;">
                    <div class="form-group">
                        <label>标题</label>
                        <input type="text" id="chineseTitle" placeholder="笔记标题" required>
                    </div>
                    <div class="form-group">
                        <label>内容</label>
                        <textarea id="chineseContent" placeholder="笔记内容"></textarea>
                    </div>
                    <button type="submit" class="btn-primary">保存</button>
                </form>
            </div>
        </div>
    </section>

    <section id="projects" class="section">
        <h2 class="section-title">💼 项目经历</h2>
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
    </section>

    <section id="travel" class="section">
        <h2 class="section-title">🌍 探索世界</h2>
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
    </section>

    <section id="works" class="section">
        <h2 class="section-title">🎨 个人作品</h2>
        <div class="works-grid">
            <div class="work-card" onclick="window.location.href='xiaohongshu.html'">
                <div class="work-icon">📕</div>
                <h3>小红书笔记</h3>
                <p>记录法语学习与生活点滴</p>
            </div>
            <div class="work-card" onclick="window.location.href='handmade.html'">
                <div class="work-icon">🎨</div>
                <h3>手工作品</h3>
                <p>创意手工与艺术创作</p>
            </div>
            <div class="work-card" onclick="window.location.href='food.html'">
                <div class="work-icon">🍳</div>
                <h3>美食分享</h3>
                <p>美食探店与烹饪心得</p>
            </div>
        </div>
    </section>

    <section id="thoughts" class="section">
        <h2 class="section-title">💭 Ariel的碎碎念</h2>
        <div class="thoughts-container">
            <div id="thoughtsList"></div>
            <div class="add-thought-form">
                <h3>分享你的想法 ✨</h3>
                <form onsubmit="addThought(); return false;">
                    <textarea id="newThought" placeholder="在这里写下你的碎碎念..." required></textarea>
                    <button type="submit" class="btn-primary" style="margin-top: 1rem; width: 100%;">发布</button>
                </form>
            </div>
        </div>
    </section>

    <section id="messages" class="section">
        <h2 class="section-title">📬 留言板</h2>
        <div class="message-board">
            <div class="message-form">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary-dark);">留下你的足迹 ✨</h3>
                <form onsubmit="addMessage(); return false;">
                    <input type="text" id="visitorName" placeholder="你的名字" required>
                    <textarea id="visitorMessage" placeholder="想对我说的话..." required></textarea>
                    <button type="submit" class="btn-primary">发送留言</button>
                </form>
            </div>
            <div class="message-list" id="messageList"></div>
        </div>
    </section>

    <footer>
        <p>Made with 💕 by Ariel | © 2024</p>
    </footer>

    <script>
        function toggleMenu() {
            const navLinks = document.getElementById('navLinks');
            navLinks.classList.toggle('active');
        }

        function toggleNotes(lang) {
            const notesSection = document.getElementById(lang + 'Notes');
            notesSection.classList.toggle('active');
        }

        function addNote(lang) {
            const title = document.getElementById(lang + 'Title').value;
            const content = document.getElementById(lang + 'Content').value;
            if (!title) return;

            const notes = JSON.parse(localStorage.getItem(lang + 'Notes') || '[]');
            notes.push({
                title,
                content,
                date: new Date().toLocaleDateString('zh-CN')
            });
            localStorage.setItem(lang + 'Notes', JSON.stringify(notes));

            document.getElementById(lang + 'Title').value = '';
            document.getElementById(lang + 'Content').value = '';
            loadNotes(lang);
        }

        function loadNotes(lang) {
            const notes = JSON.parse(localStorage.getItem(lang + 'Notes') || '[]');
            const grid = document.getElementById(lang + 'NotesGrid');

            if (notes.length === 0) {
                grid.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-sticky-note"></i>
                        <p>还没有笔记哦，快来添加第一篇吧！</p>
                    </div>
                `;
                return;
            }

            grid.innerHTML = notes.map((note, index) => `
                <div class="note-card">
                    <h4>${note.title}</h4>
                    <p>${note.content || '暂无内容'}</p>
                    <div class="date">📅 ${note.date}</div>
                    <div class="note-actions">
                        <button class="btn-small btn-delete" onclick="deleteNote('${lang}', ${index})">←</button>
                    </div>
                </div>
            `).join('');
        }

        function deleteNote(lang, index) {
            const notes = JSON.parse(localStorage.getItem(lang + 'Notes') || '[]');
            notes.splice(index, 1);
            localStorage.setItem(lang + 'Notes', JSON.stringify(notes));
            loadNotes(lang);
        }

        function addThought() {
            const content = document.getElementById('newThought').value;
            if (!content) return;

            const thoughts = JSON.parse(localStorage.getItem('thoughts') || '[]');
            thoughts.unshift({
                content,
                date: new Date().toLocaleDateString('zh-CN')
            });
            localStorage.setItem('thoughts', JSON.stringify(thoughts));
            document.getElementById('newThought').value = '';
            loadThoughts();
        }

        function loadThoughts() {
            const thoughts = JSON.parse(localStorage.getItem('thoughts') || '[]');
            const list = document.getElementById('thoughtsList');

            if (thoughts.length === 0) {
                list.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-comment-dots"></i>
                        <p>还没有碎碎念哦，快来分享你的想法吧！</p>
                    </div>
                `;
                return;
            }

            list.innerHTML = thoughts.map(thought => `
                <div class="thought-item">
                    <div class="date">📅 ${thought.date}</div>
                    <p>${thought.content}</p>
                </div>
            `).join('');
        }

        function addMessage() {
            const name = document.getElementById('visitorName').value;
            const message = document.getElementById('visitorMessage').value;
            if (!name || !message) return;

            const messages = JSON.parse(localStorage.getItem('messages') || '[]');
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

        function loadMessages() {
            const messages = JSON.parse(localStorage.getItem('messages') || '[]');
            const list = document.getElementById('messageList');

            if (messages.length === 0) {
                list.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-envelope-open"></i>
                        <p>还没有留言哦，快来留下你的足迹吧！</p>
                    </div>
                `;
                return;
            }

            list.innerHTML = messages.map(msg => `
                <div class="message-item">
                    <div class="message-header">
                        <span class="message-name">👤 ${msg.name}</span>
                        <span class="message-date">📅 ${msg.date}</span>
                    </div>
                    <p>${msg.message}</p>
                </div>
            `).join('');
        }

        function switchTravelImage(card) {
            const images = card.querySelector('.travel-images').querySelectorAll('img');
            const mainImg = card.querySelector('.travel-main-image');
            const counter = card.querySelector('.image-counter');
            let current = parseInt(counter.textContent.split('/')[0]);

            if (current >= images.length) {
                current = 0;
            }

            mainImg.src = images[current].src;
            counter.textContent = (current + 1) + '/' + images.length;
        }

        loadNotes('french');
        loadNotes('english');
        loadNotes('chinese');
        loadThoughts();
        loadMessages();
    </script>
</body>
</html>
