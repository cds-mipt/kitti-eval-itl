Для удобства использования стандартный kitti evaluation devkit был модернизирован, чтобы получать удобную статистику по каждой из последовательностей.

Установка
==========

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
Необходимо создать в корне репозитория папку с именем, например, *results/*, и в ней папку *data/*. В *results/data/* положить файлы с результатами локализации. В папке *data/odometry/poses/* лежат ground truth траектории. Для просмотра инструции по использованию программы запустить evaluate_odometry без параметров:
```sh
./evaluate_odometry
```
Параметры:  
1. Путь к папке с результатами (пример оформления такой папки описан выше на примере папки *results/*).  
2. Номер набора расстояний для валидации.  
    0: {100.0, 200.0, 300.0, 400.0, 500.0, 600.0, 700.0, 800.0}  
    1: {5.0, 10.0, 25.0, 50.0, 75.0, 100.0, 150.0, 200.0}  
3. Вид сверху или сбоку при построении графиков.  
    x/z: вид сверху  
    x/y: вид сбоку

Путь к ground truth траекториям *(data/odometry/poses/)* фиксирован и его через параметры передать нельзя.  

Для валидации запустить evaluate_odometry с нужными параметрами (например, для валидации на расстояниях 100, 200 ... 800 и построения графиков с видом сверху):
```sh
./evaluate_odometry results/ 0 x/z
```

Результаты валидации в формате Kitti Benchmark Odometry Leaderboard будут лежать в *results/resutls.txt*:

результат по каждой из последовательности + среднее по всем  - translation error (в %) и rotation error (deg/m).

В папке results/plot_error содержатся графики ошибок по разным расстояниям.

В папке results/plot_path содержатся графики получившихся траекторий в сравнении с ground truth.

В файле *results/stats.txt* содержится оригинальный вывод Kitti Benchmark devkit: первое число - translation error (условные единицы в диапазоне от 0 до 1 (нужно домножать на 100%)), второе число - rotation error (rad/m).

Альтернативные способы валидации
=========

Инструкция по установке кода на python, оригинального и модифицированного кода - https://docs.google.com/document/d/1yTAwopheMraBgP9keqNODIOkiUDAPYALBDGLR0rPrPM/edit.<br/>
