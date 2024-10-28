# Домашнее задание RabbitMQ  
Задание 1. Установка RabbitMQ

Используя Vagrant или VirtualBox, создайте виртуальную машину и установите RabbitMQ. Добавьте management plug-in и зайдите в веб-интерфейс.  

![r1](https://github.com/user-attachments/assets/5db2f09a-54ee-4c7e-be13-1288a8c78306)


Задание 2. Отправка и получение сообщений

Используя приложенные скрипты, проведите тестовую отправку и получение сообщения. Для отправки сообщений необходимо запустить скрипт producer.py.  

producer.py  
![r4](https://github.com/user-attachments/assets/2bcec082-9d84-4bac-ad96-42b833ea42de)  
![r5](https://github.com/user-attachments/assets/c9636708-c726-4f61-96b3-171522b887a1)

consumer.py
![r3](https://github.com/user-attachments/assets/3d43d613-c9da-4942-9406-e7bf38e88237)  

Задание 3. Подготовка HA кластера  

Используя Vagrant или VirtualBox, создайте вторую виртуальную машину и установите RabbitMQ. Добавьте в файл hosts название и IP-адрес каждой машины, чтобы машины могли видеть друг друга по имени.
Затем объедините две машины в кластер и создайте политику ha-all на все очереди.В качестве решения домашнего задания приложите скриншоты из веб-интерфейса с информацией о доступных нодах в кластере и включённой политикой.  

![r6](https://github.com/user-attachments/assets/78980dfc-cb3d-452d-9ec3-692980ebff46)  
![ha](https://github.com/user-attachments/assets/5cad940c-99b7-43ae-97fa-c4ae58e43c32)

Также приложите вывод команды с двух нод:
$ rabbitmqctl cluster_status
![6](https://github.com/user-attachments/assets/b5f17c36-fe4d-432d-bb42-39fa6012c909)  
![7](https://github.com/user-attachments/assets/5f4f4761-850d-4ef6-bf40-6c23cc8b8c56)


Для закрепления материала снова запустите скрипт producer.py и приложите скриншот выполнения команды на каждой из нод:
$ rabbitmqadmin get queue='hello'  
![p](https://github.com/user-attachments/assets/b727ab62-fafa-4452-bbec-d26bec74c980)


![31](https://github.com/user-attachments/assets/2beb8d48-1c3a-43f8-a308-cce1d63da457)  
![32](https://github.com/user-attachments/assets/69889596-aa0d-4edf-8bcf-3e3c2f421b6b)

После чего попробуйте отключить одну из нод, желательно ту, к которой подключались из скрипта, затем поправьте параметры подключения в скрипте consumer.py на вторую ноду и запустите его.
![33](https://github.com/user-attachments/assets/00614f22-f84d-4b86-95ef-dafe5b576c4d)
