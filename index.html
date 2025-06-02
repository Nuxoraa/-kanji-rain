<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>漢字</title> <!-- Невидимый заголовок с иероглифом -->
    <link rel="icon" href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22 fill=%22red%22>漢</text></svg>">
    <style>
        body {
            margin: 0;
            padding: 0;
            background-color: #000;
            overflow: hidden;
            height: 100vh;
            width: 100vw;
            cursor: none;
        }
        .kanji-layer {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }
        .kanji {
            position: absolute;
            color: #ff0000;
            font-size: 28px;
            user-select: none;
            opacity: 1;
            will-change: transform, opacity;
            text-shadow: 0 0 8px rgba(255, 50, 50, 0.9);
            font-weight: bold;
            font-family: "MS Gothic", "Yu Gothic", sans-serif;
        }
        /* Скрываем все элементы интерфейса */
        head, title, meta, link {
            display: none !important;
        }
    </style>
</head>
<body>
    <div id="kanji-layer" class="kanji-layer"></div>
    <script>
        // Оптимизированный пул иероглифов (200+ символов)
        const kanjiPool = [
            '嵐','瀑','渓','岳','岬','森','樹','植','葉','茎','芽','苑',
            '葵','菊','蓮','苺','楓','楠','桜','椿','梅','桃','李','杏',
            '橙','檸','柚','栗','柿','梨','霞','霜','雹','虹','曇','晴',
            '暑','寒','涼','暖','潮','汐','波','浪','渦','漣','淀','湛',
            '瀬','淵','鯨','鮫','鱗','鴎','鳩','鷹','雀','燕','鶴','鴉',
            '蛙','蛇','蜘','蟻','蝶','蝉','蟹','貝','牡','蛍','悦','憂',
            '惚','惨','怖','恥','恨','悔','悟','憧','翔','泳','跳','踊',
            '駆','斬','撃','射','祈','詠','剣','盾','弓','槍','笛','琴',
            '鈴','鏡','鐘','鼎','塔','閣','宮','殿','祠','陵','窟','舗',
            '軒','廃','茜','藍','翠','朱','紺','瑠','璃','琥珀','翡翠','瑪瑙',
            '零','壱','弐','参','肆','伍','陸','漆','捌','玖','龍','鳳',
            '麒麟','妖怪','幽霊','鬼','魑','魅','魍','魎','絆','燐','雫','凪',
            '匂','仄','栞','杣','榊','籾','麿','笹','凜','燦','澪','皐',
            '朧','凜','燐','燁','毬','簾','燐','燮','犇','猋','驫','麤',
            '龘','歮','飝','虪','讟','钃','鸜','麷','靏','龖','齾','齉'
        ];

        // Настройки системы
        const config = {
            targetFPS: 60,
            spawnRate: 40, // ms между спавном групп
            groupSize: 3,  // иероглифов в группе
            fadeDuration: 1500, // ms анимации исчезновения
            disappearChance: 0.0015 // 15% шанс исчезновения
        };

        // Состояние системы
        const state = {
            lastFrameTime: 0,
            lastSpawnTime: 0,
            activeKanjis: [],
            kanjiLayer: null,
            nextKanjiId: 0,
            frameCount: 0,
            fps: 0
        };

        // Инициализация
        function init() {
            state.kanjiLayer = document.getElementById('kanji-layer');
            
            // Авто-F11 с обработкой ошибок
            const enterFullscreen = () => {
                try {
                    if (document.documentElement.requestFullscreen) {
                        document.documentElement.requestFullscreen().catch(e => console.log(e));
                    }
                } catch(e) { console.log(e); }
            };
            
            // Пытаемся войти в полноэкранный режим
            setTimeout(enterFullscreen, 500);
            
            // Альтернативный способ по клику
            document.addEventListener('click', enterFullscreen);
            
            // Начальное заполнение
            spawnKanjiGroup(150);
            
            // Запуск главного цикла
            requestAnimationFrame(mainLoop);
        }

        // Главный игровой цикл с фиксированным FPS
        function mainLoop(timestamp) {
            // Управление FPS
            const deltaTime = timestamp - state.lastFrameTime;
            const fpsInterval = 1000 / config.targetFPS;
            
            if (deltaTime > fpsInterval) {
                state.lastFrameTime = timestamp - (deltaTime % fpsInterval);
                
                // Обновление анимаций
                updateKanjis();
                
                // Спавн новых групп
                if (timestamp - state.lastSpawnTime > config.spawnRate) {
                    state.lastSpawnTime = timestamp;
                    spawnKanjiGroup(config.groupSize);
                }
            }
            
            requestAnimationFrame(mainLoop);
        }

        // Создание группы иероглифов
        function spawnKanjiGroup(count) {
            for (let i = 0; i < count; i++) {
                const kanji = {
                    id: state.nextKanjiId++,
                    element: null,
                    x: Math.random() * window.innerWidth,
                    y: -50 - Math.random() * 100,
                    speed: 1 + Math.random() * 4,
                    rotation: (Math.random() * 90) - 45,
                    scale: 0.8 + Math.random() * 0.7,
                    opacity: 0.7 + Math.random() * 0.3,
                    isFading: false,
                    startFadeTime: 0
                };
                
                createKanjiElement(kanji);
                state.activeKanjis.push(kanji);
            }
        }

        // Создание DOM-элемента для иероглифа
        function createKanjiElement(kanji) {
            const element = document.createElement('div');
            element.className = 'kanji';
            element.textContent = kanjiPool[Math.floor(Math.random() * kanjiPool.length)];
            element.style.left = `${kanji.x}px`;
            element.style.top = `${kanji.y}px`;
            element.style.transform = `rotate(${kanji.rotation}deg) scale(${kanji.scale})`;
            element.style.opacity = kanji.opacity;
            element.dataset.id = kanji.id;
            
            state.kanjiLayer.appendChild(element);
            kanji.element = element;
        }

        // Обновление всех иероглифов
        function updateKanjis() {
            const now = performance.now();
            const toRemove = [];
            
            for (let i = 0; i < state.activeKanjis.length; i++) {
                const kanji = state.activeKanjis[i];
                
                if (kanji.isFading) {
                    // Анимация исчезновения
                    const fadeProgress = (now - kanji.startFadeTime) / config.fadeDuration;
                    if (fadeProgress >= 1) {
                        toRemove.push(i);
                        continue;
                    }
                    kanji.element.style.opacity = kanji.opacity * (1 - fadeProgress);
                } else {
                    // Движение вниз
                    kanji.y += kanji.speed;
                    kanji.element.style.top = `${kanji.y}px`;
                    
                    // Проверка на исчезновение
                    if ((Math.random() < config.disappearChance && kanji.y < window.innerHeight * 0.9) ||
                        kanji.y > window.innerHeight + 50) {
                        kanji.isFading = true;
                        kanji.startFadeTime = now;
                    }
                }
            }
            
            // Удаление исчезнувших иероглифов (с конца чтобы не ломать индексы)
            for (let i = toRemove.length - 1; i >= 0; i--) {
                const idx = toRemove[i];
                const kanji = state.activeKanjis[idx];
                if (kanji.element && kanji.element.parentNode) {
                    state.kanjiLayer.removeChild(kanji.element);
                }
                state.activeKanjis.splice(idx, 1);
            }
        }

        // Запуск при загрузке
        window.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>
