#### Сравнение скорости работы запросов в PostgresQL и Clickhouse при больших объемах данных

#### Запустил и развернул две ВМ с PostgresQL и Clickhouse
![img.png](images/img.png)

#### Для тестовых данных использовал датасет "Ошибки в энергетической системе" - kaggle datasets download -d lucasalex13/fault-in-electrical-power-systems, включает в себя 5 колонок: id ошибки, время длительности, 3 фазы
#### Загрузил данные в Clickhouse и PostgresQL размером 10 ГБ
![img.png](images/img_1.png)
![img.png](images/img_2.png)

#### Сравниваем скорость запросов в Clickhouse и PostgresQL
##### SELECT count(1) FROM data;
##### Clickhouse - запрос отработал за 0.002 сек.
![img.png](images/img_3.png)
##### PostgresQL - запрос отработал за 4.8 сек.
![img.png](images/img_4.png)
##### SELECT id_fault, SUM(time) FROM data WHERE time < 0.00001 GROUP BY id_fault;
##### Clickhouse - запрос отработал за 0.1 сек.
![img.png](images/img_5.png)
![img.png](images/img_6.png)
##### PostgresQL - запрос отработал за 2.17 сек.
![img.png](images/img_7.png)
##### SELECT count(1) FROM data WHERE time < 0.0005;
##### Clickhouse - запрос отработал за 0.098 сек.
![img.png](images/img_8.png)
##### PostgresQL - запрос отработал за 2.3 сек.
![img.png](images/img_9.png)
##### SELECT id_fault FROM data GROUP BY id_fault ORDER BY id_fault LIMIT 100000;
##### Clickhouse - запрос отработал за 0.074 сек.
![img.png](images/img_10.png)
##### PostgresQL - запрос отработал за 7.16 сек.
![img.png](images/img_11.png)
##### SELECT id_fault FROM data WHERE time > 0.5 AND s1 < 0.0 GROUP BY id_fault;
##### Clickhouse - запрос отработал за 0.079 сек.
![img.png](images/img_12.png)
##### PostgresQL - запрос отработал за 2.18 сек.
![img.png](images/img_13.png)
##### SELECT time FROM data GROUP BY time;
##### Clickhouse - запрос отработал за 0.079 сек.
![img.png](images/img_14.png)
##### PostgresQL - запрос отработал за 8.3 сек.
![img.png](images/img_15.png)

#### Таким образом при объеме данных в 10 ГБ на одинаковых по характеристикам ВМ (при оптимальных настройках postgresql.conf), запросы в Clickhouse отрабатывают примерно в 30 быстрее чем в PostgresQL