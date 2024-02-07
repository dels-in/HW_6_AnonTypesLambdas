<h3>Анонимные типы, кортежи и лямбда-выражения</h3>

Цель:
В результате этого ДЗ вы подготовите три программы (проекта).
Тренируемые навыки:
Программы 1 - анонимные типы, их вывод в консоль, сравнение между собой.
Программы 2 - кортежи.
Программы 3 - лямбда-выражения, замыкания

Описание/Пошаговая инструкция выполнения домашнего задания:
<h5>Программа 1.</h5>
Создать четыре объекта анонимного типа для описания планет Солнечной системы со свойствами "Название", "Порядковый номер от Солнца", "Длина экватора", "Предыдущая планета" (ссылка на объект - предыдущую планету): Венера, Земля, Марс, Венера (снова)
Данные по планетам взять из открытых источников.
Вывести в консоль информацию обо всех созданных "планетах". Рядом с информацией по каждой планете вывести эквивалентна ли она Венере.
<h5>Программа 2.</h5>
Написать обычный класс "Планета" со свойствами "Название", "Порядковый номер от Солнца", "Длина экватора", "Предыдущая планета" (ссылка на предыдущую Планету).
Написать класс "Каталог планет". В нем должен быть список планет - при создании экземпляра класса сразу заполнять его тремя планетами: Венера, Земля, Марс.
Добавить в класс "Каталог планет" метод "получить планету", который на вход принимает название планеты, а на выходе дает порядковый номер планеты от Солнца и длину ее экватора. В случае, если планету по названию найти не удалось, то этот метод должен возвращать строку "Не удалось найти планету" (именно строку, не Exception). На каждый третий вызов метод "получить планету" должен возвращать строку "Вы спрашиваете слишком часто". Таким образом на выходе из метода должны быть три поля: первые два заполнены осмысленными значениями, когда планета найдена, а последнее поле - для ошибки.
В main-методе Вашей программы создать экземпляр "Каталога планет". У этого каталога вызвать метод "получить планету", передав туда последовательно названия Земля, Лимония, Марс. Для найденных планет в консоль выводить их название, порядковый номер и длину экватора. А для ненайденных выводить строку ошибки, которую вернул метод "получить планету".
<h5>Программа 3.</h5>
Скопировать решение из программы 2, но переделать метод "получить планету" так, чтобы он на вход принимал еще один параметр, описывающий способ защиты от слишком частых вызовов - делегат PlanetValidator (можно вместо него использовать Func), который на вход принимает название планеты, а на выходе дает строку с ошибкой. Метод "получить планету" теперь не должен проверять сколько вызовов делалось ранее. Вместо этого он должен просто вызвать PlanetValidator и передать в него название планеты, поиск которой производится. И если PlanetValidator вернул ошибку - передать ее на выход из метода третьим полем.
Из main-метода при вызове "получить планету" в качестве нового параметра передавать лямбду, которая делает всё ту же проверку, которая была и ранее - на каждый третий вызов она возвращает строку "Вы спрашиваете слишком часто" (в остальных случаях возвращает null). Результат исполнения программы должен получиться идентичный программе 2.
(*) Дописать main-метод так, чтобы еще раз проверять планеты "Земля", "Лимония" и "Марс", но передавать другую лямбду так, чтобы она для названия "Лимония" возвращала ошибку "Это запретная планета", а для остальных названий - null. Убедиться, что в этой серии проверок ошибка появляется только для Лимонии.
Таким образом, вы делегировали логику проверки допустимости найденной планеты от метода "получить планету" к вызывающему этот метод коду.