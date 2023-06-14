# `Cian`🏗️🏢
Всем привет! 
Наша команда состоит из трех участников: Калина Вероника Юрьевна БЭК215 (капитан), Сахнова Александра Вячеславовна БЭК215, Кашурина Анастасия Денисовна БЭК219.

 `Файл` | `Описание` | 
| :-------| :-----------|
| [**CIAN для выгрузки**](https://github.com/SashaSakhnova/Cian/blob/main/CIAN%20для%20выгрузки.ipynb) | В данном блокноте находятся коды, которые был написан для выгрузки объявлений с сайта и выгрузки характеристик по квартирам.|
| [**CIAN_FINAL**](https://github.com/SashaSakhnova/Cian/blob/main/cian_final.txt) | В данном файле содержатся выгруженные ссылки для каждого объявления.|
| [**dataframe**](https://github.com/SashaSakhnova/Cian/blob/main/dataframe.csv) |  В данном файле csv содержатся выгруженные списки по каждому обьявлению.|
| [**CIAN parcer**](https://github.com/SashaSakhnova/Cian/blob/main/CIAN%20parcer.ipynb) | В данном блокноте мы поработали с выгруженными характеристиками и подготовили наш датафрейм для дальнейшей работы и обработки данных.|
| [**df_result**](https://github.com/SashaSakhnova/Cian/blob/main/df_result.csv) | В данном csv файле содержиится промежуточный DataFrame до создания новых признаков.

## `Наименование признаков`
- `ID` - Номер объявления
- `Number of rooms` - Количество комнат в квартире
- `Price (rub)` - Ценя квартиры
- `Metro` - Близжайшее станция метро к квартире
- `Time (min)` - Минимальное время от дома до метро
- `Total area(m^2)` - Общая площадь квартиры в метрах квадратных
- `Year of completion` - Наличие отделки
- `Living area(m^2)` - Жилая площадь в метрах квадратных
- `Kitchen area(m^2)` - Площадь кухни в метрах квадратных
- `Ceiling height(m)` - Высота потолков в метрах
- `Type of house` - Тип дома 
- `WC` - Количество туалетов
- `Apartment floor` - Этаж, на котором находится квартира
- `Total floors` - Всего этажей в доме
- `Readiness` - Год сдачи дома
- `Num of elevators` - Количество лифтов
- `Type of elevators` - Тип лифта

## ` Сбор данных`
Для проекта нами были выбраны квартиры на сайте ЦИАН. Параметры по которым мы выбирали квартиры: новостройка, первичка, от 1 и более комнат. Таким образом, мы получили 1508 объявлений, после удаления объявленией, в которых были неизвестны станции метро, осталось 1484 объявления, с которыми мы продолжили работу.

Так как мы смотрим только новостройки, мы предполагаем, что они в основном таргетируются на "молодые семьи" или людей, которые заинтересованы в большей степени в удобстве расположения относительно объектов социальной инфраструктуры и метро. Прогнозы рынка недвижимости на данный момент соответствуют предположению о том, что квартиры в новостройках не подходят для инвестиционной покупки.

Наши гипотезы на данный момент выглядят так:

1. Если исключить фактор метража (перейти к прогнозированию стоимости метра жилой площади, что не очень просто) дальность от метро будет ключевым фактором, влияющим на стоимость. Эту гипотезу очень хочется проверить, но нет гарантий, что хватит инструментария и идей

2. Базовой информации о доме (расположение + вид застройки + высота потолков + метраж, в целом того, что застройщик сможет гарантировать ещё до завершения конструирования) достаточно, чтобы с невысокой погрешностью (+-лям окда) предсказать стоимость квартиры.

