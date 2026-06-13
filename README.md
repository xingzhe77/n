[b.html](https://github.com/user-attachments/files/28911603/b.html)
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🎓 毕业祝福</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Microsoft YaHei', sans-serif;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }
        
        .container {
            max-width: 800px;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            overflow: hidden;
            animation: fadeIn 1s ease-out;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .header {
            text-align: center;
            padding: 30px 20px;
            color: white;
        }
        
        .title {
            font-size: 2.5rem;
            font-weight: bold;
            margin-bottom: 8px;
        }
        
        .subtitle {
            font-size: 1.1rem;
            opacity: 0.9;
        }
        
        .content {
            padding: 30px;
        }
        
        .message {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 25px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .message p {
            margin-bottom: 15px;
            font-size: 1.1rem;
            color: #2c3e50;
            line-height: 1.6;
        }
        
        .footer {
            text-align: center;
            padding: 15px;
            background: #f8f9fa;
            color: #7f8c8d;
            font-size: 0.9rem;
        }
        
        /* 弹窗样式 */
        .popup-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.85);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.5s ease;
        }
        
        .popup-overlay.active {
            opacity: 1;
            visibility: visible;
        }
        
        .popup-content {
            background: white;
            border-radius: 20px;
            padding: 40px;
            max-width: 500px;
            width: 90%;
            text-align: center;
            position: relative;
            transform: translateY(20px);
            transition: transform 0.5s ease;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
        }
        
        .popup-overlay.active .popup-content {
            transform: translateY(0);
        }
        
        .popup-icon {
            font-size: 4rem;
            margin-bottom: 15px;
            animation: pulse 1.5s ease-in-out infinite;
        }
        
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }
        
        .popup-title {
            font-size: 1.8rem;
            color: #2c3e50;
            margin-bottom: 15px;
            font-weight: bold;
        }
        
        .popup-message {
            font-size: 1.3rem;
            color: #34495e;
            margin-bottom: 25px;
            line-height: 1.6;
            min-height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .popup-countdown {
            font-size: 1rem;
            color: #7f8c8d;
            margin-top: 20px;
        }
        
        .popup-progress {
            width: 100%;
            height: 4px;
            background: #e0e0e0;
            border-radius: 2px;
            margin-top: 15px;
            overflow: hidden;
        }
        
        .popup-progress-bar {
            height: 100%;
            background: linear-gradient(90deg, #667eea, #764ba2);
            border-radius: 2px;
            transition: width 0.1s linear;
        }
        
        .popup-counter {
            font-size: 0.9rem;
            color: #95a5a6;
            margin-top: 10px;
        }
        
        @media (max-width: 768px) {
            .title { font-size: 2rem; }
            .content { padding: 20px; }
            .popup-content { padding: 25px; }
            .popup-title { font-size: 1.5rem; }
            .popup-message { font-size: 1.1rem; }
            .popup-icon { font-size: 3rem; }
        }
    </style>
</head>
<body>
    <!-- 弹窗层 -->
    <div class="popup-overlay" id="popupOverlay">
        <div class="popup-content">
            <div class="popup-icon" id="popupIcon">💖</div>
            <h2 class="popup-title" id="popupTitle">暖心祝福</h2>
            <div class="popup-message" id="popupMessage">
                正在加载暖心文案...
            </div>
            <div class="popup-progress">
                <div class="popup-progress-bar" id="popupProgressBar"></div>
            </div>
            <div class="popup-countdown" id="popupCountdown">
                3秒后自动切换
            </div>
            <div class="popup-counter" id="popupCounter">
                1 / 20
            </div>
        </div>
    </div>
    
    <!-- 祝福页面 -->
    <div class="container" id="blessingContainer" style="display: none;">
        <div class="header" id="header">
            <h1 class="title">🎓 毕业祝福</h1>
            <p class="subtitle">致秋儿姐 · 来自全体同学</p>
        </div>
        <div class="content">
            <div class="message" id="message">
                <p>亲爱的同学们，</p>
                <p>&nbsp;</p>
                <p>今天，我们在这里送别秋儿姐。</p>
                <p>&nbsp;</p>
                <p>秋儿姐是我们大四学年里的一束光，她总在我们为论文焦头烂额时，</p>
                <p>分享高效的文献检索技巧；在我们对实习迷茫无措时，耐心分析行业前景，</p>
                <p>推荐靠谱的内推机会。</p>
                <p>&nbsp;</p>
                <p>她是社团里的"定海神针"，组织活动时总能兼顾细节与大局。</p>
                <p>她也是生活里的"暖心达人"，谁生日了会悄悄准备小惊喜。</p>
                <p>&nbsp;</p>
                <p>如今，秋儿姐即将踏上新的征程，我们不舍却也满怀祝福。</p>
                <p>愿你在未来的人生路上，继续如这般热烈、这般温暖，</p>
                <p>所行皆坦途，所求皆如愿。秋儿姐，毕业快乐，我们会想你的！</p>
            </div>
        </div>
        <div class="footer">
            <p id="footerText">🎓 毕业纪念 · 2024年06月09日</p>
        </div>
    </div>

    <script>
        // 暖心文案库 (100条精选)
        const warmMessages = [
            "🎓 毕业不是结束，而是新篇章的开始",
            "💖 感谢相遇，让我们的青春如此精彩",
            "✨ 愿你前程似锦，归来仍是少年",
            "🌟 每一段旅程都有终点，但友谊没有",
            "🌻 愿你在未来的日子里，光芒万丈",
            "🌸 青春不散场，梦想正启航",
            "🌊 愿你乘风破浪，勇往直前",
            "☀️ 愿你的未来如阳光般灿烂",
            "🌙 愿你的夜晚有星光相伴",
            "🌈 愿你的生活如彩虹般绚丽",
            "🍀 愿幸运常伴你左右",
            "💪 愿你勇敢追梦，无所畏惧",
            "📚 知识是力量，愿你学以致用",
            "🎨 愿你的人生如画，色彩斑斓",
            "🎵 愿你的生活如歌，旋律优美",
            "🌳 愿你如大树般茁壮成长",
            "🦋 愿你如蝴蝶般自由飞翔",
            "🐦 愿你如鸟儿般展翅高飞",
            "🌹 愿你如玫瑰般美丽绽放",
            "🌲 愿你如松柏般坚韧不拔",
            "💧 愿你如清泉般清澈纯净",
            "🔥 愿你如火焰般热情奔放",
            "❄️ 愿你如雪花般纯洁无瑕",
            "🌪️ 愿你如风暴般充满力量",
            "🌌 愿你如星空般深邃广阔",
            "🌅 愿你如日出般充满希望",
            "🌄 愿你如日落般温柔宁静",
            "🌠 愿你如流星般闪耀瞬间",
            "🌍 愿你如地球般包容万物",
            "🌕 愿你如满月般圆满美好",
            "🌖 愿你如新月般充满期待",
            "🌗 愿你如弦月般优雅动人",
            "🌘 愿你如残月般神秘迷人",
            "🌑 愿你如新月般重新开始",
            "🌒 愿你如蛾眉月般温柔细腻",
            "🌓 愿你如上弦月般充满活力",
            "🌔 愿你如盈凸月般丰盈充实",
            "🌙 愿你的梦想如月光般照亮前路",
            "☀️ 愿你的热情如阳光般温暖人心",
            "⭐ 愿你的才华如星辰般闪耀",
            "🌟 愿你的未来如星光般璀璨",
            "💫 愿你的生活如流星般精彩",
            "🌠 愿你的梦想如彗星般实现",
            "☁️ 愿你的心情如白云般轻松",
            "⛈️ 愿你的勇气如雷雨般强大",
            "🌧️ 愿你的泪水如春雨般滋润",
            "🌦️ 愿你的生活如雨后彩虹般美丽",
            "🌤️ 愿你的日子如晴天般明朗",
            "⛅ 愿你的心情如多云转晴般愉悦",
            "🌥️ 愿你的困难如云朵般消散",
            "🌨️ 愿你的坚持如雪花般积累",
            "❄️ 愿你的纯洁如冰雪般无暇",
            "🌬️ 愿你的思想如清风般自由",
            "💨 愿你的行动如疾风般迅速",
            "🌪️ 愿你的决心如龙卷风般强大",
            "🌀 愿你的生活如漩涡般精彩",
            "🌈 愿你的未来如彩虹般多彩",
            "☔ 愿你的困难如雨伞般被遮挡",
            "⛱️ 愿你的生活如沙滩般舒适",
            "🏖️ 愿你的心情如海浪般欢快",
            "🌊 愿你的勇气如海洋般深邃",
            "🏝️ 愿你的梦想如岛屿般实现",
            "⛰️ 愿你的目标如山峰般高远",
            "🏔️ 愿你的坚持如雪山般坚定",
            "🌋 愿你的热情如火山般爆发",
            "🏜️ 愿你的毅力如沙漠般坚韧",
            "🏞️ 愿你的生活如风景般美丽",
            "🌅 愿你的每一天如日出般崭新",
            "🌄 愿你的每一夜如日落般宁静",
            "🌇 愿你的城市如晚霞般绚丽",
            "🌆 愿你的生活如夜景般迷人",
            "🌃 愿你的梦想如星空般浩瀚",
            "🌉 愿你的未来如桥梁般通达",
            "🎆 愿你的成功如烟花般灿烂",
            "🎇 愿你的生活如烟火般精彩",
            "✨ 愿你的每一天都闪闪发光",
            "💫 愿你的每一个梦想都能实现",
            "🌟 愿你的每一份努力都有回报",
            "⭐ 愿你的每一次尝试都有收获",
            "🌠 愿你的每一段旅程都有意义",
            "💖 愿你的每一份感情都有回应",
            "💕 愿你的每一份付出都有回报",
            "💞 愿你的每一份爱都被珍惜",
            "💓 愿你的每一次心跳都有意义",
            "💗 愿你的每一天都充满爱心",
            "💘 愿你的爱情如箭般命中",
            "💝 愿你的生活如礼物般惊喜",
            "💟 愿你的心灵如符号般纯洁",
            "☮️ 愿你的世界如和平般美好",
            "☯️ 愿你的生活如阴阳般平衡",
            "🕉️ 愿你的心灵如梵文般神圣",
            "✡️ 愿你的信仰如星般坚定",
            "🔯 愿你的智慧如星般闪耀",
            "🕎 愿你的光明如烛台般照亮",
            "☸️ 愿你的道路如法轮般顺畅",
            "☪️ 愿你的信仰如新月般纯洁",
            "🛐 愿你的祈祷如圣地般神圣",
            "⛎ 愿你的命运如蛇夫般神秘",
            "♈ 愿你的勇气如白羊般无畏",
            "♉ 愿你的坚持如金牛般坚定",
            "♊ 愿你的智慧如双子般灵活"
        ];
        
        // 弹窗图标库
        const popupIcons = ["💖", "✨", "🌟", "🎓", "🌸", "🌻", "💫", "🎉", "💝", "🌈", "🦋", "🌹", "⭐", "🎀", "💎", "🔥", "🍀", "🎵", "💪", "🌙"];
        
        // 弹窗相关变量
        let popupInterval = null;
        let currentPopupIndex = 0;
        let popupMessages = [];
        let popupTimer = 3;
        let progressInterval = null;
        
        // 解析URL参数
        function getUrlParams() {
            const params = {};
            const queryString = window.location.hash ? window.location.hash.substring(1) : window.location.search.substring(1);
            const pairs = queryString.split('&');
            
            for (const pair of pairs) {
                const [key, value] = pair.split('=');
                if (key && value) {
                    params[key] = decodeURIComponent(value);
                }
            }
            
            return params;
        }
        
        // 颜色映射
        const colorMap = {
            'p': 'linear-gradient(135deg, #667eea 0%, #764ba2 100%)',  // 紫色
            'b': 'linear-gradient(135deg, #3498db 0%, #2980b9 100%)',  // 蓝色
            'g': 'linear-gradient(135deg, #2ecc71 0%, #27ae60 100%)',  // 绿色
            'r': 'linear-gradient(135deg, #e74c3c 0%, #c0392b 100%)',  // 红色
            'o': 'linear-gradient(135deg, #f39c12 0%, #e67e22 100%)'   // 橙色
        };
        
        // 默认祝福内容
        const defaultMessage = [
            "亲爱的话秋儿姐：",
            "",
            "展信安！",
            "",
            "今天，我在这里送别秋儿姐。",
            "",
            "秋儿姐你是我大学三年里的一束光，我觉得遇你到是一件非常幸运的事，",
            "大一啥也不懂，你给我描绘了一个从未见过，却向往已久的世界。",
            "我们一起去西昌古楼时候的场景一直铭记，我觉得我做过最正确的决定就是去西昌回访。",
            "",
            "如今，秋儿姐即将踏上新的征程，我们不舍却也满怀祝福。",
            "愿你在未来的人生路上，继续如这般热烈、这般温暖，",
            "所行皆坦途，所求皆如愿。秋儿姐，毕业快乐，生活顺遂！",
            "",
            "                                          6月14日",
            "                                           小家文"
        ];
        
        // 显示弹窗序列
        function showPopupSequence() {
            // 随机选择20条文案
            popupMessages = [...warmMessages]
                .sort(() => Math.random() - 0.5)
                .slice(0, 20);
            
            currentPopupIndex = 0;
            showNextPopup();
        }
        
        // 显示下一个弹窗
        function showNextPopup() {
            if (currentPopupIndex >= popupMessages.length) {
                // 所有弹窗显示完毕，显示祝福页面
                closePopup();
                showBlessingPage();
                return;
            }
            
            // 随机选择图标
            const randomIcon = popupIcons[Math.floor(Math.random() * popupIcons.length)];
            document.getElementById('popupIcon').textContent = randomIcon;
            
            // 显示弹窗
            document.getElementById('popupOverlay').classList.add('active');
            document.getElementById('popupMessage').textContent = popupMessages[currentPopupIndex];
            document.getElementById('popupCounter').textContent = `${currentPopupIndex + 1} / ${popupMessages.length}`;
            
            // 重置计时器
            popupTimer = 3;
            document.getElementById('popupCountdown').textContent = `${popupTimer}秒后自动切换`;
            
            // 重置进度条
            const progressBar = document.getElementById('popupProgressBar');
            progressBar.style.width = '100%';
            
            // 清除之前的定时器
            if (popupInterval) clearInterval(popupInterval);
            if (progressInterval) clearInterval(progressInterval);
            
            // 进度条动画
            const startTime = Date.now();
            const duration = 3000; // 3秒
            
            progressInterval = setInterval(() => {
                const elapsed = Date.now() - startTime;
                const progress = Math.max(0, 100 - (elapsed / duration) * 100);
                progressBar.style.width = progress + '%';
                
                if (elapsed >= duration) {
                    clearInterval(progressInterval);
                }
            }, 50);
            
            // 倒计时
            popupInterval = setInterval(() => {
                popupTimer--;
                document.getElementById('popupCountdown').textContent = `${popupTimer}秒后自动切换`;
                
                if (popupTimer <= 0) {
                    currentPopupIndex++;
                    showNextPopup();
                }
            }, 1000);
        }
        
        // 关闭弹窗
        function closePopup() {
            document.getElementById('popupOverlay').classList.remove('active');
            if (popupInterval) {
                clearInterval(popupInterval);
                popupInterval = null;
            }
            if (progressInterval) {
                clearInterval(progressInterval);
                progressInterval = null;
            }
        }
        
        // 显示祝福页面
        function showBlessingPage() {
            const params = getUrlParams();
            
            // 获取参数值
            const to = params.t || '秋儿姐';
            const from = params.f || '全体同学';
            const color = params.c || 'p';
            const message = params.m || '';
            
            // 设置标题
            document.querySelector('.title').textContent = '🎓 毕业祝福';
            document.querySelector('.subtitle').textContent = `致${to} · 来自${from}`;
            
            // 设置背景颜色
            const bgColor = colorMap[color] || colorMap['p'];
            document.getElementById('header').style.background = bgColor;
            document.body.style.background = bgColor;
            
            // 设置祝福内容
            const messageContainer = document.getElementById('message');
            messageContainer.innerHTML = '';
            
            let messageLines = [];
            if (message) {
                messageLines = message.split('\n').filter(line => line.trim() !== '');
            } else {
                messageLines = defaultMessage;
            }
            
            messageLines.forEach(line => {
                const p = document.createElement('p');
                p.textContent = line || ' ';
                messageContainer.appendChild(p);
            });
            
            // 设置时间
            const now = new Date();
            const timeStr = now.toLocaleString('zh-CN', {
                year: 'numeric',
                month: '2-digit',
                day: '2-digit',
                hour: '2-digit',
                minute: '2-digit'
            });
            document.getElementById('footerText').textContent = `🎓 毕业纪念 · ${timeStr}`;
            
            // 设置页面标题
            document.title = `🎓 毕业祝福 - ${to}`;
            
            // 显示祝福容器
            document.getElementById('blessingContainer').style.display = 'block';
        }
        
        // 初始化
        function init() {
            const params = getUrlParams();
            const popupMode = params.p || '1';
            
            if (popupMode === '1') {
                // 模式1: 暖心弹窗
                showPopupSequence();
            } else if (popupMode === '2') {
                // 模式2: 直接祝福
                showBlessingPage();
            } else if (popupMode === '3') {
                // 模式3: 自定义（默认显示弹窗）
                showPopupSequence();
            } else {
                // 默认显示弹窗
                showPopupSequence();
            }
        }
        
        // 页面加载时初始化
        window.addEventListener('load', init);
        
        // 监听hash变化
        window.addEventListener('hashchange', init);
    </script>
</body>
</html>
