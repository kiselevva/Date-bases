**Предметная область**
База данных по студентам имеет следующие таблицы:
 Группы: идентификатор группы, краткое название специальности (ПС, ВМ, ИВТ,
БИ).
 Студенты: идентификатор студента, фамилия, номер телефона, идентификатор
группы.
 Предметы: идентификатор предмета, название.
 Преподаватели: идентификатор преподавателя, фамилия, номер телефона.
 Занятия: идентификатор занятия, идентификатор преподавателя, идентификатор
предмета, идентификатор группы, дата.
 Оценки: идентификатор оценки, идентификатор студента, идентификатор
занятия, оценка.

**Требуется**
1. Добавить внешние ключи.
2. Выдать оценки студентов по информатике если они обучаются данному
предмету. Оформить выдачу данных с использованием view.
3. Дать информацию о должниках с указанием фамилии студента и названия
предмета. Должниками считаются студенты, не имеющие оценки по предмету,
который ведется в группе. Оформить в виде процедуры, на входе
идентификатор группы.
4. Дать среднюю оценку студентов по каждому предмету для тех предметов, по
которым занимается не менее 35 студентов.
5. Дать оценки студентов специальности ВМ по всем проводимым предметам с
указанием группы, фамилии, предмета, даты. При отсутствии оценки заполнить
значениями NULL поля оценки.
6. Всем студентам специальности ПС, получившим оценки меньшие 5 по предмету
БД до 12.05, повысить эти оценки на 1 балл.
7. Добавить необходимые индексы.

**Лабораторная работа 5**

**Предметная область**

База данных по комплексу гостиниц имеет следующие таблицы:
• Отель: id отеля, название отеля, количество звезд.
• Категория номера: id категории номер, название (люкс, эконом), минимальная 
площадь по категории.
• Комната отеля: id комнаты, id отеля, id категории номер, номер комнаты в отеле, 
стоимость суток проживания.
• Клиент: id клиента, фио, телефон.
• Бронирование: id брони, id клиента, дата бронирования
• Комната в бронировании: id комнаты в брони, id брони, id номера, дата заезда, 
дата выезда.

**Предписание**
Номер считается занятым на дату Х, если день Х является датой заезда или дата Х
находится между датой заезда и выезда. В дату выезда номер освобождается и 
доступен для заезда.

**Требуется**
1. Добавить внешние ключи.
2. Выдать информацию о клиентах гостиницы “Космос”, проживающих в номерах 
категории “Люкс” на 1 апреля 2019г.
3. Дать список свободных номеров всех гостиниц на 22 апреля.
4. Дать количество проживающих в гостинице “Космос” на 23 марта по каждой 
категории номеров
5. Дать список последних проживавших клиентов по всем комнатам гостиницы 
“Космос”, выехавшим в апреле с указанием даты выезда. 
6. Продлить на 2 дня дату проживания в гостинице “Космос” всем клиентам 
комнат категории “Бизнес”, которые заселились 10 мая.
7. Найти все "пересекающиеся" варианты проживания. Правильное состояние: не 
может быть забронирован один номер на одну дату несколько раз, т.к. нельзя 
заселиться нескольким клиентам в один номер. Записи в таблице
room_in_booking с id_room_in_booking = 5 и 2154 являются примером 
неправильного состояния, которые необходимо найти. Результирующий кортеж 
выборки должен содержать информацию о двух конфликтующих номерах.
8. Создать бронирование в транзакции.
9. Добавить необходимые индексы для всех таблиц.


**Лабораторная работа 6**

**Предметная область**

База данных по лекарствам имеет следующие таблицы:
• Фармакологическая компания: номер компании (идентификатор), название 
компании, год основания. • Дилер компании: номер дилера, номер компании (лекарства которой он 
продает), ФИО дилера, телефон.
• Лекарство: номер лекарства, название, длительность стандартного курса 
лечения в днях.
• Аптека: номер аптеки, название, рейтинг. • Производство лекарств: номер производства, номер компании, номер 
лекарства, стоимость единицы продукции, оценка качества по 10-балльной 
шкале.
• Заказ: номер заказа, номер производства лекарства, номер дилера, номер 
аптеки, дата заказа, количество данного лекарства в заказе.

**Требуется**
1. Добавить внешние ключи.
2. Выдать информацию по всем заказам лекарства “Кордерон” компании “Аргус” с 
указанием названий аптек, дат, объема заказов.
3. Дать список лекарств компании “Фарма”, на которые не были сделаны заказы 
до 25 января.
4. Дать минимальный и максимальный баллы лекарств каждой фирмы, которая 
оформила не менее 120 заказов.
5. Дать списки сделавших заказы аптек по всем дилерам компании “AstraZeneca”. 
Если у дилера нет заказов, в названии аптеки проставить NULL.
6. Уменьшить на 20% стоимость всех лекарств, если она превышает 3000, а 
длительность лечения не более 7 дней.
7. Добавить необходимые индексы
