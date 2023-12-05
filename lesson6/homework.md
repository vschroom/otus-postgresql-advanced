#### Создал 3 ВМ для etcd, сконфигурировал и запустил etcd
![img.png](images/img.png)
![img.png](images/img_1.png)

#### Создал ещё 3 ВМ для Postgresql и Patroni, установил на них Postgresql, проверил доступность нод etcd
![img.png](images/img_2.png)
![img.png](images/img_3.png)

#### Установил и сконфигурировал Patroni на всех ВМ
![img.png](images/img_4.png)

#### Создал еще 1 ВМ для HaProxy
![img.png](images/img_5.png)

#### Установил HaProxy, проверил, что доступ до кластера Postgres есть c 2мя сломанными нодами Patroni
![img.png](images/img_6.png)
![img.png](images/img_7.png)
