# "Автоматизация рутинных задач с помощью Python. Практическое руководство для начинающих", Эл Свейгарт

## Глава 1

Прочитал первую главу книги Эла Свейгарта. Книга предназначена для тех, кому будет достаточно научиться писать короткие полезные программы. Материал книги предназначен для автоматизации простых задач, например в процессе контроля за качеством программного продукта:

- перемещение и переименование тысяч файлов (может быть логов?) и их сортировка по папкам;
- заполнение онлайновых форм без ввода данных вручную (тестирование пользовательского интерфейса?);
- загрузка файлов или копирование текста с веб-сайта при его обновлении;
- и так далее.

**Сделано хорошо**

- В первой же главе предлагается разобрать несколько примеров для работы с интерактивной оболочкой Python. По одной команде за один раз и сразу же видеть результаты. Подход - когда делаешь что-то своими руками, а не просто читаешь книгу, все запоминается гораздо лучше.

- В главе даны упражнения с простыми математичеcкими действиями для улучшения процесса запоминания:

  ```python
  >>> 2 ** 8
  >>> 23 // 7
  >>> 23 % 7
  ```

- В первой же главе есть пример первой программы, которую можно запустить в интерактивной оболочке IDLE или PyCharm:

  ```python
  # -*- coding: utf-8 -*-
  # Эта программа приветствует пользователя и запрашивает
  # ввод информации.
  
  print('Hello world!')
  print('What is your name?')
  myName = input()
  print(' It is good to meet you, ' + myName)
  print('The length of your name is: ')
  print(len(myName))
  print('What is your age?')
  myAge = input()
  print('You will be ' + str(int(myAge) + 1) + ' in a year.')
  ```

- В конце книги есть контрольные вопросы для оценки понимания материала. Например, "*В этой главе введены выражения присваивания наподобие `spam = 10`. В чем суть различия между выражениями и инструкцией?*".

**Сделать лучше**

- На примере первой главы не удалось установить, что можно сделать лучше.

**Вывод**

Эл Свейгарт очень доходчиво объясняет работу Python. Примеры для IDLE позволяют тут же на практике опробовать работу с языком программирования. По результатам прочтения первой же главы получилось написать первую программу для генерации строки заданной длины:

```python
# -*- coding: utf-8 -*-

print('Какой длины строку необходимо создать?')
digital = input()
result = '1' * int(digital)
print('Ваше число - ' + result)
```

**Вопросы**

- Каков объем первой главы? 38-57/573

- Какие есть семь математических операторов Python? 40/573 страниц

- Что такое тип данных? 42/573

- Какие три типа данных есть в Python? 42/573

- Что такое конкатенация строк? 43/573

- Что такое репликация строк? 43/573

- Что такое переменная? 44/573

- Что такое инструкция присваивания? 44/573

- Что такое инициализация переменной? 45/573

- Что такое перезапись переменной? 45/573

- Какие есть три требования для имен переменных в Python? 46/573

- Какой комбинацией клавиш запустить код? `Ctrl + Shift + F10`

- Какой комбинацией клавиш запустить файл в IDLE? `F5`

- Почему выражение выдает ошибку?

  ```python
  >>> print('I am ' + 29 + ' years old.')
  Traceback (most recent call last):
    File "<pyshell#3>", line 1, in <module>
      print('I am ' + 29 + ' years old.')
  TypeError: must be str, not int
  ```

  Если оператор `+` применяется к двум значениям, являющиймся числами, то он трактуется как оператор сложения. Но если оператор `+` применить к двум строковым значениям, то он объединяет их в одну строку, играя роль оператора *конкатенации строк*. Оператор конкатенации приведет выражение к новому строковому значению, объединяющему текст обеих исходных строк. Если же попытаться применить оператор `+` к строке и целому числу, то Python не сможет определить, чего именно от него хотят. Python предположил, что имеет место попытка конкатенировать строки с целочисленными значениями. Python не может автоматически выполнить преобразование целых чисел в строки. Оператор `+` можно использовать лишь для сложения двух чисел и конкатенации двух строк. Сложить число со строкой невозможно, потому что это запрещено грамматикой Python.

- При помощи какой функции можно преобразовать целое число в строкову форму? 52/573 Функцию `str()` удобно использовать в тех случаях, когда есть целое или вещественное число, которое необходимо конкатенировать со строкой.

- Что за 3.14? Иррациональное число пи - математическая постоянная, равная отношению длины окружности к ее диаметру. Десятичное представление никогда не заканчивается. Трансцендетное число, то есть не может быть корнем какого-либо многочлена с целым коэффициентом

