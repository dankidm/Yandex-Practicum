# Телеком описание задачи
Оператор связи хочет научиться прогнозировать отток клиентов. Если выяснится, что пользователь планирует уйти, ему будут предложены промокоды и специальные условия. Команда оператора собрала персональные данные о некоторых клиентах, информацию об их тарифах и договорах.

## Описание услуг:
Оператор предоставляет два основных типа услуг:
1. Стационарную телефонную связь. Возможно подключение телефонного аппарата к нескольким линиям одновременно.
2. Интернет. Подключение может быть двух типов: через телефонную линию (DSL, от англ. digital subscriber line, «цифровая абонентская линия») или оптоволоконный кабель (Fiber optic).

Также доступны такие услуги:
1. Интернет-безопасность: антивирус (DeviceProtection) и блокировка небезопасных сайтов (OnlineSecurity);
2. Выделенная линия технической поддержки (TechSupport);
3. Облачное хранилище файлов для резервного копирования данных (OnlineBackup);
4. Стриминговое телевидение (StreamingTV) и каталог фильмов (StreamingMovies).

За услуги клиенты могут платить каждый месяц или заключить договор на 1–2 года. Доступны различные способы расчёта и возможность получения электронного чека.

## Данные
Данные состоят из файлов, полученных из разных источников:
contract.csv — информация о договоре;
personal.csv — персональные данные клиента;
internet.csv — информация об интернет-услугах;
phone.csv — информация об услугах телефонии.
Во всех файлах столбец customerID содержит код клиента.

Информация о договорах актуальна на 1 февраля 2020.

## Стек проекта
В проекте использовались: 
1. Чтение и работа с датасетами: **Pandas** и **Numpy**
2. Визуализации анализа данных: **Seaborn**, **Phik** и **Matplotlib** 
3. Предобработка данных: **Sklearn**
4. Для решения задачи прогнозирования: линейные модели из библиотеки **Sklearn** и градиентные бустинги из библиотек **CatBoost**, **LightGBM**

## Вывод:
- При анализе матрицы корреляции выяснилось, что признаки InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies оказались сильно скоррелированы (>0.9)
- На валидационных данных удалось достичь поставленной цели - метрика ROC-AUC > 0.85 (~0.90)
- Лучшей моделью оказалась CatBoostClassifier с значением целевой метрики ROC-AUC на тренировочной выборке около 0.90
- На основе анализа матрицы ошибок можно сказать, что модель чаще всего допускает ошибки первого рода 

## Статус проекта:
Завершен