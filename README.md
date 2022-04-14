# Компилятор языка Pascal--

__Цель данной работы__  — разработать программную систему, позволяющую компилировать и выполнять код на языке Pascal--.
## Формлировка задачи
* Объектом работы является исполняемая программа.
* Каждая программа состоит из блока названия, блока констант и переменных (опционально), тела программы, которое может содержать инструкции для работы с числами, операции вывода и чтения, условные конструкции неограниченной вложенности.
* Для кода программы представлены следующие требования:
  - Имена переменных и констант регистронезависимы;
  - Переменные и константы принимают тип integer или real;
  - Начало блока и конец блока имеют одинаковый отступ в 2 пробела; 
* Пользователь передаёт название файла, в котором содержится код программы, производится разбор текста с выделением блоков и построением иерархии условных конструкций. На следующем этапе производится лексический и синтаксический анализ корректности программы. Компилятор выполняет анализ иерархического списка для создания объекта исполняемой программы.
## Ключевые моменты этапов работы программы
* Иерархический список представляет собой бинарное дерево, в котором правая ветвь содержит начало вложенного блока, а левая - следующий элемент текущего блока.
* Лексическая проверка текста включает в себя проверку на корректность названий переменных, корректность используемых символов.
* Синтаксическая проверка включает корректность использования лексем в контексте с помощью конечного автомата состояний.
* Компилятор по иерархическому списку строит объект исполняемой программы, содержащий в себе таблицы констант и переменных, дерево выражений.
