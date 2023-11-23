# Тема 8. Введение в ООП
Отчет по Теме #8 выполнила:
- Плясунова Милена Юрьевна
- ПИЭ-21-2

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |

Работу проверил:
- к.э.н., доцент Панов М.А.

# Лабораторные работы
## Лабораторная работа №1
### Создайте класс “Car” с атрибутами производитель и модель. Создайте объект этого класса. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями.

```python
class Car: 
    def __init__(self, make, model):
        self.make = make
        self.model = model

my_car = Car("Toyota","Corolla")
```

### Результат.

```python
class Car:
# Определение класса с именем Car.
    def __init__(self, make, model):
"""
Метод инициализации (конструктор) класса.
Метод __init__ вызывается при создании нового объекта этого класса.
Параметры self, make и model представляют объект, производителя и модель автомобиля соответственно.
"""
        self.make = make
# Эта строка присваивает значение параметра make атрибуту make объекта self, который вызывает этот метод.
        self.model = model
# Эта строка присваивает значение параметра model атрибуту model объекта self, который вызывает этот метод.

my_car = Car("Toyota","Corolla")
# Создание объекта Car с именем my_car, в который передаются значения "Toyota" и "Corolla" для параметров make и model.
```

Таким образом, создается экземпляр класса Car с конкретным производителем и моделью.

## Лабораторная работа №2
### Дополните код из первого задания, добавив в него атрибуты и методы класса, заставьте машину “поехать”. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.

```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def drive(self):
        print(f"Driving the {self.make} {self.model}")

my_car = Car("Toyota","Corolla")
my_car.drive()
```

### Результат.
```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def drive(self):
"""
Метод класса, который выводит сообщение о том, в какой машине едут (использует значения атрибутов make и model).
"""
        print(f"Driving the {self.make} {self.model}")

my_car = Car("Toyota","Corolla")
my_car.drive()
# Вызов метода drive для объекта my_car.
# Выводится сообщение о том, в какой машине едут, используя значения атрибутов make (производитель) и model (модель).
```

![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_8/pic/L82.png)

## Лабораторная работа №3
### Создайте новый класс “ElectricCar” с методом “charge” и атрибутом емкость батареи. Реализуйте его наследование от класса, созданного в первом задании. Заставьте машину поехать, а потом заряжаться.
### Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.

```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def drive(self):
        print(f"Driving the {self.make} {self.model}")

my_car = Car("Toyota","Corolla")
my_car.drive()

class ElectricCar(Car):
    def __init__(self, make, model, battery_capacity):
        super().__init__(make, model)
        self.battery_capacity = battery_capacity

    def charge(self):
        print(f"Charging the {self.make} {self.model} with {self.battery_capacity} kWh")

my_elecic_car = ElectricCar("Tesla", "Model S", 75)
my_elecic_car.drive()
my_elecic_car.charge()
```

### Результат.
```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def drive(self):
        print(f"Driving the {self.make} {self.model}")

my_car = Car("Toyota","Corolla")
my_car.drive()

class ElectricCar(Car):
# Определение класса ElectricCar, наследующегося от Car.
    def __init__(self, make, model, battery_capacity):
"""
Конструктор __init__, который вызывает конструктор родительского класса с помощью super().
Добавляет атрибут battery_capacity (емкость батареи).
"""
        super().__init__(make, model)
        self.battery_capacity = battery_capacity

    def charge(self):
"""
Метод charge класса ElectricCar.
Выводит сообщение о том, что электромобиль определенной марки (make), модели (model) и емкости батареи (battery_capacity) заряжается.
"""
        print(f"Charging the {self.make} {self.model} with {self.battery_capacity} kWh")

my_elecic_car = ElectricCar("Tesla", "Model S", 75)
# Создание экземпляра класса ElectricCar с маркой "Tesla", моделью "Model S" и емкостью батареи 75.
my_elecic_car.drive()
my_elecic_car.charge()
# Вызов методов drive (наследуемый) и charge для объекта my_electric_car.
```

![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_8/pic/L83.png)

## Лабораторная работа №4
### Реализуйте инкапсуляцию для класса, созданного в первом задании. Создайте защищенный атрибут производителя и приватный атрибут модели. Вызовите защищенный атрибут и заставьте машину поехать. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.

