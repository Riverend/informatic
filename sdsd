import random

predmet = ['Информатика','Математика','Предмет','Плохой Предмет']
familyName = ['Булышев Константин', 'Вася таракан', 'Андрей нетаракан', 'Неизвестный чел-торт']

#Список в котором хранятся данные
spisok = []

#Обьекты в котором будут хранится данные
for i in range(len(familyName)):
    date = {
       'name': familyName[i],
       'oooo': [],
       'price': '',
       'average': 0
    }
#Создается массив с оценками предметов студента
    for j in range(len(predmet)):
        numb = random.randint(3, 5)
        date['oooo'].append(
           {
              'name': predmet[j],
              'ball': numb
           }
        )
    spisok.append(date)

#Поиск и обозначение стипендии
for i in spisok:
    minimal = i['oooo'][0]['ball']
    for j in i['oooo']:
        if (j['ball'] < minimal):
            minimal = j['ball']

    if (minimal == 3):
        i['price'] = 'Нет стипухи'
    elif(minimal == 4):
        i['price'] = 'Обычная стипендия'
    elif(minimal == 5):
        i['price'] = 'Повышенная стипендия'

#Средний балл оценок студента
def averageCount(array):
    count = 0
    for i in array:
        count += i['ball']
    return round(count/len(array), 2)

#Сохранение в массиве списка у каждого студента
for i in spisok:
    i['average'] = averageCount(i['oooo'])

#print(spisok)

#Средний балл предметов студентов
def averageGroup():
    array = []
    for i in range(len(predmet)):
        areg = {
           'name': predmet[i],
           'avere': 0
        }
        for j in spisok:
            areg['avere'] += j['oooo'][i]['ball']
        num = areg['avere'] / len(familyName)
        areg['avere'] = round(num, 2)
        array.append(areg)
    return array

#print(averageGroup())

#Сохранение отображения вывода в красивой табличке
def printDate():
    array = []
    for i in range(1):
#Выравнивает строку в таблице(добавляет пробелы)
        emptyLine = len(familyName[0])
        arr = [' '*emptyLine]
        for j in range(len(predmet)):
            arr.append(predmet[j])
        array.append(arr)

    for i in spisok:
#Выравнивает строку в таблице(добавляет пробелы)
        emptyLine = len(familyName[0]) - len(i['name'])
        arr = [i['name'] + ' '*emptyLine]
        for j in i['oooo']:
            emptyLineBall = len(j['name']) - len(str(j['ball']))
            arr.append(str(j['ball']) + ' '*emptyLineBall)
        arr.append(i['average'])
        arr.append(i['price'])
        array.append(arr)

    for i in range(1):
        name = 'Средний балл пред.'
        emptyLine = len(familyName[0]) - len(name)
        arr = [name + ' '*emptyLine]

        for j in averageGroup():
            emptyLineBall = len(j['name']) - len(str(j['avere']))
            arr.append(str(j['avere']) + ' '*emptyLineBall)
        array.append(arr)
    return array

#Отображение инфы
for row in printDate():
    for elem in row:
        print(elem, end='   ')
    print()
