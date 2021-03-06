# Методы тест дизайна. Таблицы принятия решений

### «Тестирование программ», Владимир Васильевич Липаев

Москва, Радио и связь, 1986, 65/150:

Глава 3. Тестирование программных модулей. 3.2. Тестирование модулей без исполнения программ. Символическое тестирование

Есть ряд попыток (Маминков А.Г., Цвиркун А.Д., Кульба В.В. "Автоматизация/Проектирование АСУ", - М.: Энергоиздат, 1981; Ibramsha M., Rajaraman V.   "Detection of logical errors in detection table programa", CACM, 1978, Volume 21 Issue 12, Dec. 1978) применить для символического тестирования метод таблиц решений. Таблицы решений представляют собой упорядоченные условия, каждому набору которых ставится в соответствие набор действий и решений (рисунок 3.3) (12). Тем самым формулируется не конкретный алгоритм решения задачи, а ее точная формальная постановка и необходимые условия ее решения.

|  | Правило 1 | Правило 2 | Правило 3 | Правило 4 ||
|-|-|-|-|-|-|
| **Условия** |  |  | | |
| A = 0 | Да | Нет | Да | Нет | Матрица условий |
| B < 0 | Нет| Да | Да | Нет ||
| С >= 1| Да | _ | Да| Да||
| D >= C | Да | _ | Да | Нет ||
|||||||
| **Решения** |  |  |
| W >= 10 | X |  | X |  | Матрица действий |
| V >= 12 | X |  |  | X |  |
| Z != 6 ||X||X||
| Y = 4|||X|X||
| X <= ||X| X|||

Наборы условий компонуются в правила, описываемые матрицей условий. В матрице действий для каждого правила указывается совокупность решений. В общем случае таблица решений при ```n``` условиях является формально полной, если для каждой из всех 2<sup>n</sup> ситуаций имеется решающее правильно. В результате формально полные таблицы решений даже при небольшом числе условий могут оказаться весьма громоздкими. В действительно таблицы редко строятся формально полными. Кроме того, значительное сокращение размера таблиц обеспечивается их фрагментацией путем выделения групп условий и соответствующих им решений.

Большое практическое значение имеет понятие логической полноты таблиц решений. Таблица решений называется логически полной, если всем логически истинным ситуация она ставит в соответствие некоторые действия. Формальная полнота таблиц решений может быть проверена автоматически при одновременном выделении ситуаций, для которых отсутствуют правила. Логическая полнота учитывает семантические связи условий, что затрудняет формальную проверку ее полноты, однако значительно уменьшает размерность.

Из каждой таблицы решений можно получить множество эквивалентных графовых моделей (блок-схем) программ, и наборот...

### «Тестирование программного обеспечения. Фундаментальные концепции менеджмента бизнес-приложений», Сэм Канер, Джек Фолк и Енг Кек Нгуен

Москва, ДиаСофт, 2001. 321-322/538 страницы:

Таблицы и деревья решений

В таблице решений отражается логика программы. Каждый ее элемент - это `Д` (да) или `Н` (нет) либо `И` (истина) или `Л` (ложь). Программа постоянно принимает решения, что ей делать дальше. Эти решения зависят от определенных обстоятельств, а точнее, от значений определенных данных. Эти обстоятельства и принимаемые программой решений и описываются в таблице.

Пример таблицы решений приведен на рисунке 12.4. Система печатает два сводных отчета. В первом перечисляются все отчеты о проблемах, отложенные в текущем месяце (в июле). Во втором отчете перечисленны отложенные проблемы на указанную дату. Формируя эти сводные отчеты, система перебирвает все имеющиеся отчеты о проблемах и по каждому из них принимает решение: включать ли его в документы, и в какие именно.

В первых трех строках таблицы перечислены вопросы, ответы на которые определяют решение программы.

- Отложена ли проблема программистом? (Если да, в поле `Код резолюции` должно стоять 3.)
- Ввел ли тестировщик значение `Да` в поле `Считать отложенным`?
- Была ли резолюция наложения в июле?

| Первый столбец | Второй столбец | Третий столбец |
| - | - | - |
| ЕСЛИ | Код резолюции = 3 | Д Д Д Д Н Н Н Н |
| ЕСЛИ | Считать отложенным = Да | Д Д Н Н Д Д Н Н |
| ЕСЛИ | Резолюция наложения в июле | Д Н Д Н Д Н Д Н |
| ТО | Включить в отчет за июль | Д Н Д Н Д Н Н Н |
| ТО | Включить в общий отчет | Д Д Д Д Д Д Н Н |

