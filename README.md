Скомпилировать код можно командой:
g++ -O3 -DNDEBUG -o evaluate_odometry evaluate_odometry.cpp matrix.cpp

Для валидации, создать в корне репозитория папку results/ (или любую другую) и results/data/. В results/data/ положить файлы с результатами локализации. Запустить evaluate_odometry:
./evaluate_odometry results/
Результаты будут лежать в results/resutls.txt

