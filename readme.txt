0) Подготовка окружения
Установить Souffle — это язык логического программирования с открытым исходным кодом, созданный под влиянием Datalog. 

Поставить mcpp
sudo apt install mcpp

Скачать и установить souffle
wget https://github.com/souffle-lang/souffle/archive/refs/tags/2.1.tar.gz
cmake -B build -S .
cmake --build build --target install

1) Разобрать пример
В файле example.dl программа для souffle, реализующая простейший pointer analysis. В папке example_db находятся начальные факты. Запустить программу командой
souffle -F ./example_db/ -D ./out/ ./example.dl
В папке out будут созданные программой факты. Понять как они получились, соотнести с правилами.

2) Задания
2.1) В папке task1_db находятся факты полученные из java-проекта task1. В файле DirectSuperclass.facts отношение наследования между двумя классами. В файле DirectSuperinterface.facts отношение наследования между классом/интерфейсом и родительским интерфейсом.
Написать правило выводящую информацию о наследовании с учётом многоуровневого наследования.
Пример:  Есть связи наследования C -> B, B -> A. Надо также вывести связь C -> A

Сохранить результат в файл SubClass.csv
2.2) Sink Reachability
Дано отношение вызовов методов в файле MethodInvocation.facts.
В файле с фактами sinkMethod.facts задать метод-синк com.company.utils.pvf
Реализовать правило SinkReachable(caller, sink, N).  Которое показывает, что метод sink достижим из метода caller за N вызовов.
2.3) Добавить вызов методов в pointer analysis.