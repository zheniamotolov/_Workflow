#задания+указания+оценки
#Лаб.работы 1-й курс ММФ 2015-2016 уч.год

##5/11/2015 на практическом занятии возник вопрос про остаток от деления int%int если числа отрицательные.

**5%2=1 но  5%(-2)=-1 но (-5)%2=1**

Пояснение [http://ru.wikipedia.org/wiki/%D0%9E%D1%81%D1%82%D0%B0%D1%82%D0%BE%D0%BA_%D0%BE%D1%82_%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F] ниже:


| стандарт  | операция  |  результат |
|---|---|---|
| Си (ISO 1990) |	/ 	% |	Знак остатка - Не определено |
| Си (ISO 1999) |	/ 	% |	Знак остатка - Делимое|
| C++ (ISO 2003)| / 	% |	Знак остатка -Не определено|
| C++ (ISO 2011)| / 	% |	Знак остатка - Делимое|

###Обязательные требования ко всем лабам:
* Кодировка UNICODE   
* в первых строках main как комментарий должно быть записано условие задания   
* инициализация перменных обязательна  
* запрещены _в ДЗ1-3_ циклы FOR(.....) кроме нескольких заданий конкретно на эту конструкцию  

##ДЗ1##
a) сумма цифр числа до первого встреченного нуля  
b) является ли оно симметричным целое число   
c) "перевернуть" число  
d) вычислить сумму цифр стоящих на четных позициях, и стоящих на нечетных позициях, делится ли исходное число на 11  
e) вычислить E^x по Тейлору  

##ДЗ2##
a) Решение "квадратного" ур-я  
b) Наибольшая цифра числа и ее позиция в числе  
c)  вводим числа до первого отрицательного числа и выводим их сумму

##ДЗ3##
a) "Нормальный" калькулятор. Обработка ситуации деления на 0. Результат вычислений остается как текущее значение. Если вместо операции ввести символ ’c’, то калькулятор сбрасывается в начало, при вводе символа ’e’ вместо операции калькулятор завершает работу (exit).   
"Прошаренный" калькулятор (на бонус) Пользователь может вводить произвольное число чисел и операций (поочерёдно), после введения символа ’=’ выдаётся конечный результат, и калькулятор сбрасывается в начало.  
b) Покажите к чему стремится отношение соседних чисел Фибоначчи. Для этого выведите в столбик отношение последующего к предыдущему и предыдущего к последующему для первых 40 чисел Фибоначчи.  
c) Напишите игру в кости между человеком и компьютером. Они по очереди кидают по два кубика. Побеждает тот у кого сумма больше. Кубики рисуйте псевдографикой  
d) Линейный конгруэнтный генератор псевдослучайных чисел  
Для большинства программ использующих случайность достаточно не настоящих случайных чисел, а лишь чисел, которые ведут себя похожим образом. Поэтому на практике находят очень широкое применение алгоритмы генерации псевдослучайных чисел. Простейшим и обычно самым быстрым из них является *линейный конгруэнтный метод*.  
Суть метода выражается в нахождение следующего псевдослучайного числа по предыдущему по представленной формуле:  

x(n+1) = (a*x(n) + c) mod m;

где x(n+1) новое псевдослучайное число, x(n) — старое, mod это сравнимость по модулю, что практически полностью соответствует нахождению остатка при делении на m,  
1 <= a < m, 0 < c < m 
и m некоторые коэффициенты, которые и определяют последовательность псевдослучайных чисел.  
Не каждый набор коэффициентов определяет последовательность похожую на случайные числа, так например a = 7 c = 8 m = 16, порождают последовательность чередующихся 0 и 8.  
Для хорошей генерации должны быть выполнены следующие правила:  
1. Числа c и m взаимно простые;  
2. a - 1 кратно p для каждого простого p, являющегося делителем m;  
3. a - 1 кратно 4, если m кратно 4.  
Реализовать линейный конгруэнтный генератор псевдослучайных чисел.  
(a) Используя коэффициенты из википедии, например a=4096, c=150889, m=714025.  
(b) Подобрав собственные коэффициенты по правилам, не использую готовые коэффициенты из википедии.  

_е)_ (Сложная на бонус) По любому натуральному число построить следующее натуральное число с той же суммой цифр. Пример: 2104->2113 1000->10000

##ДЗ4##

###использование функций, работа с массивами

Внутри main находится только объявление переменных. Инициализация массива - отдельная функция, вывод массива - отдельная функция, поиск максимума,минимума и т.п. - отдельная функция. 
Вызов этих функций - внутри main.


а) В 2003 году Джордж Марсаглия предложил быстрый алгоритм XORShift генерации псевдослучайных  чисел с использованием XOR (в С++ эта операция обозначается через знак ^ ) и битовыми сдвигами. Алгоритм состоит из 3 действий:

tmp = XOR(x(n),x(n)<<a) ;

tmp = XOR(tmp,tmp>>b) ;

x(n+1) = XOR(tmp,tmp<<c) ;

