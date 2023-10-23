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
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/L31.png)

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
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/L32.png)

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
#### Переменная есть в массиве:
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/L33.png)
#### Переменной нет в массиве:
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/L332.png)

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
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/L34.png)
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/L342.png)
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/L343.png)

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
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/L35.png)

## Лабораторная работа №6
### Напишите программу, в которой при помощи цикла for определяется, есть ли переменная value в строке string и посмотрите, как работает оператор else для циклов. Самостоятельно посмотрите, что выведет программа, если значение переменной value оказалось в строке string. 
### Определять индекс буквы не обязательно, но если вы хотите, то это делается при помощи строки:  
### index = string.find(value)

```python
string = 'Привет всем изучающим Python!'
value = input()
for i in string:
    if i == value:
        index = string.find(value)
        print(f"Буква '{value}' есть в строке под {index} индексом")
        break
else:
    print(f"Буквы '{value}' нет в указанной строке")

```

### Результат.
#### Программа выводит первую по индексу подходящую переменную value из строки string:
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/L36.png)

## Лабораторная работа №7
### Напишите программу, в которой вы наглядно посмотрите, как работает цикл for, проходя в обратном порядке, то есть, к примеру не от 0 до 10, а от 10 до 0. В уже готовой программе показано вычитание из 100, а вам во время реализации программы будет необходимо придумать свой вариант применения обратного цикла.

#### Готовая программа:
```python
value = 100
for i in range(10, -1, -1):
    value -= i
    print(i, value)
```

#### Измененная программа:
```python
string = 'КОТ'
index = len(string) - 1
for i in range(index, -1, -1):
    word = string[index]
    print(word, index)
    index -= 1
```

### Результат.
#### Готовая программа:
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/L37.png)
#### Измененная программа, выводит буквы строки в обратном порядке с соотвественным индексом:
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/L372.png)

## Лабораторная работа №8
### Напишите программу используя цикл while, внутри которого есть какие-либо проверки. Будьте осторожны, поскольку циклы while при неправильно написанных условиях могут становится бесконечными.

#### Бесконечный цикл:
```python
value = 0
while value < 100:
    if value == 0:
        value += 10
    elif value // 5 > 2:
        value *= 5
    else:
        value -= 5
    print(value)
```

#### Исправленный вариант:
```python
value = 0
while value < 100:
    if value == 0:
        value += 10
    elif value // 5 > 1:
        value *= 5
    else:
        value -= 5
    print(value)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/L381.png)
#### Если поменять значения в 5 строке с 2 на 1, то код заработает (поскольку поступающая на вход 10 делится на 5, давая в результате частное 2, в первом случае строгий знак равенства > 2 не позволял циклу пройти второе условие).
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/L382.png)

## Лабораторная работа №9
### Напишите программу с использованием вложенных циклов и одной проверкой внутри них. Самое главное, не забудьте, что нельзя использовать одинаковые имена итерируемых переменных, когда вы используете вложенные циклы.

```python
value = 0
for i in range(10):
    for j in range(10):
        if i != j:
            value += j
        else:
            pass
print(value)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/L39.png)

## Лабораторная работа №10
### Напишите программу с использованием flag, которое будет определять, есть ли нечетное число в массиве. В данной задаче flag выступит в роли индикатора встречи нечетного числа в исходном массиве.

```python
even_array = [2, 4, 6, 8, 9]
flag = False
for value in even_array:
    if value % 2 == 1:
        flag = True
if flag is True:
    print('В массиве есть нечетное число')
else:
    print('В массиве все числа четные')
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/L310.png)

# Самостоятельные работы
## Самостоятельная работа №1
### Напишите программу, которая преобразует 1 в 31. 
### Для выполнения поставленной задачи необходимо обязательно и только один раз использовать:
### • Цикл for
### • *= 5
### • += 1
### Никаких других действий или циклов использовать нельзя.

```python
value = 1
print ('Начальное значение:', value)
for i in range(2):
    value *= 5
    value += 1
print('Результат:', value)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/S31.png)

## Выводы

В цикле for итерации происходят от 0 до 1. 
- На итерации 0 значение value, равное 1, умножается на 5 и увеличивается на 1, в результате чего получается 6. 
- На итерации 1 значение value, равное 6, вновь умножается на 5 и увеличивается на 1, в результате чего значение value равно 31.

## Самостоятельная работа №2
### Напишите программу, которая фразу «Hello World» выводит в обратном порядке, и каждая буква находится в одной строке консоли. При этом необходимо обязательно использовать любой цикл, а также программа должна занимать не более 3 строк в редакторе кода.

