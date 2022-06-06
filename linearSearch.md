# Линейный поиск #

Линейный поиск – один из самых простых алгоритмов поиска и самый простой для понимания. Мы можем думать об этом как о расширенной версии нашей собственной реализации оператора Python in .

## Алгоритм ##

Алгоритм состоит из итерации по массиву и возврата индекса первого вхождения элемента после его нахождения:

## Реализация ##

```python
def LinearSearch(lys, element):
    for i in range (len(lys)):
        if lys[i] == element:
            return i
    return -1
```

Итак, если мы используем функцию для вычисления:

```python
print(LinearSearch([1,2,3,4,5,2,1], 2))
```

После выполнения кода нас встречают:

```python
1
```

Это индекс первого вхождения элемента, который мы ищем, имея в виду, что индексы Python основаны на 0.

## Время сортировки ##

Временная сложность линейного поиска равна O(n) , что означает, что время, затраченное на выполнение, увеличивается с увеличением количества элементов в нашем входном списке lys .