Начальное значение x(0) можно выбирать любое. Начиная с него и начнется генерация чисел (аналогично srand(____) для начала работы с rand()). “Магические“ числа а,b и с подбираются самостоятельно. 
В частности, при 21, 35 и 4 генерируют последовательность с полным периодом равным 2^64-1.

Можно использовать числа 13,15,5.

Реализуйте этот алгоритм в качестве отдельной функции, чтобы потом выполнять задания на массивы (там где надо случайными числами заполнить массив)!

b) Объявить массив вещественных чисел размера N (число N объявить как константу равную нескольким десятков тысяч). 
Проинициализировать значения элементов массива случайными числами из промежутка от -50 до 50.
* Вывести значения в "обратном порядке" (начиная от последнего элемента и заканчивая первым).
* Вывести значения сначала элементов с нечетными коэффициентами (1-й, 3-й, 5-й,...) а затем - с четными.
* Вывести кол-во положительных и количество отрицательных элементов в массиве А.
(Проверить потом, что программа работает когда все элементы одного знака!)
* Вывести максимум и минимум в массиве А.
* Вывести кол-во максимальных и количество минимальных элементов в массиве А.
Этот поиск должен выполняться за один проход по массиву!
(Проверить потом, что программа работает на массиве {2,3,4,4,4,5,5,2,5}. В этом массиве максимум встречается 3 раза и минимум 2 раза!)
* "Перестроить" массив следующим образом :заполнить вспомогательный массив В в котором положительные значения массива А переместить в начало В, отрицательные переместить в конец массива В.
* аналогично предыдущей задаче "перестроить" массив А "на месте" (т.е. БЕЗ использования массива В) следующим образом положительные значения массива А переместить в начало А, отрицательные переместить в конец массива А.

c) Используя функции, разработанные в первом задании ДЗ4, выполнить следующие задания 
* вставить после первого нулевого элемента массива число 999 (тем самым стирая информацию в ячейке А(k-1)
* вставить после первого минимального элемента число 111
* вставить перед первым максимальным элементом число 222.  

d) Заполнить двумерный массив размера N на N (число N объявить как константу равную нескольким десятков)
* построчно слева-направо

|   |   |   |
|---|---|---|
| 1 | 2 | 3 |
| 4 |	5 |	6 |
| 7 |	8 |	9 |

* построчно справа-налево

|   |   |   |
|---|---|---|
| 3 | 2 | 1 |
| 6 |	5 |	4 |
| 9 |	8 |	7 |

* змейкой

|   |   |   |   |
|---|---|---|---|
| 1 | 8 | 9 | 16 |
| 2 |	7 |	10| 15 |
| 3 |	6 |	11| 14 |
| 4 |	5 |	12| 13 |

* плуговым письмом

|   |   |   |   |
|---|---|---|---|
| 1 | 2 | 3 | 4  |
| 8 |	7 |	6 | 5 |
| 9 |	10|	11| 12 |
| 16|	15|	14| 13 |
* по спирали

|   |   |   |   |
|---|---|---|---|
| 1 | 2 | 3 | 4  |
| 12|	13|	14| 5 |
| 11|	16|	15| 6  |
| 10|	9 |	8 | 7  |

##ДЗ5##

###использование функций, работа с массивами

Внутри main находится только объявление переменных. Инициализация массива - отдельная функция, вывод массива - отдельная функция, поиск максимума,минимума и т.п. - отдельная функция. 
Вызов этих функций - внутри main.

a) В массиве случайных целых чисел 

* первый положительный элемент и последний отрицательный элемент переставить местами.
* все четные элементы заменить максимальным элементом, а нечетные — минимальным.
* найти максимальный из элементов, встречающихся только один раз.
* найти минимальное из чисел, встречающихся более одного раза.
* определить максимальную длину последовательности равных элементов.

-------
В двумерном массиве NxM заполненном случайными натуральными числами 

* найти *седловую точку* если она там есть. Седловой точкой называется элемент матрицы который является минимумом в строке и максимумом в столбце.
* Вывести сумму элементов главной диагонали матрицы (N=M)
* Вывести сумму элементов нижнего треугольника матрицы (N=M)

b) В программе объявлен массив целых чисел фиксированной "емкости" N. Пользователь
вводит массив, затем пользователь вводит число, если такое
число есть - то печатается его индекс, если такого числа нет об этом сообщается пользова-
телю. При выполнении задания надо написать функцию, осуществляющую поиск в массиве. Она возвращает первый индекс, если таких чисел несколько, и -1 если такого числа нет.

c) В программе объявлен массив А целых чисел (размер массива 100). Пользователь
вводит число реально используемой части массива (число N). Эта часть затем заполняется случайными числами. Потом распечатываем массив. Затем удаляем первый элемент массива (сдвигая остальные элементы) и меняем N на единицу. Потом пользователь вводит произвольное число и оно добавляется в конец используемой части массива и меняем N на единицу. Потом распечатываем массив. Затем опять удаляем первый элемент массива (сдвигая остальные элементы) и меняем N на единицу. Потом пользователь вводит произвольное число и оно добавляется в конец используемой части массива и меняем N на единицу. Потом распечатываем массив.

