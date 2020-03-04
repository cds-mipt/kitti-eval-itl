Скомпилировать код можно командой:<br/>
'''sh
g++ -O3 -DNDEBUG -o evaluate_odometry evaluate_odometry.cpp matrix.cpp
'''

Для валидации, создать в корне репозитория папку results/ (или любую другую) и results/data/. В results/data/ положить файлы с результатами локализации. Запустить evaluate_odometry:<br/>
'''sh
./evaluate_odometry results/<br/>
'''
Результаты будут лежать в results/resutls.txt