- Что такое иррациональное число и какие еще бывают?

- Что такое многочлен?

- Как использовать вычислением с использованием значения, которое было введено в интерактивной оболочке при помощи функции `input()`? Воспользоваться функцией `int()` для получения целочисленной формы. Например, `spam = int(spam)`

- Какой есть вариант для округления вниз вещественных числе в интерактивной оболочке Python? 54/573 Использовать функцию `int()`, например `int(7.7) + 1`

- В этой главе введены выражения присваивания наподобие `spam = 10`. В чем суть различия между выражениями и инструкцией?

- Для чего нужна функция `round()`?

**Проблемы с которыми столкнулся**

- Исходный код из примера книги

  ```python
  # Эта программа приветствует пользователя и запрашивает
  # ввод информации.
  
  print('Hello world!')
  print('What is your name?') # запрос имени
  myName = input()
  print(' It is good to meet you, ' + myName)
  print('The length of your name is: ')
  print(len(myName))
  print('What is your age?') # запрос возраста
  myAge = input()
  print('You will be ' + str(int(myAge) + 1) +' in a year.')
  ```

  выдает в PyCharm Community 2017.3 сообщение

  ```
  SyntaxError: Non-ASCII character '\xd0' in file /Users/aleksey/PycharmProjects/setests/pythonTrain.py on line 1, but no encoding declared; see http://python.org/dev/peps/pep-0263/ for details
  
  Process finished with exit code 1
  ```

  Решение - поставить перед каждым значком комментария не мнее двух пробелов, о чем подсказывает PyCharm.  И поставить после оператора `+` пробел

## Глава 2

58-90/573 страницы.

**Сделано хоршо**

- 

**Сделать лучше**

- Не халтурить и в описании про инструкции `if`, `elif` давать полноценную программу, а не куски кода с вступлениями "Предположим, что у вас имеется код", проверяющий совпадение с именем "Alice". (Здесь предполагается, что переменной *name* ранее было присвоено некоторое значение)".

**Итого**

Брать и читать скучно. Видимо следует сразу переходить к кускам кода, дополнять их недостающими фрагментами, заполняя пробел Свейгерта "предположим, что у вас есть код", запкускать исполнение кода в Pycharm, расставлять комментарии на каждом предложении.

**Вопросы**

- что такое инструкции управления? Они же инструкции передачи управления, инструкции перехода, условные инструкции
- что такое поток управления? Он же поток выполнения
- что такое булевы значения и как их оформлять?
- что за связь существует между операторами сравнения и булевыми значениями?
- какие операторы работают с какими данными?
- какие есть три булевых оператора?
- какие выражения булевых операторов в каких комбинация принимают результаты истинности?
- как сочетаются операторы сравнения с булевыми операторами?
- какой определен порядок выполнения булевых операторов?
- из каких элементов состоит инструкция потока управления?
- какие выражения могут рассматриваться как условия инструкции потока управления?
- какие существуют правила группировки строк кода в блоки?

**Код для тренировки**

1. 

**Задачи с которыми столкнулся**

1. Какой комбинацией клавиш в PyCharm запустить код с текущей вкладки? `Ctrl + Shift + F10`

2. Сообщение о синтаксической офишке при выполнении фрагмента кода с пояснением PyCharm "Colon expected"

   ```python
     File "/Users/aleksey/PycharmProjects/setests/2.1 - nameAndAccess.py", line 9
       if password == 'swordfish'
                                ^
   SyntaxError: invalid syntax
   
   Process finished with exit code 1
   ```

   Решение:  для инструкции `if` необходимо использовать не только ключевого слова `if` и условие, но и двоеточие.

3. Сообщение от модуля traceback с выводом трассировочной информации о ходе выполнения программы 

   ```python
   Введите ваше имя
   Aleksey
   Traceback (most recent call last):
     File "/Users/aleksey/PycharmProjects/setests/2.1 - nameAndAccess.py", line 4, in <module>
       name = input()
     File "<string>", line 1, in <module>
   NameError: name 'Aleksey' is not defined
   
   Process finished with exit code 1
   ```

   Решение: в `PyCharm > Preferences > Project > Project Interpreter > Show All` сменить интерпретатор по-умолчанию с Python 2 на Python 3.6.

4. Непонимание, как перенести проект PyCharm в папку из которой можно удобно push-ить код в Githab. Решение: вызвать на названии проекта контекстное меню, затем Refactor > Move

5. ...

30.09.2018. Перейти на [Главную страницу](./)