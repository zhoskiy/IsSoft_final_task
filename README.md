# Elevator system
Выполнил: Дмитрук Алексей
## Условие задания:
Есть многоэтажное здание (этажность конфигурируема). В здании есть лифты (количество конфигурируемо). На каждом этаже есть кнопки вызова "вверх" и "вниз" (общие для всех лифтов). На каждом этаже рандомно появляются люди (рандомной массы), которые хотят ехать на другой этаж (рандомный). Интенсивность генерации людей конфигурируема. 
У каждого лифта есть грузоподъемность, скорость и скорость открытия/закрытия дверей. 
У человека есть масса тела и этаж на который ему нужно.
Люди стоят в очереди на засадку в лифты (одна очередь вверх, одна вниз) не нарушая ее. Приехав на нужный этаж, человек исчезает. 

Необходимо реализовать непрерывно работающее приложение (люди появляются, вызывают лифт и едут на нужный этаж) используя многопоточность (Thread, wait, notify, sleep).
По желанию можно использовать java.util.concurrent. Так же описать выбранный алгоритм текстом (кратко). 

## Алгоритм:
После создания всех необходимых компонентов в классе House, вызывается метод createRandomHuman(), который с непрерывно с заданной интенсивностью создает на случайном этаже людей с рандомной массой и этажом, на который им нужно попасть.
В классе Floor проверяется есть ли очередь и если она есть, то вызывается лифт к этому этажу, который находится в состояние покоя. Если лифт находится на этаже, на котором есть очередь, то в лифт заходят люди, пока очередь не будет пуста, либо лифт будет заполнен. Также в лифте проверяется надо ли людям выйти на текущем этаже, и если это так, то лифт выпускает людей.
