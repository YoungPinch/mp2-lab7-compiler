# Компилятор языка Pascal--

__Цель данной работы__  — разработать программную систему, позволяющую компилировать и выполнять код на языке Pascal--.
## Формулировка задачи
* Объектом работы является исполняемая программа.
* Каждая программа состоит из блока названия, блоков констант и переменных (опционально), тела программы, которое может содержать инструкции для работы с числами, операции вывода и чтения, условные конструкции неограниченной вложенности.
* Для кода программы представлены следующие требования:
  - Начало программы начинается с ключевого слова program и названия программы;
  - Блоки и выражения начинаются с 'begin' и заканчиваются 'end;', заисключением тела программы, которое заканчивается 'end.';
  - Имена переменных и констант регистронезависимы;
  - Имена переменных и констант не могут начинаться с цифры или иметь названия ключевых слов языка Pascal--;
  - Переменная не может быть объявлена одновременного как константа и переменная;
  - Переменные и константы принимают тип integer или real;
  - Начало блока и конец блока имеют одинаковый отступ в 2 пробела относительно родительского блока; 
* Пользователь передаёт название файла, в котором содержится код программы, производится разбор текста с выделением блоков и построением иерархии условных конструкций. На следующем этапе производится лексический и синтаксический анализ корректности программы. Компилятор выполняет анализ иерархического списка для создания объекта исполняемой программы.
## Ключевые моменты этапов работы программы
* Иерархический список представляет собой бинарное дерево, в котором правая ветвь содержит начало вложенного блока, а левая - следующий элемент текущего блока.
* Лексическая проверка текста включает в себя проверку на корректность названий переменных, корректность используемых символов.
* Синтаксическая проверка включает корректность использования лексем в контексте с помощью конечного автомата состояний.
* Компилятор по иерархическому списку строит объект исполняемой программы, содержащий в себе таблицы констант и переменных, дерево выражений.