Две нижние строки таблицы показывают, какое решение принимается в каждом из случаев. "В каждом из случаев" означает при каждой возможной комбинации ответов на вопросы. Все эти комбинации перечислены в правой части таблицы. Такая информация должна присутствовать в любой таблице решений - в ней всегда должны быть приведены все возможные комбинации условий, определяющих решение программы. Кроме того, в ней должны быть перечислены и все возможные решения.

Любую таблицу решений легко можно превратить в дерево. Многим людям даже легче представить эту информацию в виде дерева. а не в виде таблицы. На рисунке 12.12 показано дерево решений, эквивалентное таблице на рисунке 12.14. Если вам понадобятся дополнительные примеры таблиц и деревьев принятия решений, их приводят к своей книге Гейн и Сарсон (Gane & Sarson, 1979).

### «A Practitioner's Guide to Software Test Design»

Lee Copeland, 2004. 66-78/358 страницы:

Введение

Таблицы решений являются отличным инструментом для сбора определенных видов системных требований и документирования внутреннего дизайна системы. Они могут использоваться для записи сложных бизнес-правил, которые должна реализовывать система. Кроме того, они могут служить руководством для создания тест-кейсов.

Таблицы решений являются важным инструментом в личном наборе инструментов тестировщика. К сожалению, многие аналитики, дизайнеры, программисты и тестировщики не знакомы с этой техникой.

Техника

Таблицы решений представляют собой совокупность бизнес-правил, основанных на наборе Условий. Структура таблицы решений:

|  | **Правило 1** | **Правило 2** | **...** | **Правило p** |
| - | - | - | - | - |
| **Условия** |  |  |  |  |
| Условие-1 |  |  |  |  |
| Условие-2 |  |  |  |  |
| ... |  |  |  |  |
| Условие-m |  |  |  |  |
|  |  |  |  |  |
| **Действия** |  |  |  |  |
| Действие-1 |  |  |  |  |
| Действие-2 |  |  |  |  |
| ... |  |  |  |  |
| Действие-n |  |  |  |  |

Условия от единицы до m представляют различные входные Условия. Действия с единицы по n - это действия, которые должны выполняться в зависимости от различных комбинаций Условий ввода.

Каждое из Правил определяет уникальную комбинацию Условий, которые приводят к выполнению ("запуску") Действий, связанных с этим Правилом. Обратите внимание, что Действия зависят не от порядка, в котором оцениваются Условия, а только от их значений. (Предполагается, что все значения доступны одновременно.) Кроме того, Действия зависят только от заданных Условий, а не от предыдущих Условий ввода или состояния системы.

Возможно, конкретный пример прояснит идею. Автостраховая компания предоставляет скидки водителям, состоящим в браке и / или хорошим студентам. Начнем с Условий. Следующая таблица решений имеет два Условия, каждый из которых принимает значения "Да" или "Нет":

| - | **Правило 1** | **Правило 2** | **Правило 3** | **Правило 4** |
| - | - | - | - | - |
| **Условия** |  |  |  |  |
| Женат? | Да | Да | Нет | Нет |
| Хороший студент? | Да | Нет | Да | Нет |

Обратите внимание, что таблица содержит все комбинации Условий. Учитывая два бинарных условия ("Да" или "Нет"), возможные комбинации "Да-Да", "Да-Нет", "Нет-Да" и "Нет-Нет".

Каждое Правило представляет собой одну из этих комбинаций. В качестве тестировщика мы проверим, что все комбинации Условий определены. Пропуск комбинаций может привести к разработке системы, которая может неправильно обрабатывать определенный набор входных данных.

Теперь о Действиях. Каждое из Правил приводит приводят к выполнению ("запуску") Действий. 
Каждое Правило может специфицировать действие уникальное для этого Правила или Правила могут совместно использовать Действия.

Таблица 5-3: Добавление одного Действия в таблицу решений

| - | Правило 1 | Правило 2 | Правило 3 | Правило 4 |
| - | - | - | - | - |
| **Условия** |  |  |  |  |
| Женат? | Да | Да | Нет | Нет |
| Хороший студент? | Да | Нет | Да | Нет |
| **Действия** |  |  |  |  |
| Скидка ($) | 60 | 25 | 50 | 0 |

Таблицы принятия решений могут специфицировать более одного Действия для каждого Правила. Опять же, эти Правила могут быть уникальными или могут быть общими.

Таблица 5.4: Таблица решений с несколькими действиями

|  | **Правило 1** | **Правило 2** | **Правило 3** | **Правило 4** |
| - | - | - | - | - |
| **Условия** |  |  |  |  |
| Условие-1 | Да | Да | Нет | Нет |
| Условие-2 | Да | Нет | Да | Нет |
| **Действия** |  |  |  |  |
| Действие-1 | Выполнить X | Выполнить Y | Выполнить X | Выполнить Z |
| Действие-2 | Выполнить A | Выполнить B | Выполнить B | Выполнить B |

