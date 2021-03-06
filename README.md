# COSCO-RPS
relative positioning system for COSCO project

# Инструкция по настройке

Настройка системы производится с помощью файла 'rps.launch'. 
Для подключения системы к пакету clever в файле clever.launch должна присутствовать строка

	<arg name="rps" default="true"/>
	
Параметры для настройки:

  # Инициализация и полет
	'auto_arm' - включать ли моторы при запуске системы (False в режиме тестирования)
	'flight_time' - время полета в секундах
  
  # Позиционирование (все размеры даются в метрах)
	'cinfo_path' - путь к файлу, содержащему информацию о камере (camera_matrix, dist_coeffs)
	'first_marker' - id первого aruco-маркера
	'markers_number_x' - число маркеров по x
	'markers_number_y' - число маркеров по y 
	'markers_side' - размер стороны маркера	 
  	'markers_dist_x' - расстояние между маркерами по x
	'markers_dist_y' - расстояние между маркерами по y

  # Навигация
	'camera_angle' - угол между плоскостью контроллера и плоскостью камеры (в радианах)
	'takeoff_time' - время, которое проводит коптер в режиме взлета (значения газа и углов равны начальным, позиционирование отсутствует)
  	'hold_yaw' - включено ли удержание угла рысканья

	'thrust_0' - начальное значение газа (от 0 до 1)
	'thrust_P', 'thrust_I', 'thrust_D' - коэффициенты PID по газу
	'pitch_0' - начальное значение тангажа (в радианах)
	'pitch_P', 'pitch_I', 'pitch_D' - коэффициенты PID по тангажу
	'pitch_max' - ограничение абслютного значения тангажа (в радианах)
  	'roll_0' - начальное значение крена (в радианах)
	'roll_P', 'roll_I', 'roll_D' - коэффициенты PID по крену
	'roll_max' - ограничение абслютного значения крена (в радианах)
  
 # Комментарии
 При первоначальной настройке обязательно переводите коптер в тестовый режим с отключенными моторами (auto_arm=False)! 
