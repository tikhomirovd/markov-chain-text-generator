# Простая реализация генератора текстов на основе цепей Маркова

## Примеры использования

### Генерация 20 текстов на основе русских пословиц из викицитатника:
```
mc = markov_chain.MarkovChain()
with open('corpus/proverbs', 'r') as c:
    for line in c.readlines():
        mc.parse_and_add(line.strip())
    for i in range(20):
        print(mc.generate_sentence(140))
```

### Результаты генерации:
```
Не бей по псковскому недороду.
Не всё то и в рот тесен.
Не всё то и в лес не даёт.
Не всё свезёт.
Будет хлеб с локоток.
Без капусты щи — будет и не без хлеба не будет и сам не цветно цветут.
Не раскусив ореха, о том свете помучимся, на веселье, третья на себя нашёл. Едва ушёл, сдачи давали, да и не лезь.
Не всё не в суд свой помнит.
В гостях что в лес смотрит.
Кто в рот не без свечи.
Не по милу хорош.
Без ума не купишь.
В гостях хороша девка, с печи не без хлеба не без хлеба не портит.
Как ни в поле не верит.
Не всё не рубится.
Без хлеба не будешь.
У Бога правда одна.
Что кому не дает.
Не учи сороку и в три года серчала, а под старость умирает — не без покаяния — не в хомут.
Как ни молока.
```

### Генерация длинного текста на основе первых 8 глав романа "Анна Каренина" Л.Н.Толстого:
```
mc = markov_chain.MarkovChain()
text = ''
with open('corpus/tolstoy', 'r') as c:
    for line in c.readlines():
        text += line.strip() + ' '
    mc.parse_and_add(text)
    print(mc.generate_sentence(1500))
```

### Результаты генерации:
```
Левин не мог понять, к тому делу, которым он не мог говорить, но не мог говорить, так же она не мог думать о своем кабинете, 
на себя за отца. Он не мог раскаиваться теперь в том, что он не может быть, и не мог придумать. — сказал он, заметив изменение 
ее принять! — сказал Левин. — сказал Степан Аркадьич, выходя к брату: — сказал Степан Аркадьич был влюблен в которой объяснялось, 
что он с ним на сафьянном диване. Он не мог быть не мог простить себе. И она говорила себе, так же это и потому что он не 
мог раскаиваться теперь разве ты не в том, что Матвей в том, что он не мог удержать легкой насмешливой улыбки при этом слове, 
будто бы лучше скрыть от наклоненного положения и с ним. «ага! Стива! Облонский! Вот что: поедем к тому положению, в том, 
что он с ним. Если и не назначил своего обычною ему лица двух умерших детей, чтоб он не мог думать о том, что он не может 
быть, и он не мог раскаиваться в чаду, два слова, а в том, что он не в виде мест, аренд, концессий и не мог раскаиваться 
в его в доме Облонских. Жена узнала, что он не мог быть о том, что он не мог он не мог придумать. — сказал Степан Аркадьич 
получал и с ним на все в спальне у него на себя духами, вытянул рукава рубашки, привычным бодрым шагом вывернутых ног, так 
как он должен быть не мог жить, не было неделенное, и не мог раскаиваться теперь в доме Щербацких он не было так же мне? 
Я не оттого, чтоб играть с развратным отцом, — сказал он, вспоминая сон. — Ну, хорошо, я не могу сказать?.. Одно: прости, 
прости...
```