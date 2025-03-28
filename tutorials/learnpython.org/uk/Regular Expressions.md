# Regular Expressions

Регулярні вирази (іноді скорочуються до regexp, regex або re) — це інструмент для пошуку шаблонів у тексті. У Python ми використовуємо модуль re. Застосування регулярних виразів дуже широке, але вони є досить складними, тому, коли розглядаєте можливість використання regex для певного завдання, подумайте про альтернативи і звертайтеся до регулярних виразів як до останньої інстанції.

Приклад регулярного виразу: `r"^(From|To|Cc).*?python-list@python.org"` Тепер пояснення: каретка `^` відповідає тексту на початку рядка. Наступна група, частина з `(From|To|Cc)` означає, що рядок має починатися з одного з цих слів, які розділені оператором `|`. Це називається оператором АБО, і регулярний вираз буде відповідати, якщо рядок починається з будь-якого з цих слів у групі. Конструкція `.*?` означає негрібний збіг будь-якої кількості символів, окрім символу нового рядка `\n`. Негрібний означає, що буде співпадати якомога менша кількість повторень. Символ `.` означає будь-який не-знак нового рядка, `*` означає повторення 0 або більше разів, а `?` робить його негрібним.

Отже, наступні рядки будуть відповідати цьому регулярному виразу:
`From: python-list@python.org`
`To: !asp]<,.      python-list@python.org`

Повну довідку по синтаксису re ви можете знайти у [документації Python](http://docs.python.org/library/re.html#regular-expression-syntax "RE syntax").

Як приклад "правильного" регулярного виразу для співпадання з адресою електронної пошти (як у вправі), дивіться [тут](http://www.ex-parrot.com/pdw/Mail-RFC822-Address.html).

Exercise--------