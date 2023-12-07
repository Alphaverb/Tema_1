# Тема 11. Итераторы и генераторы
Отчет по Теме #11 выполнила:
- Плясунова Милена Юрьевна
- ПИЭ-21-2

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + |
| Задание 4 | + |
| Задание 5 | + |

Работу проверил:
- к.э.н., доцент Панов М.А.

# Лабораторные работы
## Лабораторная работа №1
### Простой итератор, но у него нет гибкой настройки, например его нельзя развернуть. Он работает просто как next(), но нет prev().

```python
numbers = [0, 1, 2, 3, 4, 5]
for item in numbers:
    print(item)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_11/pic/L111.png)

## Лабораторная работа №2
### Класс итератор с гибкой настройкой и удобными применением.

```python
class CountDown:
    def __init__(self, start):
        self.count = start + 1

    def __iter__(self):
        return self

    def __next__(self):
        self.count -= 1
        if self.count < 0:
            raise StopIteration
        return self.count

if __name__ == '__main__':
    counter = CountDown(5)
    for i in counter:
        print(i)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_11/pic/L112.png)

## Лабораторная работа №3
### Генератор списка.

```python
a = [i ** 2 for i in range(1, 5)]

print('a - ', a)
for i in a:
    print(i)

print('iter(a) - ', iter(a))
for i in a:
    print(i)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_11/pic/L113.png)

## Лабораторная работа №4
### Выражения генераторы.

```python
b = (i ** 2 for i in range(1, 5))
print(b)
print('first')
for i in b:
    print(i)
print('second')
for i in b:
    print(i)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_11/pic/L114.png)

## Лабораторная работа №5
### Такой же счетчик, как и в первом задании, только это генератор и использует yield.

```python
def countdown(count):
    while count >= 0:
        yield count
        count -= 1

if __name__ == '__main__':
    counter = countdown(5)
    for i in counter:
        print(i)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_11/pic/L115.png)

# Самостоятельные работы
## Самостоятельная работа №1
### Вас никак не могут оставить числа Фибоначчи, очень уж они вас заинтересовали. Изучив новые возможности Python вы решили реализовать программу, которая считает числа Фибоначчи при помощи итераторов. Расчет начинается с чисел 1 и 1. Создайте функцию fib(n), генерирующую n чисел Фибоначчи с минимальными затратами ресурсов. Для реализации этой функции потребуется обратиться к инструкции yield (Она не сохраняет в оперативной памяти огромную последовательность, а дает возможность “доставать” промежуточные результаты по одному). Результатом решения задачи будет листинг кода и вывод в консоль с числом Фибоначчи от 200.

```python
def fib(n):
    fib1 = fib2 = 1
    for i in range(n):
        yield fib1
        fib1, fib2 = fib2, fib1 + fib2

for num in fib(200):
    print(num)
```

### Результат.
#### Начало вывода:
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_11/pic/S1112.png)

#### Конец вывода:
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_11/pic/S1111.png)

## Выводы

1. Цикл for используется для итерации через генератор и вывода каждого числа Фибоначчи до 200 (включительно).
2. Ключевое слово yield используется в функции для создания генератора. Вместо того чтобы возвращать значение и завершать выполнение функции, как это делает return, yield сохраняет состояние функции, позволяя приостановить выполнение и возвращать значение. При следующем вызове генератора выполнение возобновляется с сохраненного состояния.

## Самостоятельная работа №2
### К коду предыдущей задачи добавьте запоминание каждого числа Фибоначчи в файл “fib.txt”, при этом каждое число должно находиться на отдельной строчке. Результатом выполнения задачи будет листинг кода и скриншот получившегося файла.

```python
def fib(n):
    fib1 = fib2 = 1
    with open('fib.txt', 'w') as file:
        for i in range(n):
            file.write(str(fib1) + '\n')
            yield fib1
            fib1, fib2 = fib2, fib1 + fib2

for num in fib(200):
    print(num)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_11/pic/S112.png)

## Выводы

Этот код сохраняет каждое число Фибоначчи на отдельной строке в файле 'fib.txt'. Каждый вызов file.write() добавляет число и переходит на новую строку с помощью '\n'. После завершения работы блока with файл автоматически закрывается.
