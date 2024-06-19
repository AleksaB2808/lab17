# lab17
def reverse_list_generator(input_list):
    for element in reversed(input_list):
        yield element
Опис: Генератор, який повертає елементи списку input_list у зворотному порядку.
Використання: Зручний для ітерації по списку в зворотньому напрямку без створення нового оберненого списку у пам'яті.
Функція cartesian_product_generator

def cartesian_product_generator(list1, list2):
    for item1 in list1:
        for item2 in list2:
            yield (item1, item2)
Опис: Генератор, який обчислює декартовий добуток двох списків list1 і list2.
Використання: Дозволяє отримати всі можливі пари елементів із двох списків.
Функція tuple_list_generator

def tuple_list_generator(input_list):
    for tup in input_list:
        yield tup
Опис: Генератор, який повертає елементи кортежів зі списку input_list.
Використання: При потребі ітерувати по кожному кортежу, що міститься у списку.
Функція parallel_lists_generator

def parallel_lists_generator(*lists):
    for items in zip(*lists):
        yield items
Опис: Генератор, який паралельно ітерується по елементах кількох списків, що передаються як аргументи.
Використання: Дозволяє отримати пари (або кортежі) елементів з кожного списку на відповідних позиціях.
Функція flatten_list_generator

def flatten_list_generator(nested_list):
    for item in nested_list:
        if isinstance(item, list):
            yield from flatten_list_generator(item)
        else:
            yield item
Опис: Генератор, який розгортає вкладені списки, повертаючи всі елементи у плоский список.
Використання: Корисний для обробки вкладених структур даних, де потрібно ітерувати по всіх елементах, незалежно від рівня вкладеності.
Функція running_sum_generator

def running_sum_generator(values):
    running_total = 0
    for val in values:
        running_total += val
        yield running_total
Опис: Генератор, який обчислює накопичувальну суму для послідовності чисел values.
Використання: Для отримання суми елементів на кожному кроці ітерації, що надає зручність у деяких обчисленнях і аналізах даних.
Функція running_product_generator

def running_product_generator(values):
    running_total = 1
    for val in values:
        running_total *= val
        yield running_total
Опис: Генератор, який обчислює накопичувальний добуток для послідовності чисел values.
Використання: Підходить для отримання добутку елементів на кожному кроці ітерації, корисний при обчисленнях, де потрібно тримати під контролем точність або об'єм даних.
Генератори, що працюють з числовими послідовностями
Функція powers_of_two_generator

def powers_of_two_generator(power_limit):
    for i in range(power_limit + 1):
        yield 2 ** i
Опис: Генератор, який створює послідовність степенів числа 2 від 2^0 до 2^power_limit.
Використання: Корисний для генерування степеневих послідовностей чисел, де кожне наступне число є потрібною степенню базового числа.
Функція powers_of_base_generator

def powers_of_base_generator(base, max_limit):
    exponent = 0
    result = 1
    while result <= max_limit:
        yield result
        exponent += 1
        result = base ** exponent
Опис: Генератор, який обчислює послідовність степенів числа base до досягнення максимального ліміту max_limit.
Використання: Призначений для створення степеневих послідовностей будь-якої базової числової системи, де кожне наступне число є потрібною степенню базового числа.
Функція squares_generator

def squares_generator(start_val, end_val):
    for val in range(start_val, end_val + 1):
        yield val ** 2
Опис: Генератор, який обчислює квадрати чисел від start_val до end_val.
Використання: Підходить для генерації квадратних числових послідовностей, де кожне число є квадратом вхідного числа.
Функція cubes_generator

def cubes_generator(start_val, end_val):
    for val in range(start_val, end_val + 1):
        yield val ** 3
Опис: Генератор, який обчислює куби чисел від start_val до end_val.
Використання: Корисний для генерації кубічних числових послідовностей, де кожне число є кубом вхідного числа.
Функція factorials_generator

def factorials_generator(limit):
    def factorial(n):
        if n == 0 or n == 1:
            return 1
        else:
            return n * factorial(n - 1)

    for i in range(limit + 1):
        yield factorial(i)
Опис: Генератор, який обчислює факторіали чисел від 0 до limit.
Використання: Для створення послідовності факторіалів чисел, корисний для обчислень у комбінаториці, математиці та статистиці.
Функція collatz_sequence_generator

def collatz_sequence_generator(number):
    while number != 1:
        yield number
        if number % 2 == 0:
            number = number // 2
        else:
            number = 3 * number + 1







