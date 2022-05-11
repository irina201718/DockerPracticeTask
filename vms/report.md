## Установка Докера
Это было легко) За два часа управилась (:
(скрины не делала, потому что много вариантов перепробовала)
1. Обновила список существующих пакетов
```javascript

$ sudo apt update

```
2. Установите пакетов, которые позволяют apt использовать пакеты через HTTPS
```javascript

$ sudo apt install apt-transport-https ca-certificates curl software-properties-common

```
3. Добавила ключ GPG для официального репозитория Docker
```javascript

$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

```
4. Добавила репозиторий Docker в источники APT
```javascript

$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

```
5. Обновила базу данных пакетов
```javascript

$ sudo apt update

```
6. Убеждаюсь, что установка будет выполняться из репозитория Docker, а не из репозитория Ubuntu по умолчанию
```javascript

$ apt-cache policy docker-ce

```
7. Установка Докера
```javascript

$ sudo apt install docker-ce

```
8. Проверка запуска
```javascript

$ sudo systemctl status docker

```
![info](/assets/images/Check_Docker.jpg)

## Создание файла mosquitto.conf
1. Создание файла
```javascript

$ nano mosquitto.conf

```
2. Заполнение файла
3. Вывод результата
```javascript

$ cat mosquitto.conf

```
![info](/assets/images/Mosquitto.conf.jpg)

## Дальше по ходу движения задания
- Аттачим, пробрасываем порты
```javascript

$ sudo docker run -v $PWD:/mosquitto/config/ -p 1883:1883 -d --name mqtt-broker eclipse-mosquitto

```
![info](/assets/images/Create.jpg)
- Проверка работы
```javascript

$ sudo docker log mqtt-broker

```