```python
class Car:
    def __init__(self, make, model):
        self._make = make
        self.__model = model

    def drive(self):
        print(f"Driving the {self._make} {self.__model}")

my_car = Car("Toyota", "Corolla")
print(my_car._make)
# print(my_car.__model)
my_car.drive()
```

### Результат.

```python
class Car:
    def __init__(self, make, model):
        self._make = make
# Защищенный атрибут.
# Имя начинается с одного нижнего подчеркивания, что обозначает его доступность внутри класса и его подклассов.
        self.__model = model
# Приватный атрибут.
# Имя начинается с двух подчеркиваний. Он доступен только внутри класса.

    def drive(self):
        print(f"Driving the {self._make} {self.__model}")

my_car = Car("Toyota", "Corolla")
print(my_car._make)
# Вывод значения защищенного атрибута _make с использованием print(my_car._make).
# print(my_car.__model)
# Вывод значения приватного атрибута __model с использованием print(my_car.__model).
# Это вызовет ошибку, так как приватные атрибуты не могут быть прямо доступны извне класса.
my_car.drive()
```

![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_8/pic/L841.png)

### Попытка вызова приватного атрибута (print(my_car.__model)):
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_8/pic/L842.png)

## Лабораторная работа №5
### Реализуйте полиморфизм создав основной (общий) класс “Shape”, а также еще два класса “Rectangle” и “Circle”. Внутри последних двух классов реализуйте методы для подсчета площади фигуры. После этого создайте массив с фигурами, поместите туда круг и прямоугольник, затем при помощи цикла выведите их площади. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.

```python
class Shape:
    def area(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius * self.radius

circle = Circle(radius=3)
rectangle = Rectangle(width=4, height=5)
shapes = [rectangle, circle]

for shape in shapes:
    print(shape.area())
```

### Результат.
```python
class Shape:
# Базовый класс формы, который предоставляет метод area(). 
    def area(self):
"""
Абстрактный метод, так как онне имеет реализации (просто pass).
Он предполагает, что любой подкласс Shape должен предоставить собственную реализацию метода.
"""
        pass

class Rectangle(Shape):
# Подкласс Shape, представляет собой прямоугольник.
    def __init__(self, width, height):
"""
Конструктор __init__.
Имеет атрибуты width (ширина) и height (высота).
"""
        self.width = width
        self.height = height

    def area(self):
"""
Переопределенный метод нахождения площади.
"""
        return self.width * self.height

class Circle(Shape):
# Подкласс Shape, представляет собой круг.
    def __init__(self, radius):
"""
Конструктор __init__.
Имеет атрибут radius (радиус).
"""
        self.radius = radius

    def area(self):
"""
Переопределенный метод нахождения площади.
"""
        return 3.14 * self.radius * self.radius

rectangle = Rectangle(width=4, height=5)
circle = Circle(radius=3)
# Создание объектов прямоугольника и круга.
shapes = [rectangle, circle]
# Добавление объектов в список.

for shape in shapes:
    print(shape.area())
# Цикл, который проходится по каждой фигуре в списке shapes.
# Выводит площадь фигуры с помощью методов area.
```

![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_8/pic/L85.png)

# Самостоятельные работы
## Самостоятельная работа №1
### Самостоятельно создайте класс и его объект. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Tank:
    def __init__(self, model):
        self.model = model

kv2 = Tank("КВ-2")
print(kv2.model)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_8/pic/S81.png)

## Выводы

 
## Самостоятельная работа №2
### Самостоятельно создайте атрибуты и методы для ранее созданного класса. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Tank:
    def __init__(self, model, country, tank_type,
                 gun_caliber, firing_rate,
                 weight, engine_power, speed):
        self.model = model
        self.country = country
        self.tank_type = tank_type
        self.gun_caliber = gun_caliber
        self.firing_rate = firing_rate
        self.weight = weight
        self.engine_power = engine_power
        self.speed = speed

    def shoot(self):
        print(f"Танк {self.model} ({self.country}) стреляет из орудия калибра {self.gun_caliber} мм")

    def shots_per_minute(self, minutes):
        result = self.firing_rate * minutes
        return result

