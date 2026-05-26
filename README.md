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
            background: linear-gradient(135deg, var(--primary-color), var(--primary-light));
            padding: 1rem 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(74, 144, 217, 0.3);
        }
        
        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo { font-size: 1.5rem; font-weight: bold; color: var(--white); }
        
        .nav-links {
            display: flex;
            list-style: none;
            gap: 0.5rem;
        }
        
        .nav-links a {
            color: var(--white);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 20px;
            white-space: nowrap;
        }
        
        .nav-links a:hover { background-color: rgba(255, 255, 255, 0.2); }
        .nav-links a.active { background-color: rgba(255, 255, 255, 0.3); }
        
        .menu-toggle { display: none; color: var(--white); font-size: 1.5rem; cursor: pointer; }
        
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
            width: 60px;
            height: 4px;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            border-radius: 2px;
        }
        
        .hero {
            padding: 120px 2rem 60px;
            background: linear-gradient(180deg, var(--primary-light), var(--bg-color));
            text-align: center;
        }
        
        .avatar-placeholder {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            margin: 0 auto 2rem;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 10px 30px rgba(74, 144, 217, 0.3);
            overflow: hidden;
        }
        
        .avatar-placeholder img { width: 100%; height: 100%; object-fit: cover; border-radius: 50%; }
        
        .hero h1 { font-size: 2.5rem; color: var(--primary-dark); margin-bottom: 1rem; }
        .hero p { font-size: 1.2rem; color: #666; margin-bottom: 1.5rem; }
        
        .tags { display: flex; flex-wrap: wrap; justify-content: center; gap: 0.5rem; }
        .tag { background-color: var(--accent-color); color: var(--primary-dark); padding: 0.5rem 1rem; border-radius: 20px; font-size: 0.9rem; }
        
        .guide-character {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            padding: 1rem 1.5rem;
            border-radius: 25px;
            box-shadow: 0 5px 20px rgba(74, 144, 217, 0.4);
            display: flex;
            align-items: center;
            gap: 1rem;
            cursor: pointer;
            z-index: 1000;
            animation: bounce 2s infinite;
        }
        
        .guide-character .character { font-size: 2rem; }
        
        .guide-character .speech {
            background-color: var(--white);
            padding: 0.5rem 1rem;
            border-radius: 15px;
            font-size: 0.9rem;
            color: var(--primary-dark);
            max-width: 200px;
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
        
        .language-cards { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 2rem; }
        
        .language-card {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 5px 20px rgba(74, 144, 217, 0.15);
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
        }
        
        .language-card:hover { transform: translateY(-5px); box-shadow: 0 10px 30px rgba(74, 144, 217, 0.25); }
        
        .language-card .flag { font-size: 3rem; margin-bottom: 1rem; }
        .language-card h3 { color: var(--primary-dark); margin-bottom: 0.5rem; }
        
        .level { background-color: var(--primary-light); color: var(--primary-color); padding: 0.3rem 0.8rem; border-radius: 15px; font-size: 0.8rem; display: inline-block; margin-bottom: 1rem; }
        .language-card p { color: #666; font-size: 0.9rem; }
        
        .lang-code { font-size: 2.5rem; font-weight: bold; margin-bottom: 0.5rem; font-family: 'Arial Black', sans-serif; }
        .lang-code.fr { color: #8B5CF6; }
        .lang-code.gb { color: #4A90D9; }
        .lang-code.cn { color: #FF6B6B; }
        
        .notes-section {
            margin-top: 2rem;
            padding: 2rem;
            background: var(--white);
            border-radius: 20px;
            display: none;
        }
        
        .notes-section.active { display: block; }
        
        .notes-section h3 { color: var(--primary-dark); margin-bottom: 1.5rem; font-size: 1.3rem; }
        
        .notes-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 1.5rem; margin-bottom: 2rem; }
        
        .note-card {
            background: var(--bg-color);
            border-radius: 12px;
            padding: 1.5rem;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            transition: all 0.3s ease;
        }
        
        .note-card:hover { transform: translateY(-3px); box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1); }
        
        .note-card h4 { color: var(--primary-dark); margin-bottom: 0.5rem; font-size: 1.1rem; }
        .note-card p { color: #666; font-size: 0.9rem; margin-bottom: 0.5rem; }
        .note-card img { max-width: 100%; max-height: 200px; object-fit: contain; border-radius: 8px; margin: 0.5rem 0; }
        .note-card .date { font-size: 0.8rem; color: #999; }
        
        .note-actions { display: flex; gap: 0.5rem; margin-top: 1rem; }
        .btn-small { padding: 0.4rem 0.8rem; border: none; border-radius: 6px; cursor: pointer; font-size: 0.8rem; }
        .btn-edit { background: var(--primary-light); color: var(--primary-color); }
        .btn-delete { background: #FFE4E4; color: #E74C3C; }
        
        .add-form { background: var(--bg-color); padding: 1.5rem; border-radius: 12px; margin-top: 1rem; }
        .add-form h4 { color: var(--primary-dark); margin-bottom: 1rem; }
        
        .form-group { margin-bottom: 1rem; }
        .form-group label { display: block; margin-bottom: 0.3rem; color: var(--text-color); font-weight: 500; font-size: 0.9rem; }
        .form-group input, .form-group textarea {
            width: 100%;
            padding: 0.6rem;
            border: 2px solid #E0E0E0;
            border-radius: 8px;
            font-size: 0.9rem;
            font-family: inherit;
        }
        .form-group input:focus, .form-group textarea:focus { outline: none; border-color: var(--primary-color); }
        .form-group textarea { min-height: 80px; resize: vertical; }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--primary-color), var(--primary-dark));
            color: var(--white);
            padding: 0.8rem 1.5rem;
            border: none;
            border-radius: 8px;
            font-size: 0.95rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 5px 15px rgba(74, 144, 217, 0.4); }
        
        .project-timeline { position: relative; }
        .project-timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(180deg, var(--primary-color), var(--secondary-color));
            transform: translateX(-50%);
        }
        
        .project-item { position: relative; margin-bottom: 3rem; display: flex; justify-content: center; }
        
        .project-item:nth-child(odd) .project-content { margin-right: calc(50% + 2rem); text-align: right; }
        .project-item:nth-child(even) .project-content { margin-left: calc(50% + 2rem); }
        
        .project-content {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 5px 20px rgba(74, 144, 217, 0.15);
            max-width: 450px;
        }
        
        .project-content h3 { color: var(--primary-dark); margin-bottom: 0.5rem; }
        .project-content .date { color: var(--primary-color); font-size: 0.9rem; margin-bottom: 1rem; }
        .project-content p { color: #666; font-size: 0.95rem; line-height: 1.7; }
        
        .travel-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; }
        
        .travel-card {
            background-color: var(--white);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(74, 144, 217, 0.15);
            transition: all 0.3s ease;
        }
        
        .travel-card:hover { transform: translateY(-5px); box-shadow: 0 10px 30px rgba(74, 144, 217, 0.25); }
        
        .travel-image {
            height: 280px;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            overflow: hidden;
            position: relative;
        }
        
        .travel-image img { width: 100%; height: 100%; object-fit: cover; }
        
        .image-counter {
            position: absolute;
            left: 10px;
            bottom: 10px;
            background-color: rgba(0, 0, 0, 0.5);
            color: white;
            padding: 4px 10px;
            border-radius: 15px;
            font-size: 0.8rem;
        }
        
        .travel-arrow-overlay {
            position: absolute;
            right: 12px;
            bottom: 12px;
            cursor: pointer;
            opacity: 0;
            color: rgba(255, 255, 255, 0.9);
            font-size: 1.8rem;
            text-shadow: 0 1px 3px rgba(0, 0, 0, 0.4);
            transition: all 0.3s ease;
        }
        
        .travel-card:hover .travel-arrow-overlay { opacity: 1; }
        .travel-arrow-overlay:hover { transform: translateX(5px); color: white; }
        
        .travel-info { padding: 1.5rem; }
        .travel-info h3 { color: var(--primary-dark); margin-bottom: 0.5rem; }
        .travel-info p { color: #666; font-size: 0.9rem; }
        
        .works-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 2rem; }
        
        .work-card {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 5px 20px rgba(74, 144, 217, 0.15);
            transition: all 0.3s ease;
            cursor: pointer;
            text-align: center;
        }
        
        .work-card:hover { transform: translateY(-5px); box-shadow: 0 10px 30px rgba(74, 144, 217, 0.25); }
        .work-card .work-icon { font-size: 3rem; margin-bottom: 1rem; }
        .work-card h3 { color: var(--primary-dark); margin-bottom: 0.5rem; }
        .work-card p { color: #666; font-size: 0.9rem; }
        
        .thoughts-container { max-width: 800px; margin: 0 auto; }
        
        .thought-item {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 5px 20px rgba(74, 144, 217, 0.15);
            margin-bottom: 2rem;
        }
        
        .thought-item .date { color: var(--primary-color); font-size: 0.9rem; margin-bottom: 1rem; }
        .thought-item p { color: #666; line-height: 1.8; }
        
        .add-thought-form { background: var(--white); padding: 2rem; border-radius: 20px; box-shadow: 0 5px 20px rgba(74, 144, 217, 0.15); margin-top: 2rem; }
        .add-thought-form textarea { width: 100%; padding: 1rem; border: 2px solid var(--primary-light); border-radius: 10px; font-family: inherit; font-size: 1rem; min-height: 100px; resize: vertical; }
        .add-thought-form textarea:focus { outline: none; border-color: var(--primary-color); }
        
        .message-board { max-width: 800px; margin: 0 auto; }
        
        .message-form {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 5px 20px rgba(74, 144, 217, 0.15);
            margin-bottom: 2rem;
        }
        
        .message-form input, .message-form textarea {
            width: 100%;
            padding: 1rem;
            margin-bottom: 1rem;
            border: 2px solid var(--primary-light);
            border-radius: 10px;
            font-family: inherit;
            font-size: 1rem;
        }
        
        .message-form input:focus, .message-form textarea:focus { outline: none; border-color: var(--primary-color); }
        .message-form button { background: linear-gradient(135deg, var(--primary-color), var(--primary-dark)); color: var(--white); border: none; padding: 1rem 2rem; border-radius: 30px; font-size: 1rem; cursor: pointer; width: 100%; }
        
        .message-list { display: flex; flex-direction: column; gap: 1.5rem; }
        
        .message-item {
            background-color: var(--white);
            padding: 1.5rem;
            border-radius: 15px;
            box-shadow: 0 3px 15px rgba(74, 144, 217, 0.1);
        }
        
        .message-item .message-header { display: flex; justify-content: space-between; margin-bottom: 1rem; }
        .message-item .message-name { font-weight: bold; color: var(--primary-dark); }
        .message-item .message-date { font-size: 0.8rem; color: #999; }
        .message-item p { color: #666; }
        
        footer {
            background: linear-gradient(135deg, var(--primary-dark), var(--primary-color));
            color: var(--white);
            text-align: center;
            padding: 2rem;
            margin-top: 4rem;
        }
        
        .empty-state { text-align: center; padding: 3rem 2rem; color: #999; background: var(--bg-color); border-radius: 12px; }
        .empty-state i { font-size: 3rem; margin-bottom: 1rem; opacity: 0.5; }
        
        @media (max-width: 768px) {
            .nav-links { display: none; flex-direction: column; position: absolute; top: 60px; left: 0; width: 100%; background-color: var(--primary-color); padding: 1rem; }
            .nav-links.active { display: flex; }
            .menu-toggle { display: block; }
            
            .hero h1 { font-size: 2rem; }
            
            .project-timeline::before { left: 20px; }
            .project-item:nth-child(odd) .project-content, .project-item:nth-child(even) .project-content { margin-left: 50px; margin-right: 0; text-align: left; }
            
            .guide-character { position: fixed; bottom: 1rem; right: 1rem; padding: 0.8rem 1.2rem; }
            .guide-character .speech { max-width: 150px; font-size: 0.8rem; }
        }
    </style>
</head>
<body>
    <nav>
        <div class="nav-container">
            <div class="logo">🌟 Ariel</div>
            <div class="menu-toggle" onclick="toggleMenu()"><i class="fas fa-bars"></i></div>
            <ul class="nav-links" id="navLinks">
                <li><a href="#home">首页</a></li>
                <li><a href="#language">语言学习</a></li>
                <li><a href="#projects">项目经历</a></li>
                <li><a href="#travel">探索世界</a></li>
                <li><a href="#works">个人作品</a></li>
                <li><a href="#thoughts">碎碎念</a></li>
                <li><a href="#messages">留言板</a></li>
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
        <h2 class="section-title">🌏 探索世界</h2>
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
            <div class="work-card" onclick="toggleNotes('xiaohongshu')">
                <div class="work-icon">📕</div>
                <h3>小红书笔记</h3>
                <p>分享生活、学习、旅行的美好点滴</p>
            </div>
            <div class="work-card" onclick="toggleNotes('handmade')">
                <div class="work-icon">🧶</div>
                <h3>手工作品</h3>
                <p>DIY手工制作，编织美好时光</p>
            </div>
            <div class="work-card" onclick="toggleNotes('food')">
                <div class="work-icon">🍰</div>
                <h3>美食</h3>
                <p>美食探索与烹饪分享</p>
            </div>
        </div>
        
        <div class="notes-section" id="xiaohongshuNotes">
            <h3>📕 小红书笔记</h3>
            <div class="notes-grid" id="xiaohongshuNotesGrid"></div>
            <div class="add-form">
                <h4>➕ 添加新笔记</h4>
                <form onsubmit="addNote('xiaohongshu'); return false;">
                    <div class="form-group">
                        <label>标题</label>
                        <input type="text" id="xiaohongshuTitle" placeholder="笔记标题" required>
                    </div>
                    <div class="form-group">
                        <label>内容</label>
                        <textarea id="xiaohongshuContent" placeholder="笔记内容"></textarea>
                    </div>
                    <div class="form-group">
                        <label>图片URL（可选）</label>
                        <input type="text" id="xiaohongshuImage" placeholder="图片链接">
                    </div>
                    <button type="submit" class="btn-primary">保存</button>
                </form>
            </div>
        </div>
        
        <div class="notes-section" id="handmadeNotes">
            <h3>🧶 手工作品</h3>
            <div class="notes-grid" id="handmadeNotesGrid"></div>
            <div class="add-form">
                <h4>➕ 添加新作品</h4>
                <form onsubmit="addNote('handmade'); return false;">
                    <div class="form-group">
                        <label>标题</label>
                        <input type="text" id="handmadeTitle" placeholder="作品标题" required>
                    </div>
                    <div class="form-group">
                        <label>描述</label>
                        <textarea id="handmadeContent" placeholder="作品描述"></textarea>
                    </div>
                    <div class="form-group">
                        <label>图片URL（可选）</label>
                        <input type="text" id="handmadeImage" placeholder="图片链接">
                    </div>
                    <button type="submit" class="btn-primary">保存</button>
                </form>
            </div>
        </div>
        
        <div class="notes-section" id="foodNotes">
            <h3>🍰 美食分享</h3>
            <div class="notes-grid" id="foodNotesGrid"></div>
            <div class="add-form">
                <h4>➕ 添加美食</h4>
                <form onsubmit="addNote('food'); return false;">
                    <div class="form-group">
                        <label>标题</label>
                        <input type="text" id="foodTitle" placeholder="美食名称" required>
                    </div>
                    <div class="form-group">
                        <label>描述</label>
                        <textarea id="foodContent" placeholder="美食描述"></textarea>
                    </div>
                    <div class="form-group">
                        <label>图片URL（可选）</label>
                        <input type="text" id="foodImage" placeholder="图片链接">
                    </div>
                    <button type="submit" class="btn-primary">保存</button>
                </form>
            </div>
        </div>
    </section>
    
    <section id="thoughts" class="section">
        <h2 class="section-title">💭 Ariel的碎碎念</h2>
        <div class="thoughts-container" id="thoughtsList"></div>
        
        <div class="add-thought-form">
            <form onsubmit="addThought(); return false;">
                <textarea id="thoughtContent" placeholder="分享你的想法..." required></textarea>
                <button type="submit" class="btn-primary" style="margin-top: 1rem;">发布</button>
            </form>
        </div>
    </section>
    
    <section id="messages" class="section">
        <h2 class="section-title">📬 留言板</h2>
        <div class="message-board">
            <div class="message-form">
                <input type="text" id="messageName" placeholder="您的名字" required>
                <textarea id="messageContent" placeholder="留下您想说的话..." required></textarea>
                <button onclick="addMessage()" class="btn-primary">发送留言</button>
            </div>
            <div class="message-list" id="messageList"></div>
        </div>
    </section>
    
    <footer>
        <p>&copy; 2024 Ariel's Personal Website. Made with 💙</p>
    </footer>
    
    <script>
        function toggleMenu() {
            document.getElementById('navLinks').classList.toggle('active');
        }
        
        function toggleNotes(type) {
            const section = document.getElementById(type + 'Notes');
            section.classList.toggle('active');
            if (section.classList.contains('active')) {
                loadNotes(type);
                section.scrollIntoView({ behavior: 'smooth', block: 'start' });
            }
        }
        
        function loadNotes(type) {
            const notes = JSON.parse(localStorage.getItem(type + '_notes')) || [];
            const grid = document.getElementById(type + 'NotesGrid');
            
            if (notes.length === 0) {
                grid.innerHTML = '<div class="empty-state"><i class="fas fa-book"></i><p>暂无笔记，点击下方添加第一篇吧！</p></div>';
                return;
            }
            
            grid.innerHTML = notes.map((note, index) => `
                <div class="note-card">
                    ${note.image ? '<img src="${note.image}" alt="${note.title}" onerror="this.style.display=\'none\';">' : ''}
                    <h4>${note.title}</h4>
                    ${note.content ? '<p>' + note.content + '</p>' : ''}
                    <span class="date">${note.date}</span>
                    <div class="note-actions">
                        <button class="btn-small btn-edit" onclick="editNote('${type}', ${index})">编辑</button>
                        <button class="btn-small btn-delete" onclick="deleteNote('${type}', ${index})">删除</button>
                    </div>
                </div>
            `).join('');
        }
        
        function addNote(type) {
            const title = document.getElementById(type + 'Title').value.trim();
            const content = document.getElementById(type + 'Content').value.trim();
            const image = document.getElementById(type + 'Image')?.value.trim() || '';
            
            if (!title) { alert('请填写标题'); return; }
            
            const notes = JSON.parse(localStorage.getItem(type + '_notes')) || [];
            notes.unshift({ title, content, image, date: new Date().toLocaleDateString('zh-CN') });
            localStorage.setItem(type + '_notes', JSON.stringify(notes));
            
            document.getElementById(type + 'Title').value = '';
            document.getElementById(type + 'Content').value = '';
            if (document.getElementById(type + 'Image')) document.getElementById(type + 'Image').value = '';
            
            loadNotes(type);
            alert('保存成功！');
        }
        
        function editNote(type, index) {
            const notes = JSON.parse(localStorage.getItem(type + '_notes')) || [];
            const note = notes[index];
            
            const newTitle = prompt('修改标题：', note.title);
            if (newTitle === null) return;
            const newContent = prompt('修改内容：', note.content);
            if (newContent === null) return;
            
            notes[index] = { ...note, title: newTitle.trim() || note.title, content: newContent.trim() || note.content };
            localStorage.setItem(type + '_notes', JSON.stringify(notes));
            loadNotes(type);
            alert('修改成功！');
        }
        
        function deleteNote(type, index) {
            if (!confirm('确定要删除吗？')) return;
            const notes = JSON.parse(localStorage.getItem(type + '_notes')) || [];
            notes.splice(index, 1);
            localStorage.setItem(type + '_notes', JSON.stringify(notes));
            loadNotes(type);
            alert('已删除！');
        }
        
        function loadThoughts() {
            const thoughts = JSON.parse(localStorage.getItem('thoughts')) || [
                { content: '今天学习了新的法语语法点，过去分词的配合真的很让人头疼呢！不过熟能生巧，继续加油！💪', date: '2024年1月15日' },
                { content: '收到了粉丝的私信，说我的学习笔记帮助到了TA，真的很开心！这就是分享的意义吧~ ❤️', date: '2024年1月10日' },
                { content: '准备开始学习法语歌曲，既能练习发音又能了解法国文化，一举两得！🎶', date: '2024年1月5日' }
            ];
            
            document.getElementById('thoughtsList').innerHTML = thoughts.map(t => `
                <div class="thought-item">
                    <div class="date">${t.date}</div>
                    <p>${t.content}</p>
                </div>
            `).join('');
        }
        
        function addThought() {
            const content = document.getElementById('thoughtContent').value.trim();
            if (!content) { alert('请输入内容'); return; }
            
            const thoughts = JSON.parse(localStorage.getItem('thoughts')) || [];
            thoughts.unshift({ content, date: new Date().toLocaleDateString('zh-CN') });
            localStorage.setItem('thoughts', JSON.stringify(thoughts));
            
            document.getElementById('thoughtContent').value = '';
            loadThoughts();
            alert('发布成功！');
        }
        
        function loadMessages() {
            const messages = JSON.parse(localStorage.getItem('messages')) || [
                { name: '小明', content: '加油！你的法语学习分享真的很有帮助！🎉', date: '2024年1月14日' },
                { name: '法语爱好者', content: '希望能看到更多关于法国文化的内容！😊', date: '2024年1月13日' }
            ];
            
            document.getElementById('messageList').innerHTML = messages.map(m => `
                <div class="message-item">
                    <div class="message-header">
                        <span class="message-name">${m.name}</span>
                        <span class="message-date">${m.date}</span>
                    </div>
                    <p>${m.content}</p>
                </div>
            `).join('');
        }
        
        function addMessage() {
            const name = document.getElementById('messageName').value.trim();
            const content = document.getElementById('messageContent').value.trim();
            
            if (!name || !content) { alert('请填写姓名和留言内容'); return; }
            
            const messages = JSON.parse(localStorage.getItem('messages')) || [];
            messages.unshift({ name, content, date: new Date().toLocaleDateString('zh-CN') });
            localStorage.setItem('messages', JSON.stringify(messages));
            
            document.getElementById('messageName').value = '';
            document.getElementById('messageContent').value = '';
            loadMessages();
            alert('留言成功！');
        }
        
        function switchTravelImage(card) {
            const images = card.querySelectorAll('.travel-images img');
            const mainImg = card.querySelector('.travel-main-image');
            const counter = card.querySelector('.image-counter');
            
            if (images.length === 0) return;
            
            let currentIndex = 0;
            for (let i = 0; i < images.length; i++) {
                if (images[i].src === mainImg.src) {
                    currentIndex = i;
                    break;
                }
            }
            
            currentIndex = (currentIndex + 1) % images.length;
            mainImg.src = images[currentIndex].src;
            counter.textContent = (currentIndex + 1) + '/' + images.length;
        }
        
        loadThoughts();
        loadMessages();
    </script>
</body>
</html>
