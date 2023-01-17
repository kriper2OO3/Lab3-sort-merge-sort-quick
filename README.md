'''
сортировки слиянием, быстрая, пирамидальная
'''
```py
from turtle import right


def merge(a, b):   #функция до исправления
    '''
    функция слияния двух отсортированных списков
    возвращает общий отсортированный список
    переписать функцию без рекурсии
    циклом, сложность равна n
    '''
    if a == [] or b == []: return a + b
    if a[0] < b[0]:
        return [a[0]] + merge(a[1:], b)
    else:
        return [b[0]] + merge(a, b[1:])


def merge_plus(a, b):  #исправленная функция
    index_a = 0
    index_b = 0
    res = []
    for i in range(len(a) + len(b)):
        # проверка на выход индекса за пределы индексации списка
        if index_a + 1 > len(a):
            res += b[index_b:]
            break
        elif index_b + 1 > len(b):
            res += a[index_a:]
            break
        # сравнение элементов списков
        # если элемент списка a > элемента списка b
        if a[index_a] < b[index_b]:
            res += [a[index_a]]  # добавляем элемент списка a в список с результатами
            index_a += 1         # увеличиваем индекст элемента списка a
        # если элемент списка b > элемента списка a
        else:
            res += [b[index_b]]  # добавляем элемент списка b в список с результатами
            index_b += 1         # увеличиваем индекст элемента списка b
    return res    # возвращаем 2 слитых отсортированных списка


def sort_merge(lst):
    if len(lst) < 2: return lst
    middle = len(lst) // 2
    left = sort_merge(lst[:middle])
    right = sort_merge(lst[middle:])
    return merge(left, right)


def sort_quick(lst):  #функция до исправления
    '''
    переписать эту функцию так
    чтобы не было три цикла
    за один цикл выбрать меньшие, большие и равные pivot
    '''
    if len(lst) < 2: return lst
    pivot = lst[0]
    left = list(filter(lambda x: x < pivot, lst))
    middle = list(filter(lambda x: x == pivot, lst))
    right = list(filter(lambda x: x > pivot, lst))
    return sort_quick(left) + middle + sort_quick(right)


def sort_quick(lst):  #исправленная функция



def sort_heap():
    return
```