kv2 = Tank("КВ-2","СССР", "Тяжелый",
           152, 2.5,
           60.8, 640, 35)
kv2.shoot()
minutes = 5
print(f"Танк {kv2.model} выстрелил {kv2.shots_per_minute(minutes)} раз(а) за {minutes} минут")
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_8/pic/S82.png)

## Выводы


## Самостоятельная работа №3
### Самостоятельно реализуйте наследование, продолжая работать с ранее созданным классом. Оно должно отличаться, от того, что указано в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
with open('input.txt', encoding='utf-8') as f:
    data = f.read()

    excluded = [' ', '\n', '.']
    count = 0
    for letter in data:
        if letter not in excluded:
            count += 1
    letters = count

    words = len(data.split())
    lines = len(data.split('\n'))

print(f"Input file contains:\n{letters} letters\n{words} words\n{lines} lines")
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_7/pic/S73.png)

## Выводы

1. Чтобы найти количество букв в текстовом файле, необходимо составить список исключенных символов (пробел, перенос на следующую строку, точка) и проверить каждую букву (символ) на отсутствие в нем. Если буква не исключена, то к счетчику прибавляется 1.
2. Чтобы найти количество слов, данные из текста делятся на слова методом split (по умолчанию разделитель - пробел), а затем вычисляется длина получившегося списка.
3. Чтобы найти количество строк, нужно использовать метод split с разделителем \n и вычислить длину получившегося списка.

## Самостоятельная работа №4
### Самостоятельно реализуйте инкапсуляцию, продолжая работать с ранее созданным классом. Она должна отличаться, от того, что указана в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.


```python
def censor_text(text, banned_words):
    for word in banned_words:
        block = "*" * len(word)
        text = text.replace(word, block)
    return text

with open('input.txt', encoding='utf-8') as f:
    data = f.read()
    banned_words = data.split()
    text = ("Hello, world! Python IS the programming language of thE future. My\nEMAIL is....\nPYTHON is awesome!!!!")
    text_low = text.lower()

censored_text = censor_text(text_low, banned_words)

index = 0
result = ''

for letter in censored_text:
    if letter == '*':
        result += letter
        index += 1
    else:
        result += text[index]
        index += 1

print(result)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_7/pic/S74.png)

## Выводы

1. Функция censor_text принимает на вход исходный текст в нижнем регистре и список запрещенных слов. Для каждого запрещенного слова вычисляется блок со звездочками, который соответствует длине слова ("*" * len(word)). Затем в полученном тексте все встреченные запрещенные слова заменяются на такие блоки.
2. Чтобы вернуть исходный регистр некоторым нетронутым словам, пришлось прибегнуть к замене. Проверялась каждая буква (символ) из полученного зацензуренного текста - если это звездочка, то она прибавляется к результирующему тексту, а индекс увеличивается на 1, если это иная буква (символ) то к результату прибавляется буква (символ) исходого текста и индекс снова увеличивается на 1.

## Самостоятельная работа №5
### Самостоятельно реализуйте полиморфизм. Он должен отличаться, от того, что указан в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
import random

def generate(words, sentences):
    new_sentence = []
    for sentence in sentences:
        generated = sentence.replace('_', random.choice(words), 1)
        generated_again = generated.replace('_', random.choice(words), 1)
        new_sentence.append(generated_again)
    return new_sentence


with open('input.txt', 'r', encoding='utf-8') as file:
    words = file.read().split(', ')

sentences = [
    "Если бы у меня тогда был _, жизнь стала бы чуточку проще.",
    "Я решил подарить ей на день рождения _. Она была в полном восторге, я уверен!",
    "Заказал тогда по скидке _, но пришел _. Наверное, это знак."
    ]

new_sentences = generate(words, sentences)

for sentence in new_sentences:
    print(sentence)
```

### Результат.
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_7/pic/S751.png)
![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_7/pic/S752.png)

## Выводы

Функция generate принимает на вход список слов для генерации и список предложений. На основе каждого предложения из списка предложений генерируется новое предложение, которое заменяет символ '_' на случайное слово из списка words. При этом операция замены происходит два раза (сначала для generated, потом для generated_again, каждый раз заменяется только один символ для того, чтобы в предложении с двумя повторами вставленные слова не повторялись).

