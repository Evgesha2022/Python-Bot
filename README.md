# Python-Bot
 In this project, a telegram bot was created for recording and issuing books.
In the init.py the interface of our bot was made
In the folder we keep a our database, exactly database models(models.py) and methods for obtaining and saving the results we need(dbpai.py).</br>
In the dbpai.py the interface of our bot was made
In the models.py the interface of our bot was made
In the telegram.py the interface of our bot was made. It has functions to add a book, delete a book, a list of books, take a book, find a book, return a book, statistics about books.
```python
 markup = types.ReplyKeyboardMarkup(resize_keyboard=True)
    btn1 = types.KeyboardButton('Добавить книгу')
    btn2 = types.KeyboardButton('Удалить книгу')
    btn3 = types.KeyboardButton('Все книги')
    btn4 = types.KeyboardButton('Найти книгу')
    btn5 = types.KeyboardButton('Взять себе')
    btn6 = types.KeyboardButton('Вернуть')
    btn7 = types.KeyboardButton('INFO по книге')
    markup.add(btn1, btn2, btn3, btn4, btn5, btn6, btn7)
    bot.send_message(message.from_user.id, "Добро пожаловать в чат бота-библиотеки! Выберите действие", reply_markup=markup)
```
In the app.py we was creating a link where you cam
