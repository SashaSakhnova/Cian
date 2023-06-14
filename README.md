# `Cian`🏗️🏢
Всем привет! 
Наша команда состоит из трех участников: Калина Вероника Юрьевна БЭК215 (капитан), Сахнова Александра Вячеславовна БЭК215, Кашурина Анастасия Денисовна БЭК219.

Целью нашего проекта является прогнозирование цены за один квадратный метр.

 `Файл` | `Описание` | 
| :-------| :-----------|
| [**CIAN для выгрузки**](https://github.com/SashaSakhnova/Cian/blob/main/CIAN%20для%20выгрузки.ipynb) | В данном блокноте находятся коды, которые были написан для выгрузки объявлений с сайта и выгрузки характеристик по квартирам.|
| [**CIAN_FINAL**](https://github.com/SashaSakhnova/Cian/blob/main/cian_final.txt) | В данном файле содержатся выгруженные ссылки для каждого объявления.|
| [**dataframe**](https://github.com/SashaSakhnova/Cian/blob/main/dataframe.csv) |  В данном файле csv содержатся выгруженные списки по каждому обьявлению.|
| [**CIAN parcer**](https://github.com/SashaSakhnova/Cian/blob/main/CIAN%20parcer.ipynb) | В данном блокноте мы поработали с выгруженными характеристиками и подготовили наш датафрейм для дальнейшей работы и обработки данных.|
| [**df_result**](https://github.com/SashaSakhnova/Cian/blob/main/df_result.csv) | В данном csv файле содержиится промежуточный DataFrame до создания новых признаков.
| [**Визуализации**](https://github.com/SashaSakhnova/Cian/blob/erunka-patch-1/Визуализации.ipynb) | В данном блокноте мы построили графики различного типа, чтобы посмотреть на зависимость интересующих нас признаков.|
| [**Приложение**](https://github.com/SashaSakhnova/Cian/blob/main/Приложение.ipynb) | Для дальнейшего тестирования гипотез и работы с машинным обучением нам нужно было распределить метро по округам. Распределили станции метро, которые мы встречали в наших объявлениях по округам, вручную.|
| [**Гипотезы+взаимосвязи**](https://github.com/SashaSakhnova/Cian/blob/main/Гипотезы%2Bвзаимосвязи.ipynb) | В данном блокноте мы моздали новые признаки для построения гипотез, рассмотрели гипотезы и посмотрели на, наш взгляд, важные взаимосвязи.|
| [**ML_cian**](https://github.com/SashaSakhnova/Cian/blob/main/ML_cian.ipynb) | В данном блокноте мы протестировали различные модели, чтобы выявить наименьшую ошибку и понять, какая из моделей более оптимальная.|

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
- `ppm(rub)` - Цена за 1 кв метр
- `Okrug` - Округ, в котором расположено близжайшее к квартире метро

## `Сбор данных`
Для проекта нами были выбраны квартиры на сайте ЦИАН. Параметры по которым мы выбирали квартиры: новостройка, первичка, от 1 и более комнат. Таким образом, мы получили 1508 объявлений, после удаления наблюдений, в которых отсутствовали станции метро, осталось 1484 объявления, с которыми мы продолжили работу.

## `Визуализация`
Для визуализации мы использовали диаграмму рассеяния, гистограмму и ящик с усами. С помощью визуализации мы путем изучения графиков распределения признаков постарались выявить наличие илли отсутствие корреляции между ними, а также попытались сделать предположение о влиянии рассматриваемых признаков на конечную цену.

На основании полученных визуализации мы перейдем к тестированию гипотез.

## `Гипотезы`
Сначала мы создали два новых признака "Цена за квадратный метра" (этот признак понадобиться для ML) и "Округ" (распределние метро по округам можно найти в файле "Приложение").
Далее мы перешли к тестированию гипотез:
1. В центральном административном округе квартиры дороже, чем в остальных округах.
2. В диапозоне [ 1; 30] этажах квартиры стоят дороже, чем на остальных.
3. Влияет ли этажность дома на количество лифтов в нем
4. Влияет ли год постройки дома на время до близжайшего метро.
После этого мы решили рассмотреть гипотезы о значимости следующих коэффициенов линейной регрессии:
5. Коэффициент при регрессоре, определяющем год постройки, незначим в формировании стоимости квартиры.
6. Коэффициент при регрессоре общего метража квартиры незначим в формировании стоимости квартиры.

Гипотезы мы проверяли с помощью t-теста, коэффициента корреляции Пирсона и построения множественной модели линейноой регресии.

## `Машинное обучение`
- Сперва мы перекодируем признак "Okrug" через onehotkey для использования качественных признаков. 
- Далее рассмотрим две одинаковые модели линейной регрессии, где в одной будем таргетировать цену на квардратный метр, а в другой  нашу изначальную цену за всю квартиру.
- Теперь посмотрим на штрафование и оценивание модели и интерпритацию полученных оценок. Для этого мы возьмем MSE как скоринг и метод оценки. Модели будем сравнивать между собой по его величине, учитывая, специфику нормализации.
- И финально через очень короткий catboost посмотрим, какая из моделей более эффективна.
Замечения и выводы по ML:
1. При классификацмм возникают группы, в которых менее одного элемента.
2. Вероятнее всего, предсказать цену можно, но её функция кусочно-заданная (предположение о кластерах), при этом чисто функционально выделить их нельзя.
3. Наиболее эффективной оказалась модель "n-соседей" с min-max скэлером.

