#### Поднял ВМ, поднял кластер postgres и установил wal-g
![img.png](images/img.png)

#### Создал файл конфигурации для wal-g
![img.png](images/img_1.png)

#### Настроил postgresql.auto.conf
![img.png](images/img_2.png)

#### Перезапустил кластер, заполнил базу данными
![img.png](images/img_3.png)

#### Сделал бэкап
![img.png](images/img_4.png)

#### Обновил данные, сделал delta бэкап 
![img.png](images/img_5.png)

#### Создал второй кластер, восстановил данные из бэкапа
![img.png](images/img_6.png)

#### Проверил, что данные на втором кластере восстановились
![img.png](images/img_7.png)