```python
string = 'Hello World'
for i in range(len(string)-1, -1, -1):
    print(string[i])
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/S32.png)

## Выводы

Цикл начинает выполнение с последнего индекса строки - для этого используется функция len(string)-1, так как индексация строки начинаются с 0. Конечный индекс задан как -1 (не включительно), то есть цикл будет идти до индекса 0 (первого символа строки). Шаг каждой итерации равен -1, то есть цикл будет уменьшать индекс строки на 1. В каждой итерации цикла выписывается буква с заданным индексом.

## Самостоятельная работа №3
### Напишите программу, на вход которой поступает значение из консоли, оно должно быть числовым и в диапазоне от 0 до 10 включительно (это необходимо учесть в программе). Если вводимое число не подходит по требованиям, то необходимо вывести оповещение об этом в консоль и остановить программу. Код должен вычислять в каком диапазоне находится полученное число. Нужно учитывать три диапазона:
### • от 0 до 3 включительно
### • от 3 до 6
### • от 6 до 10 включительно
### Результатом работы программы будет выведенный в консоль диапазон. Программа должна занимать не более 10 строчек в редакторе кода

```python
value = int(input('Введите число от 0 до 10: '))
if 0 <= value <= 10:
    if 0 <= value <= 3: print('Число находится в диапазоне [0; 3]')
    elif 3 < value < 6: print('Число находится в диапазоне (3; 6)')
    elif 6 <= value <= 10: print('Число находится в диапазоне [6; 10]')
else:
    print("Введенное число не в диапазоне!")
    exit()
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/S331.png)
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/S332.png)
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/S333.png)
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/S334.png)

## Выводы

1. Если блок выражений if состоит только из одной строки, он может располагаться на той же строке, что и оператор if.
2. Допустимо объединить операторы сравнения в форме 'a < b < c' (при этом это будет идентично форме написания с использованием логических операторов, пример - 'a < b and b < c' )
3. Функция exit() позволяет в любой момент остановить выполнение скрипта или программы. Это может понадобиться для обработки ошибок, тестирования и отладки, остановки программы при (не)соблюдении каких-то условий.

## Самостоятельная работа №4
### Манипулирование строками. Напишите программу на Python, которая принимает предложение (на английском) в качестве входных данных от пользователя. Выполните следующие операции и отобразите результаты:
### • Выведите длину предложения.
### • Переведите предложение в нижний регистр.
### • Подсчитайте количество гласных (a, e, i, o, u) в предложении.
### • Замените все слова "ugly" на "beauty".
### • Проверьте, начинается ли предложение с "The" и заканчивается ли на "end".
### Проверьте работу программы минимум на 3 предложениях, чтобы охватить проверку всех поставленных условий.

```python
vowels = ['a', 'e', 'i', 'o', 'u', 'A', 'E', 'I', 'O', 'U']
countV = 0

string = (input('Введите предложение на английском: '))
print('Длина предложения: ', len(string))
print('Предложение в нижнем регистре: ', string.lower())

for i in range(0, len(string)-1, 1):
    for j in range(0, len(vowels)-1, 1):
        if vowels[j] == string[i]:
            countV += 1
print(f"Количество гласных в предложении: {countV}")

if "ugly" in string:
    noUgly = string.replace("ugly", "beauty")
    print('Замена ugly на beauty: ', noUgly)

if string.startswith('The'):
    print('Строка начинается на The')
else:
    print('Строка не начинается на The')

if string.endswith('end'):
    print('Строка заканчивается на end')
else:
    print('Строка не заканчивается на end')
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/S341.png)
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/S342.png)
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/S343.png)

## Выводы

1. Для нахождения всех гласных в предложении был использован вложенный цикл. Задача решена полным перебором букв введенного предложения и букв списка с гласными vowels. 
- Сначала запускается внешний цикл, который отвечает за перебор букв введенной строки. Внешний цикл фиксирует очередное значение итерируемой переменной i, с каждым шагом цикла будет смещение по индексу на следующую букву.
- Далее запускается внутренний цикл, отвечающий за перебор букв из списка vowels и изменяющий значение итерируемой переменной j. Она обозначает смещение по элементу списка. Таким образом, проверяется соответсвие буквы из предложения и буквы из списка гласных.
2. Функция replace() в Python возвращает копию строки, в которой все вхождения подстроки заменяются другой подстрокой.
3. Метод startswith() возвращает True, если строка начинается с указанного префикса (строки). Если нет, возвращается False.
4. Метод endwith() возвращает True, если строка заканчивается указанным суффиксом. Если нет, возвращается False.

## Самостоятельная работа №5
### Составьте программу, результатом которой будет данный вывод в консоль:
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/S301.png)
### Программу нужно составить из данных фрагментов кода:
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/S302.png)
### Строки кода можно использовать только один раз. Не обязательно использовать все строки кода.


```python
values = [0, 2, 4, 6, 8, 10]
counter = 0
string = 'hello'
memory = ' world'

while counter != 10:
    if counter in values:
        print(string + memory)
        print(string)
    counter += 1
string = string + ' world'
memory = string
print(memory)

```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_3/pic/S35.png)

## Выводы

Пока счетчик (counter) не равен 10, выполняется цикл while. Если значение счетчика равняется какому-либо числу из списка values, то происходит вывод строк 'hello world' и 'hello'. На каждом шаге цикла значение counter увеличивается на 1. Условие 'if counter in values' проходит по всем элементам values, кроме 10, значит всего будет выведено 5 строк 'hello world' и 'hello'. После окончания цикла while для переменной string определяется новое значение - 'string + ' world''. После переменной memory присваиваем значение string и выводим ее в консоль. Программа завершена, итог - всего вывелось 5 строк 'hello' и 6 строк 'hello world'.
