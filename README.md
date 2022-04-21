# Компилятор языка Pascal--

__Цель данной работы__  — разработать программную систему, позволяющую "компилировать" и выполнять код на языке Pascal--.
## Формулировка задачи
* Объектом работы является объект исполняемой программы.
* Код программы состоит из блока названия, опциональных блоков констант и переменных, тела программы, которое может содержать инструкции для работы с числами, операции ввода/вывода, условные конструкции неограниченной вложенности.
* Для кода программы представлены следующие требования:
  - В начале указано название программы после ключевого слова program;
  - Ключевые слова 'begin' и 'end' соответственно объявляют начало и конец блока
  - Каждое выражение внутри блока и сам блок (кроме блоков констант и переменных) заканчиваются ';', за исключением тела программы, которое заканчивается '.'.
  - Имена переменных и констант регистронезависимы;
  - Имена переменных и констант не могут начинаться с цифры или иметь названия ключевых слов языка Pascal--;
  - Переменная не может быть объявлена одновременного как константа и переменная;
  - Переменные и константы принимают тип integer или real;
  - Начало блока и конец блока имеют одинаковый отступ в 2 пробела относительно родительского блока; 
* Пользователь вводит название файла, в котором содержится код программы, производится разбор текста с выделением блоков и построением иерархии условных конструкций. На следующем этапе производится лексический и синтаксический анализ корректности программы. Компилятор выполняет анализ иерархического списка для создания объекта исполняемой программы.
## Ключевые моменты этапов работы программы
* Иерархический список, содержащий обработанный текст программы, представляет собой бинарное дерево, в котором правая ветвь содержит начало вложенного блока, а левая - следующий элемент текущего блока.
* Лексическая проверка текста включает в себя проверку на корректность названий переменных, корректность используемых символов.
* Синтаксическая проверка включает корректность использования лексем в контексте с помощью конечного автомата состояний.
* Компилятор по иерархическому списку строит объект исполняемой программы, содержащий в себе таблицы констант и переменных, дерево выражений.
* Арифметические выражения выполняются при помощи постфикса.
