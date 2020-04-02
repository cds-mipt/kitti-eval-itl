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
Необходимо создать в корне репозитория папку с именем, например, *results/*, и в ней папку *data/*. В *results/data/* положить файлы с результатами локализации. В папке *data/odometry/poses* лежат ground truth траектории. Для просмотра инструции по использованию запустить evaluate_odometry без параметров:
```sh
./evaluate_odometry
```
Для валидации запустить evaluate_odometry с нужными параметрами (например, для валидации на расстояниях 100, 200 ... 800 и построения графиков с видом сверху):
```sh
./evaluate_odometry results/ 0 top
```
Виду сверху соответствуют оси x/z, а виду сбоку - x/y. Поэтому это не ошибка, если на графике изображён вид сверху, а оси подписаны как x и z.

Результаты валидации в формате Kitti Benchmark Odometry Leaderboard будут лежать в *results/resutls.txt*:

результат по каждой из последовательности + среднее по всем  - translation error (в %) и rotation error (deg/m).

В папке results/plot_error содержатся графики ошибок по разным расстояниям.

В папке results/plot_path содержатся графики получившихся траекторий в сравнении с ground truth.

В файле *results/stats.txt* содержится оригинальный вывод Kitti Benchmark devkit: первое число - translation error (условные единицы в диапазоне от 0 до 1 (нужно домножать на 100%)), второе число - rotation error (rad/m).

Альтернативные способы валидации
=========

Инструкция по установке кода на python, оригинального и модифицированного кода - https://docs.google.com/document/d/1yTAwopheMraBgP9keqNODIOkiUDAPYALBDGLR0rPrPM/edit.<br/>
