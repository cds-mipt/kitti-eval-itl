Компиляция
==========
Скомпилировать код можно командой:
```sh
g++ -O3 -DNDEBUG -o evaluate_odometry evaluate_odometry.cpp matrix.cpp
```

Валидация
=========
Для валидации, создать в корне репозитория папку с именем, например, results/ и в ней папку data/. В results/data/ положить файлы с результатами локализации. Запустить evaluate_odometry:
```sh
./evaluate_odometry results/
```
Результаты будут лежать в results/resutls.txt

