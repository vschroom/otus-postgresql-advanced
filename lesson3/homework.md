#### Создал ВМ, поставил Docker Engine
![img.png](images/img.png)

#### Создал каталог - /var/lib/postgres
![img.png](images/img_1.png)

#### Развернул контейнер postgres, смонтировал в него директорию /var/lib/postgres
![img.png](images/img_2.png)

#### Поднял контейнер с клиентом и добавил несколько записей в контейнер с сервером postgres-а
![img.png](images/img_3.png)

#### Удалил контейнер postgres и запустил заново
![img.png](images/img_4.png)

#### Подключился через клиент и проверил, что данные остались целыми
![img.png](images/img_5.png)