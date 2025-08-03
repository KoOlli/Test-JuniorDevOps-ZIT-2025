#### Все файлы, о которых идет речь в этом readme, есть в директории part3  

- Создаем Dockerfile  
- На один уровень с Dockerfile собираем index.html и my_site.conf  
- Запускаем при помощи команды:  
`docker build -t testZIT . && docker run -p 8080:80 testZIT`  
или можно запустить скрипт `.buildRun`  