Еще перевести с 69 по 76 страницы...

### "Разработка требований к программному обеспечению", Карл И. Вигерс

Перевод с английского языка. Москва, Издательско-торговый дом "Русская редакция", 2004 год. 576 страниц. 229-231 страницы:

Часто система программного обеспечения управляется сложной логикой, учитывающей различные комбинации условий, результатом которых является различное поведение системы. Например, если водитель нажимает кнопку ускорения на системе круиз-контроля автомобился и автомобиль в данный момент двигается, то система увеличит скорость автомобиля, в противном случае команда игронируется. Для спецификации требований к программному обеспечению необходимы функциональные требования, в которых будет описано, что должна делать система при всех комбинациях условий. Однако условие легко пропустить, в результате чего пропускается и требование. Эти пробелы трудно заметить, просматривая текстовые спецификации вручную.

Таблицы решений и деревья решений - это два альтернативных приема для представления того, что система должна делать, когда в игру вступают сложные логика и решения (Davis, Alan M. 1993. Software Requirements: Objects, Functions, and States, Englewood Cliffs, NJ: Prentice Hall PTR). В таблице решений (decision table) перечислены различные значения для всех факторов, влияющих на поведение системы, и приведены ожидаемые действия системы в ответ на каждую комбинацию факторов. Факторы могу быть показаны либо как утверждения с различными условиями true и false, либо как вопрсоы с возможными ответами "да" или "нет". Естетственно, вы также можете использовать таблицы решений с факторами, которые имеют более двух возможных значений.

Ловушка. Не нужно создать и таблицу решений, и дерево решений, чтобы показать один и тот же фрагмент информации; вполне достаточно одного из них.

| Условие                                                      | 1     | 2     | 3     | 4     | 5    |
| ------------------------------------------------------------ | ----- | ----- | ----- | ----- | ---- |
| Пользователь авторизован                                     | false | true  | true  | true  | true |
| Химикат есть в наличии                                       | -     | false | true  | true  | true |
| Химикат считается опасным                                    | -     | -     | false | true  | true |
| Сотрудник, разместивший заказ на химикат, прошел соответствующую подготовку | -     | -     | -     | false | true |
|                                                              |       |       |       |       |      |
| **Действие**                                                 |       |       |       |       |      |
| Принять запрос                                               |       |       | х     |       | х    |
| Отклонить запрос                                             | х     | х     |       | х     |      |

В таблице 11-2 показана таблица решений с логикой, управляющей принятием или отклонением запроса нового химиката Chemical Tracking System. На решение влияет четыре фактора:

1. авторизован ли пользователь, создающий запрос;
2. имеется ли химикат в наличии на складе или у поставщика;
3. включен ли химикат в список опасных химикатов, для работы с которыми необходима специальная подготовка;
4. есть ли у пользователя, создающего запрос, соответствующая подготовка для работы с этим типом опасного вещества.

Каждый из этих четыре факторов имеет два возможных условия, true или false. В принипе это увеличивает на 24 и 16 различные комбинации true/false для 16 вероятных отдельных функциональных требований. Однако на практике результатов многих комбинаций является одна и та же реакция системы. Если пользователь не авторизован для запроса химикатов, то система не примет запрос, и таким образом остальные условия несущественны (показаны прочерками в таблице решений). Таблица показывает, что результат различных логических комбинаций - лишь пять отдельных функциональных требований.

На рисунке 11-7 показано дерево решений, представляющее ту же логику. Пять прямоугольник обозначают пять возможных результатов принятия или отклонения запроса на химикат. Таблицы решений и деревья решений - это хорошие способы документации требований (или бизнес-правил), позволяющие не пропустить ни одну комбинацию условий. Даже сложная таблица или дерево решений более просты для чтения, чем повторяющие требования в текстовом виде.

### «Основы инженерии качества программных систем», Филипп Андон, Галина Коваль, Татьяна Коротун, Екатерина Лаврищева, В. Суслов

Академпериодика, 2007. 317/679 страница:

Методы, основанные на спецификации (или методы функционального тестирования)

... Метод, использующий таблицы решений для проектирования тестов, был предложен Дж.Гуденафом и С.Герхартом [22]. Каждая колонка такой таблицы представляет комбинацию условий, которые могут существенно повлиять на выполнение программы. Эти условия идентифицируются на основе анализа спецификаций. Затем определяется множество их возможных значений, и устанавливаются ограничения относительно их совместимости. Таким образом, сокращается количество тестовых предикатов (например, ограничение может говорить о том, что, если условие 1 выполняется, то ни условие 2, ни условие 3 не могут выполняться).

### «Сертифицированный тестировщик Программа обучения Базового уровня», ISTQB

