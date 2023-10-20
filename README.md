# Тема 3. Операторы, условия, циклы
Отчет по Теме #3 выполнила:
- Плясунова Милена Юрьевна
- ПИЭ-21-2

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |
| Задание 6 | + |
| Задание 7 | + |
| Задание 8 | + |
| Задание 9 | + |
| Задание 10 | + |

Работу проверил:
- к.э.н., доцент Панов М.А.

# Лабораторные работы
## Лабораторная работа №1
### Создайте две переменные, значение которых будете вводить через консоль. Также составьте условие, в котором созданные ранее переменные будут сравниваться, если условие выполняется, то выведете в консоль «Выполняется», если нет, то «Не выполняется».

```python
one = int(input('Введите значение первой переменной: '))
two = int(input('Введите значение второй переменной: '))
if one >= two:
    print('Выполняется')
else:
    print('Не выполняется')
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/L21.png)

## Лабораторная работа №2
### Напишите программу, которая будет определять значения переменной меньше 0, больше 0 и меньше 10 или больше 10. Это нужно реализовать при помощи одной переменной, значение которой будет вводится через консоль, а также при помощи конструкций if, elif, else.

```python
one = int(input('Введите значение переменной: '))
if one < 0:
    print('Переменная меньше 0')
elif 0 < one < 10:
    print('Переменная больше 0 и меньше 10')
else:
    print('Переменная больше либо равна 10')
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/L22.png)

## Лабораторная работа №3
### Напишите программу, в которой будет проверяться есть ли переменная в указанном массиве используя логический оператор in. Самостоятельно посмотрите, как работает программа со значениями которых нет в массиве numbers.

```python
numbers = [1, 2, 3, 6, 8, 9]
value = int(input('Введите значение переменной: '))
if value in numbers:
    print('Переменная есть в данном массиве')
else:
    print('Переменной нет в данном массиве')
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/L23.png)

## Лабораторная работа №4
### Напишите программу, которая будет определять находится ли переменная в указанном массиве и если да, то проверьте четная она или нет. Самостоятельно протестируйте данную программу с разными значениями переменной value.

```python
numbers = [1, 2, 3, 6, 8, 9, 15, 16, 73, 321, 322]
value = int(input('Введите значение переменной: '))
if value in numbers:
    if value % 2 == 0:
        print('Переменная четная и есть в массиве numbers')
    else:
        print('Переменная нечетная и есть в массиве numbers')
else:
    print(f"Переменной нет в массиве numbers и она равна {value}")
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/L24.png)

## Лабораторная работа №5
### Напишите программу, в которой циклом for значения переменной i будут меняться от 0 до 10 и посмотрите, как разные виды сравнений и операций работают в цикле.

```python
for i in range(10):
    print('i = ', i)
    if i == 0:
        i += 2
    if i == 1:
        continue
    if i == 2 or i == 3:
        print('Переменная равна 2 или 3')
    elif i in [4, 5, 6]:
        print('Переменная равна 4, 5 или 6')
    else:
        break
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/L25.png)

## Лабораторная работа №6
### Напишите программу, в которой при помощи цикла for определяется есть ли переменная value в строке string и посмотрите, как работает оператор else для циклов. Самостоятельно посмотрите, что выведет программа, если значение переменной value оказалось в строке string. 
### Определять индекс буквы не обязательно, но если вы хотите, то это делается при помощи строки:  
### index = string.find(value)
### Вы берете название переменной, в которой вы хотите что-то найти, затем применяете встроенный метод find() и в нем указываете то, что вам нужно найти. Данная строка вернет индекс искомого объекта.

```python
a = 12
b = 5
print('Возведение в степень:', a ** b)
print('Обычное деление:', a / b)
print('Целочисленное деление:', a // b)
print('Нахождение остатка от деления:', a % b)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/L26.png)

## Лабораторная работа №7
### Напишите программу, в которой вы наглядно посмотрите, как работает цикл for проходя в обратном порядке, то есть, к примеру не от 0 до 10, а от 10 до 0. В уже готовой программе показано вычитание из 100, а вам во время реализации программы будет необходимо придумать свой вариант применения обратного цикла.

```python
line = 'Hello!'
print(line * 6)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/L27.png)

## Лабораторная работа №8
### Напишите программу используя цикл while, внутри которого есть какие-либо проверки, но быть осторожным, поскольку циклы while при неправильно написанных условиях могут становится бесконечными, как указано в примере далее.

```python
sentence = 'Hello World'
print(sentence.count('o'))
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/L28.png)
### Если поменять значения в 5 строке с 2 на 1, то код заработает.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/L28.png)

