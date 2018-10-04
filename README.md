## Лабораторная работа 3

### Инструкция
Для генерации массива со случайными числами используйте функцию `generate_random_vector`. Для этого перед функцией `main` вставьте следующий код:
```cpp
#include <algorithm>
#include <iostream>
#include <random>
#include <vector>

template<class T>
std::vector<T> generate_random_vector(std::size_t num, T min = -10, T max = 10)
{
    std::random_device rd;
    std::mt19937 e2(rd());
    std::uniform_real_distribution<> dist(min, max);

    auto lambda = [&e2, &dist] () -> T { return dist(e2); };

    std::vector<T> result(num);
    std::generate_n(result.begin(), num, lambda);
    return result;
}
```

Если вам необходимо создать массив целочисленных значений длины 10 со случайными значениями от -100 до 50, необходимо написать следующий код:
```cpp
std::vector<int> v = generate_random_vector<int>(10, -100, 50);
```

Если вам необходимо создать массив чисел с плавающей точкой длины 25, необходимо написать следующий код:
```cpp
std::vector<float> v = generate_random_vector<float>(25);
```

### Задание
1. Дан массив. Все его элементы:
    * увеличить в 2 раза;
    * уменьшить на число `a`;
    * разделить на первый элемент.

1. Определить: 
    * сумму всех элементов массива;
    * сумму квадратов всех элементов массива;
    * сумму шести первых элементов массива;
    * сумму  элементов  массива  с  `k1`-го  по  `k2`й (значения  `k1` и `k2` вводятся с клавиатуры; `k2 > k1`);
    * среднее арифметическое всех элементов массива;
    * среднее арифметическое элементов массива с `s1`-го по `s2`-й (значения s1 вводятся с клавиатуры; `s2 > s1`).

1. Дан  одномерный массив  из  20 элементов.  Переставить  первые  три  и  последние три элемента, сохранив порядок их следования.

1. Удалить из массива:
    * первый отрицательный элемент (если отрицательные элементы в массиве есть);
    * удалить  последний  четный  элемент  (если  четные  элементы  в  массиве есть).

1. Дано название города. Определить, четно или нет количество символов в нем.
1. Даны две фамилии. Определить, какая из них длиннее.
1. Даны названия трех городов. Вывести на экран самое длинное и самое короткое название.

1. Дано слово. Получить его часть, образованную идущими подряд буквами, начиная с `m`-й и кончая `n`-й.
1. Дано  слово.  Добавить  к  нему  в  начале  и  конце  столько  звездочек,  сколько букв в этом слове.
1. Дано предложение. Определить долю (в %) букв `'a'` в нем.
1. Дано предложение `"Can you can a can as a canner can can a can?"`. Заменить все слова `can` на слово `newWord` (`newWord` вводится с клавиатуры)


## Инструкция по выполнению
Напоминаю, что задания необходимо сдавать через PR и с пройденными тестами в TravisCI. Подробное описание [по ссылке](https://classroom.github.com/a/J-dNYuEp).

## Полезные ссылки и литература
* https://github.com/bmstu-iu8-cpp/cpp-beginner-2017/blob/master/lab3/lab3_1.cpp
