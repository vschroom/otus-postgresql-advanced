#### Развернуть Greenplum в GKE или GCE. Потесировать dataset с чикагскими такси.
#### Создаем ВМ, разворачиваем Greenplum и подключаемся
![img.png](images/img.png)
![img.png](images/img_1.png)
#### Создадим бд test и загрузим 10ГБ данных в таблицу - https://console.cloud.google.com/storage/browser/chicago10 
![img.png](images/img_2.png)

#### Протетируем выполнение запросов
##### COUNT
![img.png](images/img_3.png)
##### DISTINCT
![img.png](images/img_4.png)
##### GROUP BY
![img.png](images/img_5.png)
##### JOIN
![img.png](images/img_6.png)
##### Добавим индекс на поле trip_miles
![img.png](images/img_7.png)
##### Запросы по индексу
![img.png](images/img_8.png)
![img.png](images/img_9.png)
![img.png](images/img_10.png)