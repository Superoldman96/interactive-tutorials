Клоужърът е обект на функция, който си спомня стойности в обграждащите го области, дори ако те не са налични в паметта. Нека го разгледаме стъпка по стъпка.

Първо, **вложена функция** е функция, дефинирана вътре в друга функция. Много е важно да се отбележи, че вложените функции могат да имат достъп до променливите на обграждащата ги област. Все пак, поне в Python, те са само за четене. Въпреки това, можете да използвате ключовата дума "nonlocal", за да модифицирате тези променливи изрично.

Например:

    def transmit_to_space(message):
        "Това е обграждащата функция"
        def data_transmitter():
            "Вложената функция"
            print(message)
    
        data_transmitter()
    
    print(transmit_to_space("Тестово съобщение"))

Това работи добре, тъй като функцията 'data_transmitter' може да има достъп до 'message'. За да демонстрираме използването на ключовата дума "nonlocal", разгледайте следното:

    def print_msg(number):
        def printer():
            "Тук използваме ключовата дума nonlocal"
            nonlocal number
            number=3
            print(number)
        printer()
        print(number)
    
    print_msg(9)

Без ключовата дума nonlocal, изходът би бил "3 9", все пак с нейното използване получаваме "3 3", тоест стойността на променливата "number" е променена.

А сега, какво ще кажете да върнем обекта на функцията, вместо да извикваме вложената функция вътре. (Запомнете, че дори функциите са обекти. (Това е Python.))

    def transmit_to_space(message):
        "Това е обграждащата функция"
        def data_transmitter():
            "Вложената функция"
            print(message)
        return data_transmitter

И извикваме функцията по следния начин:


      def transmit_to_space(message):
        "Това е обграждащата функция"
        def data_transmitter():
            "Вложената функция"
            print(message)
        return data_transmitter
        
  	  fun2 = transmit_to_space("Изгори Слънцето!")
  	  fun2()

Въпреки че изпълнението на "transmit_to_space()" беше завършено, съобщението бе запазено. Тази техника, чрез която данните са прикрепени към някакъв код, дори след края на тези други оригинални функции, се нарича клоужъри в Python.

ПРЕДИМСТВО: Клоужърите могат да избегнат използването на глобални променливи и предоставят някаква форма на скриване на данни. (Например, когато има малко методи в един клас, използвайте клоужъри вместо тях).

Също така, декораторите в Python използват клоужъри обширно.

Exercise
--------

Направете вложен цикъл и клоужър в Python, за да създадете функции за получаване на множество функции за умножение чрез клоужъри. Тоест, използвайки клоужъри, можете да създадете функции за създаване на multiply_with_5() или multiply_with_4() функции чрез клоужъри.