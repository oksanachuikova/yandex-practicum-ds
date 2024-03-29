# Телекоммуникации: прогнозирование оттока клиентов
## Задача
Построить модель, которая позволит прогнозировать отток клиентов оператора связи и вовремя и адресно предлагать промокоды и специальные условия для удержания клиентов
## Описание проекта
Оператор связи хочет научиться прогнозировать отток клиентов. Если выяснится, что пользователь планирует уйти, ему будут предложены промокоды и специальные условия. В распоряжении имеются персональные данные о некоторых клиентах, информация об их тарифах и договорах. При оценки качества модели учитывается значение метрики AUC-ROC, дополнительным пожеланием заказчика является расчет значения Accuracy.
## Этапы работы
* *План и исследовательский анализ данных:*
  * загрузка и изучение данных;
  * предобработка данных: приведение данных к подходящим типам, устранение ошибок, добавление столбцов, объединение таблиц, устранение пропусков.
  * исследовательский анализ данных: анализ распределения признаков, анализ распределения признаков в связи со значениями целевого признака, рассмотрение корреляции признаков и борьба с мультиколлинеарностью.
* *Построение модели:*
  * подготовка данных к обучению;   
  * обучение моделей и выбор лучшей модели: обучение моделей с различными гиперпараметрами, оценка качества моделей на кросс-валидации и построение сравнительной таблицы;
  * тестирование лучшей модели и проверка на адекватность путем сравнения с константной моделью;
  * построение матрицы ошибок и ее интерпретация;
  * оценка важности признаков.
* *Отчет по проекту*
## Вывод
В ходе работы было обнаружено, что **идентичные по качеству с точки зрения значения целевой метрики ROC-AUC варианты лучшей модели**, обученные с применением **техники взвешивания классов** и без нее, показывают существенные различия с точки зрения оценки результатов матрицы ошибок. Из условий задачи неизвестно, что в приоритете у заказчика: 1) **предотвратить уход большего числа клиентов**, рискуя при этом также предложить промокоды и специальные условия клиентам, которые не собираются уходить из компании, или 2) **допустить уход большего числа клиентов**, при этом избежав неадресного предложения промокодов и специальных условий. Поскольку явно обозначенная **цель проекта - предсказать уход** клиентов, более адекватными этой цели результатами при прочих равных представляются результаты модели, обученной с учетом дисбаланса. При этом необходимо **ознакомить заказчика** с результатами тестирования обоих вариантов лучшей модели (обученной **с учетом дисбаланса и без него**) и рекомендуется оценить возможную упущенную выгоду от ухода клиента и от предложения промокодов и специальных условий клиентам, которые на самом деле не собираются уйти из компании.
## Используемые библиотеки
*Pandas*, *NumPy*, *Matplotlib*, *Seaborn*, *Scikit-learn*, *CatBoost*, *LightGBM*, *Phik*, *Shap*