## Лабораторная работа №9
### Напишите программу с использованием вложенных циклов и одной проверкой внутри них. Самое главное, не забудьте, что нельзя использовать одинаковые имена итерируемых переменных, когда вы используете вложенные циклы.

```python
print('Hello\nWorld')
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/L29.png)

## Лабораторная работа №10
### Напишите программу с использованием flag, которое будет определять есть ли нечетное число в массиве. В данной задаче flag выступает в роли индикатора встречи нечетного числа в исходном массиве, четных чисел.

```python
sentence = 'Hello World'
print(sentence[1])
print(sentence[:5])
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/L210.png)

# Самостоятельные работы
## Самостоятельная работа №1
### Напишите программу, которая преобразует 1 в 31. 
### Для выполнения поставленной задачи необходимо обязательно и только один раз использовать:
### • Цикл for
### • *= 5
### • += 1
### Никаких других действий или циклов использовать нельзя.

```python
boolean = 0
print(bool(boolean))
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/S21.png)

## Выводы

В Python для приведения других типов данных к булевому типу, используется функция bool(). Любое значение, которое рассматривается как "ложное" (например, пустая строка, ноль, пустой список или NoneType), будет преобразовано в False. Все остальные значения будут преобразованы в True.

## Самостоятельная работа №2
### Напишите программу, которая фразу «Hello World» выводит в обратном порядке, и каждая буква находится в одной строке консоли. При этом необходимо обязательно использовать любой цикл, а также программа должна занимать не более 3 строк в редакторе кода.
### Пример вывода в консоль:
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/S22.png)

```python
one, two, three = 1, 2, 3
print(one, two, three)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/S22.png)

## Выводы

В Python возможно множественное (позиционное) присваивание - каждому имени в левой части оператора присваивания соотвестсвует объект (значение) в правой части оператора присваивания, который имеет ту же позицию. Порядок присваивания формируется слева направо.

## Самостоятельная работа №3
### Напишите программу, на вход которой поступает значение из консоли, оно должно быть числовым и в диапазоне от 0 до 10 включительно (это необходимо учесть в программе). Если вводимое число не подходит по требованиям, то необходимо вывести оповещение об этом в консоль и остановить программу. Код должен вычислять в каком диапазоне находится полученное число. Нужно учитывать три диапазона:
### • от 0 до 3 включительно
### • от 3 до 6
### • от 6 до 10 включительно
### Результатом работы программы будет выведенный в консоль диапазон. Программа должна занимать не более 10 строчек в редакторе кода

```python
num = int(input('Введите целое число: '))
print("Вы ввели: ", num)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/S231.png)
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/S232.png)

## Выводы

Функция int() в Python возвращает целое число в десятичной системе счисления, где аргумент - число или строка, которую можно преобразовать в целое число, т.е. строка должна быть символьным представлением целого числа, в противном случае сгенерируется исключение типа ValueError.

## Самостоятельная работа №4
### Манипулирование строками. Напишите программу на Python, которая принимает предложение (на английском) в качестве входных данных от пользователя. Выполните следующие операции и отобразите результаты:
### • Выведите длину предложения.
### • Переведите предложение в нижний регистр.
### • Подсчитайте количество гласных (a, e, i, o, u) в предложении.
### • Замените все слова "ugly" на "beauty".
### • Проверьте, начинается ли предложение с "The" и заканчивается ли на "end".
### Проверьте работу программы минимум на 3 предложениях, чтобы охватить проверку всех поставленных условий.

```python
line = 'hot'
print(line * 6)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/S24.png)

## Выводы

Умножение строк в Python осуществляется с помощью оператора умножения *, который принимает два операнда: строку для умножения и число, на которое нужно умножить строку. Операцию умножения удобно использовать, если строку нужно продублировать много раз без ручного ввода.

## Самостоятельная работа №5
### Составьте программу, результатом которой будет данный вывод в консоль:
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/S25.png)
### Программу нужно составить из данных фрагментов кода:
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/S25.png)
### Строки кода можно использовать только один раз. Не обязательно использовать все строки кода.


```python
day, month, year = 13, 'десятый', 2023
print(f"Сегодня {int(day)} день, {str(month)} месяц, {int(year)} год.", end=" Всего хорошего!")
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_2/pic/S25.png)

## Выводы

1. F-строки (formatted string literals) в Python позволяют создавать строки, которые могут включать значения переменных и выражений, которые вычисляются во время выполнения программы. Для создания F-строки используется префикс f перед строкой, а значения переменных и выражений заключаются в фигурные скобки {}. 
2. end — это строка, которая добавляется после последнего значения. По умолчанию — это перенос на новую строку (\n). С помощью аргумента end программист может самостоятельно определить окончание выражения print.
3. Функция str() возвращает строковое представление объекта.
