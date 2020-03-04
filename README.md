Устрановка
==========
Инструкция по установке оригинального кода - https://docs.google.com/document/d/1yTAwopheMraBgP9keqNODIOkiUDAPYALBDGLR0rPrPM/edit.<br/>
Установка зависимостей:
```sh
sudo apt-get install texlive-extra-utils
sudo apt-get install gnuplot
```
Компиляция:
```sh
g++ -O3 -DNDEBUG -o evaluate_odometry evaluate_odometry.cpp matrix.cpp
```

Валидация
=========
Необходимо создать в корне репозитория папку с именем, например, *results/*, и в ней папку *data/*. В *results/data/* положить файлы с результатами локализации. В папке *data/odometry/poses* лежат ground truth траектории. Для валидации запустить evaluate_odometry:
```sh
./evaluate_odometry results/
```
Результаты валидации будут лежать в *results/resutls.txt*.