d) В программе объявлен массив А целых чисел (размер массива 100). Пользователь
вводит число реально используемой части массива (число N). Эта часть затем заполняется последовательно числами от 1 до N. Затем пользователь вводит произвольное число и мы его помещаем в отсортированный А так, чтобы не нарушить порядок  и изменяем значение N на единицу. Затем пользователь вводит произвольное число и если оно есть в массиве (используйте ф-цию из задачи **а)**) то оно удаляется.

e) Написать программу заполнения массива А элементами в случайном порядке из массива В (заранее определенном). Например, B={'М','Д'}; или B={'Т','К','Д','В'}; 

f(**на бонус**) Написать программу "перетасовки элементов массива А".

g(**на бонус**) Написать программу "циклической перестановки элементов массива А" на k
элементов влево (потом на k элементов вправо).

##ДЗ6##

###использование массивов

Внутри main находится только объявление переменных. Инициализация массива - отдельная функция, вывод массива - отдельная функция, поиск максимума,минимума и т.п. - отдельная функция. 
Вызов этих функций - внутри main.

a) Дописать программу, которая реализует стек целых чисел на массиве (функции push, pop и дополнительную функцию с именем view, которая печатает элемент, находящийся в вершине стека).

Внутри main выполнить по очереди следующие 14 действий:
* Ввести число с кливиатуры. Поместить его в стек (push).
* Ввести еще число с кливиатуры. Поместить его в стек  (push).
* Ввести еще число с кливиатуры. Поместить его в стек  (push).
* Распечатать вершину стека (view).
* Распечатать кол-во элементов в стеке.
* Достать элемент из стека (pop). 
* Распечатать новое кол-во элементов в стеке.
* Достать элемент из стека (pop). Вывести его на экран.
* Распечатать новое кол-во элементов в стеке.
* Достать элемент из стека (pop). Вывести его на экран.
* Распечатать новое кол-во элементов в стеке.
* Попробовать достать элемент из стека (pop). Вывести предупреждение.
* Ввести число с кливиатуры. Поместить его в стек (push).
* Распечатать новое кол-во элементов в стеке.

b) В программе объявлен массив А целых элементов (размер массива 10). Пользователь
вводит массив c клавиатуры. Потом распечатываем массив. Вводим число N < 10. Затем удаляем N-ый элемент массива (сдвигая последующие элементы). 

c) В программе объявлен массив А элементов типа char (размер массива 20). Пользователь
вводит массив c клавиатуры. Затем ищем в массиве какая буква встречается чаще всего. Ее выводим на экран. (что делать, если таких букв несколько????)

d) В программе объявлен массив А элементов типа char (размер массива 20). Пользователь
вводит массив c клавиатуры. Затем заменяем последнюю встреченную в массиве букву Z на букву F. (что делать, если z нет?) 

**(на бонус) Дописать программу, которая реализует очередь 5 целых чисел на массиве (функции push, pop).**

Внутри main выполнить по очереди несколько действий, демонстрирующих, что ваша очередь работает.
_Добавить три элемента 10,20,30, обработать пару элементов, добавить еще 40,50,60,70 (так, чтобы увидеть, что элементов в очереди пять), обработать теперь следующие три элемента в очереди._


## Результаты##

|N  |Прозвішча                     | КР1 | ДЗ1 |диктант|ДЗ2|ДЗ3 |КР2 | ДЗ6 |итого  |
|--:|:-----------------------------|:---:|----:|:---:|----:|:--:|----:|:--:|----:|
|  1|Бачище Яна Александровна      |  2  |     |  не сдавала  |   не сдавала   |   не сдавала  | 4   | не сдавала   |
|  2|Бойко Максим Александрович    |  4  |     |  8  |   +?|++-?|     | +  |
|  3|Войлоков Максим Сергеевич     |  10 |     |  7  |  +  |  + | 8   | не сдавал |
|  4|Гресский Никита Олегович      |  10 |     |  9  |  +  | +  | 7   | +- нет 6d   |
|  5|Евсей Ирина Сергеевна         |  5  |     |  6  |--+  |  + | 5   | + (сама ли?)  |
|  6|Жук Дмитрий Иванович          |  5  |     |    не сдавал |+--  | +  | 5   | +- |
|  7|Климкович Надежда Викторовна  |  1  |     |  8  |     |  + | 5   | не сдавала   |
|  8|Комаровский Дмитрий Юрьевич   |  6  |     |  10 |  +- |  +-| 8   | -+ |
|  9|Крейдич Александра Алексеевна |  6  |     |  9  | -+- |  - | 4   | +- нет 6с   |
| 10|Мотолов Евгений Олегович      |  6,5|     |  8  |+-   |  - | 4   | -  | 
| 11|Рыбова Юлия Владимировна      |  7  |     |  6  |+--  |  + | 6   | +- |
| 12|Салей Олег Александрович      |  3  |     |  8  |  +  |  + | 8   | +- |
| 13|Хмельникова Надежда Алексеевна|  10 |     |  8  | +-  |  + | 6   |  + |
| 14|Шкляник Валерия Руслановна    |  7  |     |  5  |   не сдавала  | +- | 6   |  не сдавала  |