Версия 2011 (от 13 апреля 2011 года), **International Software Testing Qualifications Board**, Андрей Конушин (председатель), Александр Александров, Алексей Александров, Татьяна Смехнова, Елена Абрамова. 56/101 страница:

4.3.3 Тестирование таблицы решений

Таблицы решений – хороший метод для сбора системных требований, содержащих логические условия и документирования внутреннего дизайна системы. Они могут использоваться для записи сложных бизнес-правил, которые должна реализовывать система. Анализируются спецификации и определяются условия и действия системы. Входные условия и действия чаще всего формулируются таким образом, чтобы они могли принимать логические значения «истина» или «ложь».

Таблица решений содержит триггерные условия, обычно комбинации значений «истина» и «ложь» для всех входных условий, и результирующие действия для каждой комбинации условий. Каждый столбец таблицы соотносится с бизнес- правилом, определяющим уникальную комбинацию условий и результат выполнения действий, связанных с этим правилом. Стандартом покрытия для тестирования таблицы решений обычно является наличие хотя бы одного теста для каждой колонки, что обычно включает в себя покрытие всех комбинаций триггерных условий.

Сильной стороной тестирования таблицы решений является то, что она создает комбинации условий, которые могли бы быть не проверены в ходе тестирования иным способом. Этот метод может быть применен ко всем ситуациям, в которых действие программного продукта зависит от нескольких логических альтернатив.

### ISTQB Sample Paper

This document contains sample questions collected and collated from various exam sites, user forums, blogs and recent sample questions provided by examinees. For more sample question visit www.istqb.guru. 7/97 страниц:

Question 21: Given the following decision table: Which of the following test cases and expected results is VALID?

| | **Rule 1** | **Rule 2** | **Rule 3** | **Rule 4** |
| - | - | - | - | - |
| **Conditions** | | | | |
| Age | < 21 yrs | 21-29 yrs | 30-50 yrs | > 50 yrs |
| Insurance Class | A | A or B | B, C or D | C or D |
| **Actions** | | | | |
| Premium | £100 | £90 | £70 | £70 |
| Excess | £2,500 | £2,500 | £500 | £1000 |

A. 23 year old in insurance class A Premium is 0 and excess is ,500. 

B. 51 year old in insurance class C Premium is 0 and excess is 00.

C. 31 year old in insurance class B Premium is 0 and excess is ,500. 

D. 43 year old in insurance class C Premium is 0 and excess is ,000.

### «Сертифицированный тестировщик Программа обучения Продвинутого уровня»

Версия 2012 от 30 марта 2017 года, International Software Testing Qualifications Board. Рабочая группа Продвинутого уровня Rex Black, Judy McKay, Graham Bath, Debra Friedenberg, Bernard Homès, Kenji Onishi, Mike Smith, Geoff Thompson, Tsuyoshi Yumoto, Маргарита Трофимова, Александр Александров, Андрей Конушин, Елена Костина, Александр Мешков, Александра Титова. 56/101 страница:

Таблицы решений – хороший метод для сбора системных требований, содержащих логические условия и документирования внутреннего дизайна системы. Они могут использоваться для записи сложных бизнес-правил, которые должна реализовывать система. Анализируются спецификации и определяются условия и действия системы. Входные условия и действия чаще всего формулируются таким образом, чтобы они могли принимать логические значения «истина» или «ложь».

Таблица решений содержит триггерные условия, обычно комбинации значений «истина» и «ложь» для всех входных условий, и результирующие действия для каждой комбинации условий. Каждый столбец таблицы соотносится с бизнес- правилом, определяющим уникальную комбинацию условий и результат выполнения действий, связанных с этим правилом. Стандартом покрытия для тестирования таблицы решений обычно является наличие хотя бы одного теста для каждой колонки, что обычно включает в себя покрытие всех комбинаций триггерных условий.

Сильной стороной тестирования таблицы решений является то, что она создает комбинации условий, которые могли бы быть не проверены в ходе тестирования иным способом. Этот метод может быть применен ко всем ситуациям, в которых действие программного продукта зависит от нескольких логических альтернатив.

### «Тестирование программного обеспечения. Базовый курс», Святослав Куликов

Версия книги 1.2.1 от 02.08.2017, EPAM Systems. 94/297 страница:

... Тестирование на основе (моделей) поведения приложения (application behav-ior/model-based testing): 

- Тестирование по таблице принятия решений (decision table test-ing) — техника тестирования (по методу чёрного ящика), в которой тест-кейсы разрабатываются на основе так называемой таблицы принятия решений, в которой отражены входные данные (и их комбинации) и воздействия на приложение, а также соответствующие им выходные данные и реакции приложения.

2018.05.06. Перейти на [Главную страницу](./)