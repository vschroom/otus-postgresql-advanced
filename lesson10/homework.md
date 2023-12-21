#### Развернуть CockroachDB в GKE или GCE. Потесировать dataset с чикагскими такси.
#### Разворачиваем инстанс CockroachDB и создаем тестовую бд
![img.png](images/img.png)
![img.png](images/img_1.png)
![img.png](images/img_2.png)
![img.png](images/img_3.png)

#### Загрузим в test 10ГБ данных - https://console.cloud.google.com/storage/browser/chicago10 
#### в среднем батчи по 250МБ на данной ВМ загружаются от 15 до 25 секунд
![img.png](images/img_4.png)

#### Протетируем выполнение запросов
##### COUNT
![img.png](images/img_5.png)
##### DISTINCT
![img.png](images/img_6.png)
##### GROUP BY
![img.png](images/img_7.png)
##### JOIN 
![img.png](images/img_8.png)
##### Добавим индекс на поле trip_miles
![img.png](images/img_9.png)
##### Запросы по индексу
![img.png](images/img_10.png)
![img.png](images/img_11.png)
![img.png](images/img_12.png)
![img.png](images/img_13.png)