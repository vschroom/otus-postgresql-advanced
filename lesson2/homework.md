#### Создал и подключился к ВМ, установил и запустил PostgresQL 16
![img.png](images/img.png)

#### Зашел под пользователем postgres, создал таблицу test и заполнил ее
![img.png](images/img_1.png)

#### Остановил кластер postgres-a. Создал и смонтировал новый диск к ВМ
![img.png](images/img_2.png)
![img.png](images/img_3.png)

#### Перенес содержимое /var/lib/postgresql/16 в /mnt/data/
![img.png](images/img_4.png)
#### При попытке запустить кластер postgres-a возникла ошибка - "/var/lib/postgresql/16 is not accessible"

#### Т.к. каталог для хранения данных /var/lib/postgresql/16 перенесли в директорию нового диска, указал в файле postgresql.conf для параметра data_directory новую локацию.
![img.png](images/img_5.png)

#### Кластер успешно запустился, данные таблицы test остались целыми
![img.png](images/img_6.png)



### Со звездочкой *
#### Создал вторую ВМ
![img.png](images/img_7.png)

#### Установил на нее postgres и удалил директорию с данными /var/lib/postgresql
![img.png](images/img_8.png)

#### Перемонтировал внешний диск из первой ВМ ко второй
![img.png](images/img_9.png)

#### Добавил значение в конфиг для postgres-а на второй ВМ
![img.png](images/img_10.png)

#### Запустил кластер, проверил, что сохранилась таблица с данными, которую создавал в первой ВМ
![img.png](images/img_11.png)