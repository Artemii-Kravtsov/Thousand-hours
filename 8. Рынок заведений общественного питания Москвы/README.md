# Рынок заведений общественного питания Москвы
[Открыть проект в NBViewer](https://nbviewer.jupyter.org/github/Artemii-Kravtsov/thousands-of-hours/blob/master/8.%20%D0%A0%D1%8B%D0%BD%D0%BE%D0%BA%20%D0%B7%D0%B0%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B9%20%D0%BE%D0%B1%D1%89%D0%B5%D1%81%D1%82%D0%B2%D0%B5%D0%BD%D0%BD%D0%BE%D0%B3%D0%BE%20%D0%BF%D0%B8%D1%82%D0%B0%D0%BD%D0%B8%D1%8F%20%D0%9C%D0%BE%D1%81%D0%BA%D0%B2%D1%8B/8_restaurants_in_moscow.ipynb)
<br>

## Задачи 
- В каких районах Москвы находятся улицы, где расположено наибольшее количество заведений общественного питания? Что это за улицы? Отличаются ли в чём-то заведения, расположенные на этих улицах?
- Исследовать соотношение разных видов заведений, соотношение сетевых и несетевых заведений. Для каких видов характерно сетевое распространение?
- Что характерно для сетевых заведений: много заведений с небольшим числом посадочных мест в каждом или мало заведений с большим количеством посадочных мест?
- Для каждого вида объекта общественного питания описать среднее количество посадочных мест. Какой вид предоставляет наибольшое количество посадочных мест?
- Какие можно дать рекомендации ресторанному стартапу (заведение, где обслуживанием гостей должны заниматься роботы) после изучения данных?


## Коротко о данных 
15366 записей. Есть уникальный идентификатор заведения, название и адрес заведения (текстовые поля), одна булева переменная, одна дискретная и одна категориальная.


## Библиотеки 
`pandas` `matplotlib` `re` `Open Street Map` `plotly`


## Выводы 
<ol style="padding-left: 0px;"><li><p align="justify">Не рекомендуется в таком объёме брать информацию из открытых источников, приходится тратить немало времени на предобработку.</p></li><li><p align="justify">Внутри третьего транспортного кольца (центр города) и за МКАДом - самая высокая доля ресторанов в Москве. За МКАД, скорее всего, из-за относительной невостребованности кофеен и сетевых ПБО, а в центре - из-за благоприятных условий для ресторанов.</p></li><li><p align="justify">Сетевые заведения чаще встречаются на окраинах, нежели в центре - на окраинах их доля выше примерно на 5-10%.</p></li><li><p align="justify">В популярных и непопулярных районах, на популярных и непопулярных улицах распределение посадочных мест идентично.</p></li><li><p align="justify">К сетевому распространению склонны, в первую очередь, предприятия быстро обслуживания и, во вторую, кафе и рестораны. Несетевые рестораны наиболее активно располагаются в центре города. Самые популярные улицы для них: 'Пресненская набережная', 'проспект Мира' и 'Ленинградский проспект'.</p></li><li><p align="justify">В заведениях нашего формата по медиане 40 посадочных мест.</p></li><li><p align="justify">По мере роста сетей количество мест в ресторанах увеличивается примерно до 90, после чего сети продолжают расти только 'в ширину'</p></li><li><p align="justify">Вопросы, поставленные в этом проекте перед аналитиком данных, лучше адресовать аналитику бизнес-идей.</p></li></ol>
