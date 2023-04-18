**Исключение в программировании**

import os
os.system('cls')

import random
#переменные для хранения длины списка
list_a_length = random.randint(0, 2)
list_b_length = random.randint(0, 2)
#переменные для хранения случайных значение в диапозоне 0 - 2
list_a = [random.randint(0, 2) for _ in range(list_a_length)]
list_b = [random.randint(0, 2) for _ in range(list_b_length)]

#функция выситания индексов из списка А списком Б
def subtract_lists(list_a, list_b):
    #блок для исключений
    try:
        if len(list_a) != len(list_b):
            raise ValueError("Длины списков не совпадают.") #проверка длин списков
        new_list = [] #здесь хранится результат вычитания
        #цикл проходит по элементам списка а
        for i in range(len(list_a)):
            new_list.append(list_a[i] - list_b[i])
        print("Результат вычитания: ", new_list)
    except IndexError:
        print("Вне диапазона.")
    except ValueError as e:
        print(e)
        print("Попробуйте еще раз!")
        return []
    return new_list
#вывод результатов
print("----------------------")
print("Сгенерированные массивы: ", list_a,"/", list_b)
print("----------------------")
subtract_lists(list_a, list_b)

**------------------------**

import os
os.system('cls')

import random
#переменные для хранения длины списка
list_a_length = random.randint(0, 2)
list_b_length = random.randint(0, 2)
#переменные для хранения случайных значение в диапозоне 0 - 2
list_a = [random.randint(0, 2) for _ in range(list_a_length)]
list_b = [random.randint(0, 2) for _ in range(list_b_length)]
#функция деления индексов из списка А списком Б
def divide_lists(list_a, list_b):
    if len(list_a) != len(list_b):
        print("Длины списков не совпадают") #проверка длин списков
    
    new_listd = [] #хранение результата деления
    #проход по списку А
    for i in range(len(list_a)):
        if list_b[i] == 0:
            raise ZeroDivisionError("На ноль делить нельзя")
        new_listd.append(list_a[i] / list_b[i]) #деление
    return new_listd 
try:
    list_d = divide_lists(list_a, list_b)
except ValueError:
    print("Длины списков не совпадают")
except ZeroDivisionError:
    print("На ноль делить нельзя")
except IndexError:
    print("Вне диапозона")
else:
    print("Результат деления: ", list_d)
finally:
    print("Попробуйте еще раз!")

print("----------------------")
print("Сгенерированные массивы: ", list_a,"/", list_b)
print("----------------------")

**2 задание по исключениям**

import os
os.system('cls')
#начинаем с цикда, чтобы каждый раз запрашивать у пользователя ввести число
while True:
    num_f = input("Введи дробное число: ").strip()
    if not num_f:
        print("Ошибка: Введена пустая строка!")
    else:
        try:
            num_f = float(num_f)
            print("Отлично! Это дробное число:", num_f)
            break
        except ValueError:
            print("Ошибка: Введи дробное число!")