### План по выполнению проекта

### Шаг 1. Открыть файл с данными и изучить общую информацию



### Шаг 2. Подготовить данные

Привести данные к нужным типам;
Найти и исправить ошибки в данных.
Пояснить, какие ошибки найдены и как их исправил. У большого количества звонков длительность — 0.0 минут. Это проблема в данных, нужна предобработка.
Посчитать для каждого пользователя:
##### количество сделанных звонков и израсходованных минут разговора по месяцам;
##### количество отправленных сообщений по месяцам;
##### объем израсходованного интернет-трафика по месяцам;
##### помесячную выручку с каждого пользователя (вычтите бесплатный лимит из суммарного количества звонков, сообщений и интернет-трафика; остаток умножьте на значение из тарифного плана; прибавьте абонентскую плату, соответствующую тарифному плану).

### Шаг 3. Проанализируйте данные

Опиcать поведение клиентов оператора, исходя из выборки. Сколько минут разговора, сколько сообщений и какой объём интернет-трафика требуется пользователям каждого тарифа в месяц? Посчитать среднее количество, дисперсию и стандартное отклонение. Построить гистограммы. Описать распределения.

### Шаг 4. Проверьте гипотезы

##### средняя выручка пользователей тарифов «Ультра» и «Смарт» различается;
##### средняя выручка пользователей из Москвы отличается от выручки пользователей из других регионов;
Пороговое значение alpha задайте самостоятельно.

### Шаг 5. Напишите общий вывод
Оформление: Задание выполните в Jupyter Notebook. Программный код заполните в ячейках типа code, текстовые пояснения — в ячейках типа markdown. Примените форматирование и заголовки.

Описание данных
### Таблица users (информация о пользователях):
#### user_id — уникальный идентификатор пользователя
#### first_name — имя пользователя
#### last_name — фамилия пользователя
#### age — возраст пользователя (годы)
#### reg_date — дата подключения тарифа (день, месяц, год)
#### churn_date — дата прекращения пользования тарифом (если значение пропущено, то тариф ещё действовал на момент выгрузки данных)
#### city — город проживания пользователя
#### tariff — название тарифного плана

### Таблица calls (информация о звонках):

#### id — уникальный номер звонка
#### call_date — дата звонка
#### duration — длительность звонка в минутах
#### user_id — идентификатор пользователя, сделавшего звонок
#### Таблица messages (информация о сообщениях):
#### id — уникальный номер сообщения
#### message_date — дата сообщения
#### user_id — идентификатор пользователя, отправившего сообщение

### Таблица internet (информация об интернет-сессиях):
#### id — уникальный номер сессии
#### mb_used — объём потраченного за сессию интернет-трафика (в мегабайтах)
#### session_date — дата интернет-сессии
#### user_id — идентификатор пользователя

### Таблица tariffs (информация о тарифах):
#### tariff_name — название тарифа
#### rub_monthly_fee — ежемесячная абонентская плата в рублях
#### minutes_included — количество минут разговора в месяц, включённых в абонентскую плату
#### messages_included — количество сообщений в месяц, включённых в абонентскую плату
#### mb_per_month_included — объём интернет-трафика, включённого в абонентскую плату (в мегабайтах)
#### rub_per_minute — стоимость минуты разговора сверх тарифного пакета (например, если в тарифе 100 минут разговора в месяц, то со 101 минуты будет взиматься плата)
#### rub_per_message — стоимость отправки сообщения сверх тарифного пакета
#### rub_per_gb — стоимость дополнительного гигабайта интернет-трафика сверх тарифного пакета (1 гигабайт = 1024 мегабайта)