# Сортировка пузырьком #

В сортировке методом пузырька количество итераций внешнего цикла определяется длинной списка минус единица, так как когда второй элемент становится на свое место, то первый уже однозначно минимальный и находится на своем месте.

Количество итераций внутреннего цикла зависит от номера итерации внешнего цикла, так как конец списка уже отсортирован, и выполнять проход по этим элементам смысла нет.

Пусть имеется список [6, 12, 4, 3, 8].

За первую итерацию внешнего цикла число 12 переместится в конец. Для этого потребуется 4 сравнения во внутреннем цикле:

6 > 12? Нет
12 > 4? Да. Меняем местами
12 > 3? Да. Меняем местами
12 > 8? Да. Меняем местами
Результат: [6, 4, 3, 8, 12]

За вторую итерацию внешнего цикла число 8 переместиться на предпоследнее место. Для этого потребуется 3 сравнения:

6 > 4? Да. Меняем местами
6 > 3? Да. Меняем местами
6 > 8? Нет
Результат: [4, 3, 6, 8, 12]

На третьей итерации внешнего цикла исключаются два последних элемента. Количество итераций внутреннего цикла равно двум:

4 > 3? Да. Меняем местами
4 > 6? Нет
Результат: [3, 4, 6, 8, 12]

На четвертой итерации внешнего цикла осталось сравнить только первые два элемента, поэтому количество итераций внутреннего равно единице:

3 > 4? Нет
Результат: [3, 4, 6, 8, 12]

## Сортировка пузырьком с помощью циклов for/in ##

```python
from random import randint

N = 10
a = []
for i in range(N):
    a.append(randint(1, 99))
print(a, ' - случайно сгенерированный массив')

for i in range(N - 1):
    for j in range(N - i - 1):
        if a[j] > a[j + 1]:
            a[j], a[j + 1] = a[j + 1], a[j]

print(a, ' - отсортированный массив методом пузырька')
```
