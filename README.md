# Тема 9. Концепции и принципы ООП
Отчет по Теме #9 выполнила:
- Плясунова Милена Юрьевна
- ПИЭ-21-2

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | 
| Задание 3 | + |
| Задание 4 | + |
| Задание 5 | + |

Работу проверил:
- к.э.н., доцент Панов М.А.

# Лабораторные работы
## Лабораторная работа №1
### Допустим, что вы решили оригинально и немного странно познакомится с человеком. Для этого у вас должен быть написан свой класс на Python, который будет проверять угадал ваше имя человек или нет. Для этого создайте класс, указав в свойствах только имя. Дальше создайте функцию __init__(), а в ней сделайте проверку на то угадал человек ваше имя или нет. Также можете проверить что будет, если в этой функции указав атрибут, который не указан в вашем классе, например, попробуйте вызвать фамилию.

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
### Вам дали важное задание, написать продавцу мороженого программу, которая будет писать добавили ли топпинг в мороженое и цену после возможного изменения. Для этого вам нужно написать класс, в котором будет определяться изменили ли состав мороженого или нет. В этом классе реализуйте метод, выводящий на печать «Мороженое с {ТОППИНГ}» в случае наличия добавки, а иначе отобразится следующая фраза: «Обычное мороженое». При этом программа должна воспринимать как топпинг только атрибуты типа string.

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
### Петя – начинающий программист и на занятиях ему сказали реализовать икапсу…что-то. А вы хороший друг Пети и ко всему прочему прекрасно знаете, что икапсу…что-то – это инкапсуляция, поэтому решаете помочь вашему другу с написанием класса с инкапсуляцией. Ваш класс будет не просто инкапсуляцией, а классом с сеттером, геттером и деструктором. После написания класса вам необходимо продемонстрировать что все написанные вами функции работают. Также вас необходимо объяснить Пете почему на скриншоте ниже в консоли выводится ошибка.

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

my_electric_car = ElectricCar("Tesla", "Model S", 75)
# Создание экземпляра класса ElectricCar с маркой "Tesla", моделью "Model S" и емкостью батареи 75.
my_electric_car.drive()
my_electric_car.charge()
# Вызов методов drive (наследуемый) и charge для объекта my_electric_car.
```

![Меню](https://github.com/Alphaverb/Software_Engineering/blob/Tema_8/pic/L83.png)

## Лабораторная работа №4
### Вам прекрасно известно, что кошки и собаки являются млекопитающими, но компьютер этого не понимает, поэтому вам нужно написать три класса: Кошки, Собаки, Млекопитающие. И при помощи “наследования” объяснить компьютеру что кошки и собаки – это млекопитающие. Также добавьте какой-нибудь свой атрибут для кошек и собак, чтобы показать, что они чем-то отличаются друг от друга.

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
### На разных языках здороваются по-разному, но суть остается одинаковой, люди друг с другом здороваются. Давайте вместе с вами реализуем программу с полиморфизмом, которая будет описывать всю суть первого предложения задачи. Для этого мы можем выбрать два языка, например, русский и английский и написать для них отдельные классы, в которых будет в виде атрибута слово, которым здороваются на этих языках. А также напишем функцию, которая будет выводить информацию о том, как на этих языках здороваются. Заметьте, что для решения поставленной задачи мы использовали декоратор @staticmethod, поскольку нам не нужны обязательные параметры-ссылки вроде self.

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
### Задание Садовник и помидоры.
Классовая структура:
Есть Помидор со следующими характеристиками:
• Индекс
• Стадия созревания (стадии: отсутствует, цветение, зеленый, красный)
Помидор может:
• Расти (переходить на следующую стадию созревания)
• Предоставлять информацию о своей зрелости
Есть Куст с помидорами, который:
• Содержит список томатов, которые на нем растут
А также может:
• Расти вместе с томатами
• Предоставлять информацию о зрелости всех томатов
• Предоставлять урожай
И также есть Садовник, который имеет:
• Имя
• Растение, за которым он ухаживает
Он может:
• Ухаживать за растением
• Собирать с него урожай
Задание:
Класс Tomato:
1) Создайте класс Tomato
2) Создайте статическое свойство states, которое будет содержать все
стадии созревания помидора
3) Создайте метод __init__(), внутри которого будут определены два
динамических свойства: _index (передается параметром) и _state
Михаил А. Панов
(принимает первое значение из словаря states). После написания
этого блока кода в комментарии к нему укажите какими являются
эти два свойства
4) Создайте метод grow(), который будет переводить томат на
следующую стадию созревания
5) Создайте метод is_ripe(), который будет проверять, что томат созрел
Класс TomatoBush:
1) Создайте класс TomatoBush
2) Определите метод __init__(), который будет принимать в качестве
параметра количество томатов и на его основе будет создавать
список объектов класса Tomato. Данный список будет храниться
внутри динамического свойства tomatoes
3) Создайте метод grow_all(), который будет переводить все объекты
из списка томатов на следующий этап созревания
4) Создайте метод all_are_ripe(), который будет возвращать True, если
все томаты из списка стали спелыми.
5) Создайте метод give_away_all(), который будет чистить список
томатов после сбора урожая
Класс Gardener:
1) Создайте класс Gardener
2) Создайте метод __init__(), внутри которого будут определены два
динамических свойства: name (передается параметром, является
публичным) и _plant (принимает объект класса TomatoBush). После
написания этого блока кода в комментарии к нему укажите какими
являются эти два свойства
3) Создайте метод work(), который заставляет садовника работать, что
позволяет растению становиться более зрелым
4) Создайте метод harvest(), который проверяет, все ли плоды созрели.
Если все, то садовник собирает урожай. Если нет, то метод печатает
предупреждение
5) Создайте статический метод knowledge_base(), который выведет в
консоль справку по садоводству
Тесты:
1) Вызовите справку по садоводству
2) Создайте объекты классов TomatoBush и Gardener
3) Используя объект класса Gardener, поухаживайте за кустом с
помидорами
4) Попробуйте собрать урожай, когда томаты еще не дозрели.
Продолжайте ухаживать за ними
Михаил А. Панов
5) Соберите урожай
Результатом работы вашей программы будет листинг кода с подробными
комментариями и скриншоты выполенния всех тестов.

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
Этот код определяет класс Tank, который имеет конструктор __init__, принимающий параметр model. Внутри конструктора значение model присваивается атрибуту self.model, который является членом данного экземпляра класса. Затем создается экземпляр класса Tank с именем kv2. После этого выводится 
