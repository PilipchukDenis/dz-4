

# 1 Задание:
# Реализуйте класс «Автомобиль». Необходимо хранитьв полях класса: название модели, год выпуска, произво-
# дителя, объем двигателя, цвет машины, цену. Реализуйтеметоды класса для ввода данных, вывода данных, реа-
# лизуйте доступ к отдельным полям через методы класса.

#
# class Car:
#     def __init__(self, model_name='', year_release=0, manufacturer="", engine_volume="", color_car="", price=0):
#         self.__model_name = model_name
#         self.__year_release = year_release
#         self.__manufacturer = manufacturer
#         self.__engine_volume = engine_volume
#         self.__color_car = color_car
#         self.__price = price
#
#     def display_info(self):
#         print(f"Название модели: {self.__model_name}")
#         print(f"Год выпуска: {self.__year_release}")
#         print(f"Производитель: {self.__manufacturer}")
#         print(f"Объем двигателя: {self.__engine_volume}")
#         print(f"Цвет автомобиля: {self.__color_car}")
#         print(f"Цена: {self.__price}")
#
#
# car = Car("Lada", 2014, "Русский автороизводитель АвтоВАЗ", "1.6 литра", 'Green', 1_600_000)
# car.display_info()
#



# 2 задание: Реализуйте класс «Книга». Необходимо хранить вполях класса: название книги, год выпуска, издателя,
# жанр, автора, цену. Реализуйте методы класса для вводаданных, вывода данных, реализуйте доступ к отдельным
# полям через методы класса.
#
# import os
# class Book:
#     default_instance_type = "200$"
#     def __init__(self, title_book: str, genre: str, year_release=0):
#         self.__title_book = title_book
#         self.__genre = genre
#         self.__year_release = year_release
#         self.__instance_type = self.default_instance_type
#
#     def data_output(self):
#         print("Название книги:", self.__title_book)
#         print("Год выпуска:", int(self.__year_release))
#         print("Жанр:", self.__genre)
#         print("Цена:", self.__instance_type)
#
#     @property
#     def title_book(self):
#         return self.__title_book
#
#     @title_book.setter
#     def title_book(self, title_book):
#         self.__title_book = self.__validate_title_book(title_book)
#
#     def __validate_title_book(self, title_book):
#
#         if not isinstance(title_book, str):
#             raise TypeError(f"{title_book} должен быть строкой")
#         if not title_book:
#             raise ValueError(f"{title_book} не может быть пустым")
#
#         valid_characters = set(
#             'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZабвгдежзийклмнопрстуфхцчшщъыьэюяАБВГДЕЖЗИЙКЛМНОПРСТУФХЦЧШЩЪЫЬЭЮЯ ')
#         if not all(i in valid_characters for i in title_book):
#             raise ValueError(f"{title_book} должен содержать только символы кириллицы, латиницы или пробелы")
#         return ''.join(title_book.lower().capitalize())
#
#     @staticmethod
#     def from_file(file_path):
#         if not os.path.exists(file_path):
#             with open(file_path, 'w', encoding='utf-8') as file:
#                 file.write("Harry Potter\nФантастика, приключение\n2002")
#
#         with open(file_path, 'r', encoding='utf-8') as file:
#             data = file.read().splitlines()
#             if len(data) != 3:
#                 raise ValueError("Файл должен содержать заголовок, жанр и год выпуска книги")
#
#             title = data[0]
#             genre = data[1]
#             year = int(data[2])
#             return Book(title, genre, year)
#
#     def set_instance_type(self, instance_type):
#         self.__instance_type = instance_type
#
#
# book = Book("Harry Potter", "Фантастика, приключение", 2001)
# book.data_output()
# print("-"*23)
#
# book.title_book = "Джоан Роулинг"
# print(book.title_book)
# print("-"*23)
#
#
#
#
#
#



# 3 задание:
# Реализуйте класс «Стадион». Необходимо хранить вполях класса: название стадиона, дату открытия, страну,
# город, вместимость. Реализуйте методы класса для вводаданных, вывода данных, реализуйте доступ к отдельным
# полям через методы класса.

# class Stadium:
#     def __init__(self, stadium="", opening_date="", country="", city="", capacity=""):
#         self.__name_stadium = stadium
#         self.__opening_date = opening_date
#         self.__country = country
#         self.__city = city
#         self.__capacity = capacity
#
#     def display_info(self):
#         print(f"Название стадиона: {self.__name_stadium}")
#         print(f"Дата открытия: {self.__opening_date}")
#         print(f"Страна: {self.__country}")
#         print(f"Город: {self.__city}")
#         print(f"Вместимость стадиона {self.__capacity}")
#
# stadium = Stadium("Ростов Арена", "Основан 2 декабря 2010 года. Первый тестовый матч на арене прошёл 15 апреля 2018 года'", "Россия", "Ростов-на-Дону", "43 472 зрительских места")
# stadium.display_info()



