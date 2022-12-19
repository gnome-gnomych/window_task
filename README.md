# Лабораторная работа. Развертывание JupyterHub
---
## Этап 1. Подготовка
---
- Для начала работы необходимо установить на устройтво Docker [https://www.docker.com](https://www.docker.com).
- Необходимо скачать файл из папки данного репозитория ```/Main``` и сохранить в любой директории устройства.
---
## Этап 2. Сборка и запуск
---
- Откройте терминал и вставьте команду: ```docker build -t jupyterhub:main```, после чего нажать клавишу ```Enter```. Происходит сборка.
  - Внимание: на данном этапе терминал может выдать ошибку!
- Если сборка произошла успешно, можно приступать к следуюшему этапу- подготовке хранилища для данных. Необходимо выполнить в терминале команду:```docker volume create jupyterhubdate```. 
- Далее необходимо запустить образ, а также создать контейнер при помощи команды:```docker run -d -v jupyterhubdata:/home -p 80:8000 --name JupyterHub jupyterhub:main```.
  - Внимание: на данном этапе терминал может выдать ошибку!
---
## Этап 3. Создание аккаунта в DockerHub
---
- Откройте __Docker__.
- Перейдите во вкладку ```Containers```. Выберите ваш контейнер.
- Откройте __Terminal__ в Docker. Вставьте команду ```adduser admin``` и нажмите ```Enter```.
- В строке ```New password``` введите ```admin```. Нажмите ```Enter``` и введите ```admin``` повторно, нажмите ```Enter```.
- Далее необходимо 5 раз нажать Enter, чтобы пропустить добавление информации о пользователе.
- В строке __Is the information correct?__ введите: ```Y```.
- Поздравляем, вы успешно создали аккаует ```admin``` с паролем ```admin```!
---
## Этап 4. Авторизация в DockerHub
---
- Откройте любой браузер и перейдите по ссылке: [http://localhost:80/hub/login](http://localhost:80/hub/login).
- Аккаунт с __Username__ ```admin``` и __Password__ ```admin``` уже создан. Осталось только войти в аккаунт.
- На странице авторизации введите в поле __Username__:```admin```, а в поле __Password__:```admin```.
- Нажмите на кнопку __Sign In__
- Поздравляем, вы успешно авторизовались в DockerHub!
