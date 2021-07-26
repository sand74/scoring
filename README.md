# scoring
Компьютер говорит "Нет"

Задача:

Построить скоринг модель для вторичных клиентов банка, которая бы предсказывала вероятность дефолта клиента. Для этого нужно будет определить значимые параметры заемщика.

Данные:

client_id	идентификатор клиента
education	уровень образования
sex		пол заёмщика
age		возраст заёмщика
car		флаг наличия автомобиля
car_type	флаг автомобиля-иномарки
decline_app_cnt	количество отказанных прошлых заявок
good_work	флаг наличия «хорошей» работы
bki_request_cnt	количество запросов в БКИ
home_address	категоризатор домашнего адреса
work_address	категоризатор рабочего адреса
income		доход заёмщика
foreign_passport	наличие загранпаспорта
sna		связь заемщика с клиентами банка
first_time	давность наличия информации о заемщике
score_bki	скоринговый балл по данным из БКИ
region_rating	рейтинг региона
app_date	дата подачи заявки
default	наличие дефолта

Наборы:

тренировочный - train.csv (73800 строк)
тестовый - test.csv (36350 строк)


Рассмотренные модели:

LogisticRegression
XGBClassifier
CatBoostClassifier


Выводы:
Рассмотренные модели дают примерно одинаковый ROC-AUC (0.73+-). Модели с балансировкой классов дают в разы больший F1. Наверное, настройкой гиперпараметров XGD и CatBoost можно добиться улучшения результата, но зато с логистической регрессией работать проще (меньше гиперпараметров). Можно сгенерировать еще признаки (например полиномиальные), но тогда значитльно упадет интерпретируемость модели.