## Основные задачи

Основная задача контент-менеджера - это поиск, сохранение, обработка и перенос информации между источниками. Эту работу можно производить вручную и автоматизированно. К автоматическим методам относятся:

◾️Парсинг;

◾️Перенос базы;

◾️Генерация отдельных элементов (ЧПУ, характеристик, названия, описания и т.д.).

К сожалению, полностью автоматизировать эти процессы практически невозможно в связи с тем, что каталоги и сайты наполняются людьми вручную, годами и в разных стилях, так что настроить соответствие одних элементов другим достаточно сложно. Так что, несмотря на все технологии, в этой области доминирует ручной труд.

Однако, и ручной труд можно автоматизировать, используя:
◾️Парсеры;

◾️Надстройки для CRM и 1С;

◾️Автокликеры;

◾️Базы данных;

◾️Excel;

◾️Программы пакетной обработки файлов и текстовой информации.

Используемый инструмент зависит от предоставленных доступов и поставленной задачи.

### Clickermann 

В этой папке собраны видеозаписи работы автокликера Clickermann. Он помогает полностью или почти полностью автоматизировать многие рутинные процессы самого переноса информации из уже подготовленной базы. Программа представляет собой набор готовых шаблонов и команд, позволяет доволно неплохо составлять циклы и настраивать действия в зависимости от полученного результата (цвета на экране, вычисления и т.д.).

В моей практике он выполнял задачи:

◾️Переноса информации из Excel и Google Sheets для создания новых карточек товаров, организаций, рецептур - чего угодно;

◾️Поиска и редактирования уже добавленной информации;

◾️Установления соответствия товара в списке поставщика - товару в системе (также на основе либо заранее составленного листа соответствия, либо на основании информации, полученной от поставщика).

### Сравнение через SQL

Также в папке представлен скриншот - пример обработки и сравнения данных по уже имеющимся в системе товарам. Такие задачи тоже попадаются часто. Например, поставщик блокирует отгрузку по причине того, что неправильно были сделаны соотнесения. Нужно сделать сверку и исправить ошибки. Я просмотрела данные и увидела, что придется сравнивать около 6000 строк. Вручную и средствами Excel это долго и малоэффективно, так что я использовала SQL.

Я смогла получить из системы 3 таблицы (с названиями моделей, с названиями номенклатур, к ним привязанных, и с названиями номенклатур поставщика). Последовательно их объединив, я получила общую таблицу, в которой проверила, содержит ли название номенклатуры поставщика - название модели.

Почему именно так.

Вообще сравнивать можно разными путями, все зависит от заполненности данных. Эта категория товаров была заполнена не слишком единообразно, поставщики не предоставляли правильных артикулов, так что проще всего оказалось сравнить именноп о наименованиям. В сложных случаях я сперва привожу в порядок наименования товаров в самой системе, а уже потом сравниваю.

Здесь я получила около 1000 строк, которые уже можно отсмотреть вручную, а также ID каждого остатка, так что после окончательной чистки этот список можно удалить при помощи Clickermann.
