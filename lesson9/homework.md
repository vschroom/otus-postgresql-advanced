#### Разворачиваем высокодоступный кластер PostgeSQL с использованием pg_auto_failover

#### Introducing pg_auto_failover: Open source extension for automated failover and high-availability in PostgreSQL

#### Создал ВМ и установил pg_auto_failover с версией Postgres 14 
![img.png](images/img.png)

#### Создаем и настраиваем первый компонент - монитор. Он будет следить за состоянием нод постгреса.
![img.png](images/img_1.png)
![img.png](images/img_2.png)

#### Создаем времменную файловую систему с небольшим объемом памяти, для того что бы в дальнейшем симулировать аварию. И создаем Primary ноду Postgres-а.
![img.png](images/img_3.png)

#### Стартуем Primary на порту 6010 
![img.png](images/img_4.png)

#### Создаем Secondary ноду Postgres-a и запускаем на порту 6011
![img.png](images/img_5.png)
![img.png](images/img_6.png)

#### Смотрим что монитор видит состояние обеих нод 
![img.png](images/img_7.png)

#### Проверим, что все работает. Создадим таблицу и добавим туда данные в primary ноде и посмотрим, что реплика синхронизирована
![img.png](images/img_8.png)

#### Попробуем загрузить в дисковое пространство primary ноды файл большого объема и посмотрим, что произойдет
![img.png](images/img_9.png)

#### Теперь Primary нода помечена как demoted, а Secondary заняла ее место, если освободить дисковое пространство первой ноды, то нода которая была primary и demoted измениться на secondary и будет доступна только на чтение
![img.png](images/img_10.png)