# Python-Bot
 In this project, a telegram bot was created for recording and issuing books.</br>
In the folder 'database' we keep a our database, exactly database models('models.py') and methods for obtaining and saving the results we need('dbpai.py').</br>
For example, method for add book in our database ( 'dbpai.py' ):
```python
def add(self, title, author, published):
        # Создание новой книги и добавление ее в базу данных
        book = Book(title=title, author=author, published=published, date_added=datetime.datetime.now(),
                    date_deleted=datetime.datetime.max)
        self.session.add(book)
        try:
            self.session.commit()
            return book.book_id
        except:
            self.session.rollback()
            return False
```
In the init.py  we access files from the folder through the `from something import *` command, and we consider this import format to be the most convenient for users of our module.
```python
from database.dbapi import *
from database.models import *
```
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
