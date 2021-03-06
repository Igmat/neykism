> **DRAFT DISCLAIMER:** это всего лишь черновое описание системы, которую мы хотим получить в результате. По итогу проведения работ и исследований в этой теме, содержимое этого документа можете претерпеть кардинальные изменения.

## Составляющие части системы
1. Формальный язык программирования
2. Runtime окружение (описывается языком из предыдущего пункта)
    1. Законы
    2. Договора
3. События-программы - это описание свершившегося события на формальном языке (кто, что, как, кому, когда, где сделал)
4. Хост-приложение для запуска событий-программ в заданом Runtime (законы в него включены по умолчанию, договора добавляются по необходимости)
5. Набор тестов, где тест это:  
    1. Событие-программа
    2. Дополнительные входные условия (например, Договора)
    3. Ожидаемый результат

    Тест считается пройденным, если запуск события-программы с заданными дополнительными входными условиями в хост-приложении приводит к ожидаемому результату.
6. Набор инструментов статического анализа, который включает, но не ограничивается слеудющим:
    1. Поиск всех законов, которые регламентируют то или иное действие
    2. Поиск всех законов, которые регламентируют права и обязанности того или иного субъекта (должностное лицо, гражданин, гос. учреждение и т.д.)
    3. Поиск законов противоречащих друг другу
    4. Построение графа зависимостей между законами
    5. Построение цепочек событий вызванных тем или иным действием
    6. Построение графов подчинения в гос. структурах

### База формального языка
> TODO: этот раздел ещё не закончен

1. Субъект
2. Объект
3. Право
4. Действие - это функция принимающая на вход 1 или более субъектов и опционально неограниченное количество объектов
    > **Пример:** действие "Продажа".  
    Принимает на вход _субъект_ "Покупатель", _субъект_ "Продавец", _объект_ "Товар", _объект_ "Денежная сумма"  
    Отчуждает _право_ собственности на _объект_ "Товар" у _субъекта_ "Продавец"  в пользу _субъекта_ "Покупатель"  
    Отчуждает _право_ собственности на _объект_ "Денежная сумма" у _субъекта_ "Покупатель" в пользу _субъекта_ "Продавец"  
5. Обязательство - это свойство субъекта, означающие, что он должен выполнить определённое _действие_ с определёнными входными параметрами. Может так же обладать дополнительной мета-информацией как-то срок, место и другое.
6. Договор - это программа, которая добавляет заданным _субъектам_ (подписавшим его) определённые _обязательства_. Она так же может добавлять дополнительные _обязательства_ подписантам, если те выполнили какие-то _действия_.
7. Закон - то же самое, что и договор, только его _субъектами_ выступают все граждане или какое-то их подмножество, а их явное согласие не требуется.