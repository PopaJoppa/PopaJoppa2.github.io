      <!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Тест по финансовой грамотности | Для школьников 9-11 классов</title>
    <meta name="description" content="Проверь свои знания по финансовой грамотности и узнай, как правильно управлять деньгами">
    <style>
        :root {
            --primary: #4A6FA5;
            --secondary: #166088;
            --success: #4CB963;
            --warning: #FF9F1C;
            --danger: #E71D36;
            --light: #f8f9fa;
            --dark: #212529;
            --border-radius: 10px;
            --box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #4A6FA5 0%, #166088 100%);
            color: #333;
            line-height: 1.6;
            min-height: 100vh;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .container {
            max-width: 800px;
            width: 100%;
            background: white;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--box-shadow);
        }
        
        header {
            text-align: center;
            padding: 40px 20px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
        }
        
        h1 {
            font-size: 2.2rem;
            margin-bottom: 15px;
        }
        
        .subtitle {
            font-size: 1.1rem;
            opacity: 0.9;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .card {
            padding: 30px;
        }
        
        .step {
            display: none;
        }
        
        .step.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        h2 {
            color: var(--dark);
            margin-bottom: 25px;
            border-bottom: 2px solid #f0f0f0;
            padding-bottom: 10px;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--dark);
        }
        
        input, select {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            transition: all 0.3s;
        }
        
        input:focus, select:focus {
            border-color: var(--primary);
            outline: none;
            box-shadow: 0 0 0 3px rgba(74, 111, 165, 0.1);
        }
        
        .question {
            margin-bottom: 25px;
            padding: 20px;
            border: 1px solid #eaeaea;
            border-radius: 10px;
            background: #fafafa;
        }
        
        .question-text {
            font-size: 1.1rem;
            margin-bottom: 15px;
            font-weight: 600;
            color: var(--dark);
        }
        
        .options {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }
        
        .option {
            display: flex;
            align-items: center;
            padding: 12px 15px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.2s;
            background: white;
        }
        
        .option:hover {
            border-color: var(--primary);
            background: #f0f5ff;
        }
        
        .option.selected {
            background: #e8efff;
            border-color: var(--primary);
        }
        
        .option input {
            margin-right: 12px;
            width: auto;
        }
        
        .btn {
            display: inline-block;
            background: var(--primary);
            color: white;
            padding: 14px 30px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 16px;
            font-weight: 600;
            transition: all 0.3s;
            text-align: center;
            text-decoration: none;
        }
        
        .btn:hover {
            background: var(--secondary);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .btn-container {
            display: flex;
            justify-content: space-between;
            margin-top: 30px;
            gap: 15px;
        }
        
        .btn-next {
            margin-left: auto;
        }
        
        .btn-prev {
            background: #6c757d;
        }
        
        .btn-prev:hover {
            background: #5a6268;
        }
        
        .progress-container {
            margin-bottom: 30px;
        }
        
        .progress-text {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--primary);
        }
        
        .progress-bar {
            height: 10px;
            background-color: #e9ecef;
            border-radius: 5px;
            overflow: hidden;
        }
        
        .progress {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--success));
            width: 0%;
            transition: width 0.5s ease;
        }
        
        .result-card {
            text-align: center;
            padding: 40px 30px;
        }
        
        .level {
            font-size: 2rem;
            margin: 20px 0;
            color: var(--primary);
            font-weight: 700;
        }
        
        .score {
            font-size: 1.5rem;
            margin: 15px 0;
            color: var(--success);
        }
        
        .description {
            margin-bottom: 30px;
            font-size: 1.1rem;
            line-height: 1.7;
        }
        
        .recommendations {
            text-align: left;
            margin-top: 30px;
            background: #f8f9fa;
            padding: 25px;
            border-radius: 10px;
            border-left: 4px solid var(--primary);
        }
        
        .recommendations h3 {
            margin-bottom: 15px;
            color: var(--dark);
        }
        
        .recommendations ul {
            padding-left: 20px;
        }
        
        .recommendations li {
            margin-bottom: 10px;
            line-height: 1.5;
        }
        
        .restart-btn {
            margin-top: 25px;
            background: var(--success);
        }
        
        .restart-btn:hover {
            background: #3da852;
        }
        
        footer {
            text-align: center;
            margin-top: 40px;
            padding: 20px;
            color: #6c757d;
            font-size: 0.9rem;
            border-top: 1px solid #eaeaea;
        }
        
        .info-box {
            background: #e8f0ff;
            border: 1px solid #b8d0ff;
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 20px;
        }
        
        .warning-box {
            background: #fff3e8;
            border: 1px solid #ffd9b8;
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 20px;
            border-left: 4px solid var(--warning);
        }
        
        .subject-icon {
            font-size: 1.5rem;
            margin-right: 10px;
        }
        
        @media (max-width: 600px) {
            body {
                padding: 10px;
            }
            
            h1 {
                font-size: 1.8rem;
            }
            
            .card {
                padding: 20px 15px;
            }
            
            .btn-container {
                flex-direction: column;
            }
            
            .btn {
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Финансовая грамотность для школьников</h1>
            <p class="subtitle">Проверь свои знания и узнай, как правильно управлять деньгами</p>
        </header>
        
        <div class="card">
            <div class="progress-container">
                <div class="progress-text">
                    <span>Прогресс</span>
                    <span id="progress-percent">0%</span>
                </div>
                <div class="progress-bar">
                    <div class="progress" id="progress"></div>
                </div>
            </div>
            
            <div class="step active" id="step1">
                <div class="info-box">
                    <p>💰 Этот тест поможет оценить твой уровень финансовой грамотности. Ответь честно на все вопросы для получения точного результата и полезных рекомендаций.</p>
                    <p><strong>Примечание:</strong> Вопросы меняются при каждом обновлении страницы!</p>
                </div>
                
                <h2>Информация об ученике</h2>
                <div class="form-group">
                    <label for="name">Имя:</label>
                    <input type="text" id="name" placeholder="Введите ваше имя">
                </div>
                <div class="form-group">
                    <label for="grade">Класс:</label>
                    <select id="grade">
                        <option value="">Выберите класс</option>
                        <option value="9">9 класс</option>
                        <option value="10">10 класс</option>
                        <option value="11">11 класс</option>
                    </select>
                </div>
                <div class="btn-container">
                    <button class="btn btn-next" id="start-btn">Начать тест</button>
                </div>
            </div>
            
            <div class="step" id="step2">
                <h2><span class="subject-icon">💰</span> Основы финансов</h2>
                <div id="questions-basics">
                    <!-- Вопросы будут добавлены с помощью JavaScript -->
                </div>
                <div class="btn-container">
                    <button class="btn btn-prev" id="prev-btn-2">Назад</button>
                    <button class="btn btn-next" id="next-btn-2">Далее</button>
                </div>
            </div>
            
            <div class="step" id="step3">
                <h2><span class="subject-icon">🏦</span> Банки и карты</h2>
                <div id="questions-banking">
                    <!-- Вопросы будут добавлены с помощью JavaScript -->
                </div>
                <div class="btn-container">
                    <button class="btn btn-prev" id="prev-btn-3">Назад</button>
                    <button class="btn btn-next" id="next-btn-3">Далее</button>
                </div>
            </div>
            
            <div class="step" id="step4">
                <h2><span class="subject-icon">🚫</span> Защита от мошенников</h2>
                
                <div class="warning-box">
                    <p>⚠️ В этом разделе проверь, как хорошо ты знаешь способы защиты от финансовых мошенников.</p>
                </div>
                
                <div id="questions-fraud">
                    <!-- Вопросы будут добавлены с помощью JavaScript -->
                </div>
                
                <div class="btn-container">
                    <button class="btn btn-prev" id="prev-btn-4">Назад</button>
                    <button class="btn btn-next" id="next-btn-4">Завершить тест</button>
                </div>
            </div>
            
            <div class="step" id="step5">
                <div class="result-card">
                    <h2>Результаты тестирования</h2>
                    <p id="student-info"></p>
                    <div class="score" id="score-result"></div>
                    <div class="level" id="level-result"></div>
                    <div class="description" id="level-description"></div>
                    
                    <div class="recommendations">
                        <h3>Рекомендации для улучшения финансовой грамотности:</h3>
                        <ul id="recommendations-list"></ul>
                    </div>
                    
                    <button class="btn restart-btn" id="restart-btn">Пройти тест заново</button>
                </div>
            </div>
        </div>
        
        <footer>
            <p>© 2025 Тест по финансовой грамотности для школьников 9-11 классов</p>
        </footer>
    </div>

    <script>
        // БАЗА ВОПРОСОВ - адаптирована для школьников 9-11 классов
        const questionBank = {
            basics: [
                {
                    question: "Что такое бюджет?",
                    options: [
                        "Список желаемых покупок",
                        "План доходов и расходов на определенный период",
                        "Сумма денег на банковском счете",
                        "Государственные финансы"
                    ],
                    correct: 1
                },
                {
                    question: "Что такое 'финансовая подушка безопасности'?",
                    options: [
                        "Деньги на развлечения",
                        "Сбережения на крупную покупку",
                        "Резерв средств на непредвиденные расходы",
                        "Деньги на инвестиции"
                    ],
                    correct: 2
                },
                {
                    question: "Что такое инфляция?",
                    options: [
                        "Увеличение стоимости ценных бумаг",
                        "Повышение общего уровня цен на товары и услуги",
                        "Увеличение заработной платы",
                        "Снижение курса национальной валюты"
                    ],
                    correct: 1
                },
                {
                    question: "Что такое пассивный доход?",
                    options: [
                        "Доход от работы по найму",
                        "Доход от бизнеса",
                        "Доход, не требующий постоянных активных действий",
                        "Доход от подработки"
                    ],
                    correct: 2
                },
                {
                    question: "Что такое подоходный налог?",
                    options: [
                        "Налог на покупку товаров и услуг",
                        "Налог на доходы физических лиц",
                        "Налог на недвижимость",
                        "Налог на транспортные средства"
                    ],
                    correct: 1
                },
                {
                    question: "Что такое кредитная история?",
                    options: [
                        "История покупок в кредит",
                        "Информация о выполнении обязательств по кредитам",
                        "Список всех взятых кредитов",
                        "История работы кредитных организаций"
                    ],
                    correct: 1
                },
                {
                    question: "Что такое актив?",
                    options: [
                        "Обязательство перед банком",
                        "Расходы компании",
                        "Ресурс, который приносит доход",
                        "Налоговая декларация"
                    ],
                    correct: 2
                },
                {
                    question: "Что такое сложный процент?",
                    options: [
                        "Процент, начисляемый только на первоначальную сумму",
                        "Высокий процент по вкладу",
                        "Процент, начисляемый на сумму с ранее начисленными процентами",
                        "Процент по кредиту"
                    ],
                    correct: 2
                }
            ],
            banking: [
                {
                    question: "Что такое депозит?",
                    options: [
                        "Вид кредита",
                        "Вклад денежных средств в банк под проценты",
                        "Платежная карта",
                        "Страховой полис"
                    ],
                    correct: 1
                },
                {
                    question: "Какие данные банковской карты можно сообщать по телефону?",
                    options: [
                        "Полный номер карты и CVV-код",
                        "Только номер карты",
                        "Никакие данные карты нельзя сообщать",
                        "Можно сообщить, если звонящий представился сотрудником банка"
                    ],
                    correct: 2
                },
                {
                    question: "Что такое фишинг?",
                    options: [
                        "Вид рыбалки",
                        "Мошенническая схема с целью получения конфиденциальных данных",
                        "Вид инвестирования",
                        "Способ экономии денег"
                    ],
                    correct: 1
                },
                {
                    question: "Что означает понятие 'овердрафт'?",
                    options: [
                        "Превышение расходов над доходами",
                        "Краткосрочный кредит на небольшую сумму",
                        "Возможность оплаты при отсутствии средств на счете",
                        "Все варианты верны"
                    ],
                    correct: 3
                },
                {
                    question: "Что такое ипотека?",
                    options: [
                        "Кредит на образование",
                        "Кредит на покупку недвижимости под залог этой недвижимости",
                        "Кредит на автомобиль",
                        "Потребительский кредит"
                    ],
                    correct: 1
                },
                {
                    question: "Что такое кредитный лимит?",
                    options: [
                        "Максимальная сумма, которую можно снять в банкомате",
                        "Максимальная сумма кредита, доступная заемщику",
                        "Срок действия кредитной карты",
                        "Процентная ставка по кредиту"
                    ],
                    correct: 1
                },
                {
                    question: "Что такое безналичный расчет?",
                    options: [
                        "Расчет наличными деньгами",
                        "Расчет через банковские счета без использования наличных",
                        "Расчет криптовалютой",
                        "Расчет через мобильное приложение"
                    ],
                    correct: 1
                }
            ],
            fraud: [
                {
                    question: "Что делать, если вам позвонили и представились сотрудником банка, запрашивая данные карты?",
                    options: [
                        "Назвать данные, так как звонят из банка",
                        "Перезвонить в банк по официальному номеру для уточнения информации",
                        "Сообщить данные, но только номер карты",
                        "Ничего не делать, это точно мошенники"
                    ],
                    correct: 1
                },
                {
                    question: "Как отличить финансовую пирамиду от легальной инвестиционной компании?",
                    options: [
                        "По наличию лицензии у компании",
                        "По обещаниям очень высокой доходности",
                        "По требованию привлекать новых участников для получения дохода",
                        "Все вышеперечисленное"
                    ],
                    correct: 3
                },
                {
                    question: "Что такое 'социальная инженерия' в контексте мошенничества?",
                    options: [
                        "Методы воздействия на людей для получения конфиденциальной информации",
                        "Инженерные работы в социальной сфере",
                        "Социальные программы помощи",
                        "Вид благотворительности"
                    ],
                    correct: 0
                },
                {
                    question: "Какие меры защиты следует предпринять при онлайн-покупках?",
                    options: [
                        "Покупать только на проверенных сайтах с HTTPS-протоколом",
                        "Использовать виртуальные карты для онлайн-платежей",
                        "Не сохранять данные карты на сайтах",
                        "Все вышеперечисленное"
                    ],
                    correct: 3
                },
                {
                    question: "Как защититься от телефонных мошенников?",
                    options: [
                        "Никогда не сообщать личные данные по телефону",
                        "Установить приложение для блокировки спам-звонков",
                        "Проверять информацию через официальные каналы связи с банком",
                        "Все вышеперечисленное"
                    ],
                    correct: 3
                },
                {
                    question: "Как распознать мошенническое SMS-сообщение?",
                    options: [
                        "Сообщение содержит ссылку на незнакомый сайт",
                        "В сообщении просят срочно перейти по ссылке и ввести данные",
                        "Отправитель неизвестен или подделан под известную организацию",
                        "Все вышеперечисленное"
                    ],
                    correct: 3
                },
                {
                    question: "Что делать, если вы стали жертвой мошенников?",
                    options: [
                        "Немедленно заблокировать карту через приложение банка",
                        "Сообщить в банк о несанкционированной операции",
                        "Обратиться в полицию с заявлением",
                        "Все вышеперечисленное"
                    ],
                    correct: 3
                }
            ]
        };

        // Функция для случайного выбора вопросов
        function getRandomQuestions(category, count) {
            const questions = [...questionBank[category]];
            const selected = [];
            
            for (let i = 0; i < count && questions.length > 0; i++) {
                const randomIndex = Math.floor(Math.random() * questions.length);
                selected.push(questions[randomIndex]);
                questions.splice(randomIndex, 1);
            }
            
            return selected;
        }

        // Глобальные переменные для хранения выбранных вопросов и правильных ответов
        let selectedQuestions = {
            basics: [],
            banking: [],
            fraud: []
        };
        
        let correctAnswers = {};

        // Функция для отображения вопросов на странице
        function renderQuestions() {
            // Очищаем контейнеры с вопросами
            document.getElementById('questions-basics').innerHTML = '';
            document.getElementById('questions-banking').innerHTML = '';
            document.getElementById('questions-fraud').innerHTML = '';
            
            // Сбрасываем объект с правильными ответами
            correctAnswers = {};
            
            // Отображаем вопросы по основам финансовой грамотности
            selectedQuestions.basics.forEach((q, index) => {
                const questionId = `basics${index + 1}`;
                correctAnswers[questionId] = q.correct;
                
                const questionHTML = `
                    <div class="question">
                        <div class="question-text">${index + 1}. ${q.question}</div>
                        <div class="options">
                            ${q.options.map((option, optIndex) => `
                                <label class="option">
                                    <input type="radio" name="${questionId}" value="${optIndex}"> ${option}
                                </label>
                            `).join('')}
                        </div>
                    </div>
                `;
                
                document.getElementById('questions-basics').innerHTML += questionHTML;
            });
            
            // Отображаем вопросы по банковским продуктам
            selectedQuestions.banking.forEach((q, index) => {
                const questionId = `banking${index + 1}`;
                correctAnswers[questionId] = q.correct;
                
                const questionHTML = `
                    <div class="question">
                        <div class="question-text">${index + 4}. ${q.question}</div>
                        <div class="options">
                            ${q.options.map((option, optIndex) => `
                                <label class="option">
                                    <input type="radio" name="${questionId}" value="${optIndex}"> ${option}
                                </label>
                            `).join('')}
                        </div>
                    </div>
                `;
                
                document.getElementById('questions-banking').innerHTML += questionHTML;
            });
            
            // Отображаем вопросы по защите от мошенничества
            selectedQuestions.fraud.forEach((q, index) => {
                const questionId = `fraud${index + 1}`;
                correctAnswers[questionId] = q.correct;
                
                const questionHTML = `
                    <div class="question">
                        <div class="question-text">${index + 7}. ${q.question}</div>
                        <div class="options">
                            ${q.options.map((option, optIndex) => `
                                <label class="option">
                                    <input type="radio" name="${questionId}" value="${optIndex}"> ${option}
                                </label>
                            `).join('')}
                        </div>
                    </div>
                `;
                
                document.getElementById('questions-fraud').innerHTML += questionHTML;
            });
            
            // Добавляем обработчики событий для вариантов ответов
            addOptionHandlers();
        }

        // Функция для добавления обработчиков событий к вариантам ответов
        function addOptionHandlers() {
            const options = document.querySelectorAll('.option');
            options.forEach(option => {
                option.addEventListener('click', function() {
                    const radio = this.querySelector('input[type="radio"]');
                    radio.checked = true;
                    
                    // Снимаем выделение со всех вариантов в группе
                    const groupName = radio.getAttribute('name');
                    const groupOptions = document.querySelectorAll(`input[name="${groupName}"]`);
                    groupOptions.forEach(opt => {
                        opt.parentElement.classList.remove('selected');
                    });
                    
                    // Выделяем выбранный вариант
                    this.classList.add('selected');
                });
            });
        }

        // Описания уровней
        const levelDescriptions = {
            beginner: {
                name: "Начальный уровень",
                description: "У тебя есть базовые представления о финансах, но много важных аспектов требуют изучения. Особенно важно изучить способы защиты от мошенников.",
                recommendations: [
                    "Изучи основы финансовой грамотности: бюджет, сбережения, кредиты",
                    "Научись распознавать основные схемы финансового мошенничества",
                    "Создай финансовую подушку безопасности на 3-6 месяцев",
                    "Никогда не сообщай данные карты по телефону или в сообщениях",
                    "Установи мобильное приложение банка и настрой уведомления о операциях"
                ]
            },
            intermediate: {
                name: "Средний уровень",
                description: "У тебя хорошие базовые знания в области финансов, но есть темы, которые требуют углубленного изучения, особенно в области кибербезопасности.",
                recommendations: [
                    "Углубляй знания в области защиты от финансового мошенничества",
                    "Используй виртуальные карты для онлайн-платежей",
                    "Включи двухфакторную аутентификацию для всех финансовых сервисов",
                    "Регулярно проверяй свою кредитную историю",
                    "Изучи возможности страхования финансовых рисков"
                ]
            },
            advanced: {
                name: "Продвинутый уровень",
                description: "Поздравляем! У тебя отличные знания в области финансов и защиты от мошенников. Ты понимаешь основные финансовые концепции и способы защиты.",
                recommendations: [
                    "Продолжай следить за новыми схемами мошенничества",
                    "Обучай близких правилам финансовой безопасности",
                    "Рассмотри возможности для диверсификации инвестиционного портфеля",
                    "Используй отдельные карты для разных типов операций",
                    "Регулярно обновляй пароли к финансовым сервисам"
                ]
            }
        };
        
        let currentStep = 1;
        const totalSteps = 5;
        
        // Функция обновления прогресс-бара
        function updateProgress() {
            const progress = document.getElementById('progress');
            const progressPercent = document.getElementById('progress-percent');
            const percentage = ((currentStep - 1) / (totalSteps - 1)) * 100;
            progress.style.width = percentage + '%';
            progressPercent.textContent = Math.round(percentage) + '%';
        }
        
        // Функция перехода к следующему шагу
        function nextStep() {
            // Проверка заполнения текущего шага
            if (currentStep === 1) {
                const name = document.getElementById('name').value;
                const grade = document.getElementById('grade').value;
                
                if (!name || !grade) {
                    alert('Пожалуйста, заполните все поля');
                    return;
                }
            } else {
                // Проверка ответов на вопросы текущего шага
                let allAnswered = true;
                const questions = document.querySelectorAll(`#step${currentStep} input[type="radio"]`);
                const questionGroups = {};
                
                questions.forEach(q => {
                    const name = q.getAttribute('name');
                    if (!questionGroups[name]) questionGroups[name] = [];
                    questionGroups[name].push(q);
                });
                
                for (const group in questionGroups) {
                    let answered = false;
                    questionGroups[group].forEach(q => {
                        if (q.checked) answered = true;
                    });
                    if (!answered) allAnswered = false;
                }
                
                if (!allAnswered) {
                    alert('Пожалуйста, ответьте на все вопросы перед переходом к следующему шагу');
                    return;
                }
            }
            
            // Переход к следующему шагу
            document.getElementById(`step${currentStep}`).classList.remove('active');
            currentStep++;
            document.getElementById(`step${currentStep}`).classList.add('active');
            updateProgress();
            
            // Если это последний шаг, показать результаты
            if (currentStep === totalSteps) {
                showResults();
            }
        }
        
        // Функция перехода к предыдущему шагу
        function prevStep() {
            document.getElementById(`step${currentStep}`).classList.remove('active');
            currentStep--;
            document.getElementById(`step${currentStep}`).classList.add('active');
            updateProgress();
        }
        
        // Функция показа результатов
        function showResults() {
            // Сбор информации о пользователе
            const name = document.getElementById('name').value;
            const grade = document.getElementById('grade').value;
            document.getElementById('student-info').textContent = `${name}, ${grade} класс`;
            
            // Подсчет правильных ответов
            let score = 0;
            const totalQuestions = Object.keys(correctAnswers).length;
            
            for (const question in correctAnswers) {
                const selected = document.querySelector(`input[name="${question}"]:checked`);
                if (selected && parseInt(selected.value) === correctAnswers[question]) {
                    score++;
                }
            }
            
            // Определение уровня
            let level;
            if (score <= 4) {
                level = 'beginner';
            } else if (score <= 7) {
                level = 'intermediate';
            } else {
                level = 'advanced';
            }
            
            // Отображение результатов
            document.getElementById('score-result').textContent = `Правильных ответов: ${score} из ${totalQuestions}`;
            document.getElementById('level-result').textContent = levelDescriptions[level].name;
            document.getElementById('level-description').textContent = levelDescriptions[level].description;
            
            const recommendationsList = document.getElementById('recommendations-list');
            recommendationsList.innerHTML = '';
            levelDescriptions[level].recommendations.forEach(rec => {
                const li = document.createElement('li');
                li.textContent = rec;
                recommendationsList.appendChild(li);
            });
        }
        
        // Функция перезапуска теста
        function restartTest() {
            // Сброс формы
            document.getElementById('name').value = '';
            document.getElementById('grade').value = '';
            
            // Сброс выбранных ответов
            const allInputs = document.querySelectorAll('input[type="radio"]');
            allInputs.forEach(input => {
                input.checked = false;
                input.parentElement.classList.remove('selected');
            });
            
            // Генерация новых случайных вопросов
            selectedQuestions.basics = getRandomQuestions('basics', 3);
            selectedQuestions.banking = getRandomQuestions('banking', 3);
            selectedQuestions.fraud = getRandomQuestions('fraud', 4);
            
            // Перерисовка вопросов
            renderQuestions();
            
            // Возврат к первому шагу
            document.getElementById(`step${currentStep}`).classList.remove('active');
            currentStep = 1;
            document.getElementById(`step${currentStep}`).classList.add('active');
            updateProgress();
            
            // Прокрутка к верху страницы
            window.scrollTo(0, 0);
        }
        
        // Инициализация после загрузки DOM
        document.addEventListener('DOMContentLoaded', function() {
            // Выбираем случайные вопросы при загрузке страницы
            selectedQuestions.basics = getRandomQuestions('basics', 3);
            selectedQuestions.banking = getRandomQuestions('banking', 3);
            selectedQuestions.fraud = getRandomQuestions('fraud', 4);
            
            // Отображаем вопросы
            renderQuestions();
            
            // Обработчики для кнопок навигации
            document.getElementById('start-btn').addEventListener('click', nextStep);
            document.getElementById('next-btn-2').addEventListener('click', nextStep);
            document.getElementById('next-btn-3').addEventListener('click', nextStep);
            document.getElementById('next-btn-4').addEventListener('click', nextStep);
            
            document.getElementById('prev-btn-2').addEventListener('click', prevStep);
            document.getElementById('prev-btn-3').addEventListener('click', prevStep);
            document.getElementById('prev-btn-4').addEventListener('click', prevStep);
            
            document.getElementById('restart-btn').addEventListener('click', restartTest);
            
            // Инициализация прогресс-бара
            updateProgress();
        });
    </script>
</body>
</html>   
                 
            
