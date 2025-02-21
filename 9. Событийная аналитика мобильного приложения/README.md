# Событийная аналитика мобильного приложения
[Открыть проект в NBViewer](https://nbviewer.jupyter.org/github/Artemii-Kravtsov/thousands-of-hours/blob/master/9.%20%D0%A1%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9%D0%BD%D0%B0%D1%8F%20%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D1%82%D0%B8%D0%BA%D0%B0%20%D0%BC%D0%BE%D0%B1%D0%B8%D0%BB%D1%8C%D0%BD%D0%BE%D0%B3%D0%BE%20%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F/9_analysing_events_logs.ipynb)
<br>

## Задачи 
- Посчитать долю пользователей, которые хоть раз совершали действия. Предположить, в каком порядке происходят события и построить воронку. 
- На каком шаге теряется больше всего пользователей? Какая доля пользователей доходит от первого события до оплаты?
- Есть ли характерные черты в пользовательском поведении покупающих и непокупающих пользователей?  
- Проверить, соблюдены ли все условия для проведения корректного A/B-теста.
- Протестировать различие в конверсии из каждого экрана в каждый между контрольной и тестовой группами.


## Коротко о данных 
240000 записей в логах за 14 дней наблюдений. Одна категориальная переменная, одна временная, уникальный идентификатор пользователя и идентификтор группы. Аномалии: неполные данные за семь дней; серии из действий, выполненных одним пользователем меньше чем за секунду, а иногда - серии из одного повторяющегося действия. 


## Библиотеки 
`pandas` `matplotlib` `seaborn` `scipy.stats` `plotly` `statsmodels`


## Выводы
<ol style="padding-left: 0px;"><li><p align="justify">Есть множество таких записей, когда показ экранов "Корзина" и "Оплачено" происходит в одну и ту же секунду, притом эти события составляют больше 1/3 от всех показов корзины и больше 1/2 от всех успешных оплат. Это похоже на сбой либо в записи логов, либо в работе приложения. Из-за этого в проекте сравниваются по неким общим чертам уникальные пользователи, их сессии, но их действия подробно не анализируются.</p></li><li><p align="justify">Кроме обучения, все рассматриваемые события образуют типичную последовательность действий: Главный экран --> Каталог --> Корзина --> Оплата. Именно в таком порядке события выстраиваются в воронку. Наибольшее число пользователей (до сорока процентов) теряется на переходе с главного экрана в каталог. Среди ничего не купивших пользователей проникновение в каталог - всего 10%, и лишь около процента хоть раз заходят в корзину.</p></li><li><p align="justify">Большинство первых покупок совершается в первую и вторую сессии - похоже, что пользователи скачивают приложение целенаправленно, заранее нацеливаясь на покупки. Чем выше номер некоторой сессии, тем больше по своему содержанию она похожа на клиентскую, а не пользовательскую. К двадцатой сессии не остаётся никого, кто ничего ни разу не купил.</p></li><li><p align="justify">Прошедшие обучение пользователи доходят до покупкок на 10% чаще, и почти на 20% чаще - до каталога. Среди ничего не купивших пользователей доля прошедших обучение не больше 2%, остальные проигнорировали обучение. Обучение в большинстве случаев проходят в первую сессию.</p></li><li><p align="justify">Клиентский retention, равно как содержание клиентской сессии незменны и постоянны. Коэффициент удержания - 60%, и одинаковый, независимо от активности клиента в приложении. Даже среди тех, кто пользуется приложением ежедневно и иногда по нескольку раз, доля что-либо купивших - 60% для каждой сессии. Не меняется и типичное содержание клиентской сессии: на протяжении семи сессий клиенты с неизменной активностью изучуют каталог и добавляют товары в корзину, а вот посещения главного экрана постепенно падают.</p></li><li><p align="justify">Статистически значимых различий в конверсиях нет (ни в одной из тридцати, что были проверены). Выборочные (фактические) различия в конверсиях - в пределах полутора-двух процентных пунктов. Размеров выборок было бы недостсаточно для того, чтобы зафиксировать даже самое значительное из этих различий с уровнем значимости 0.05 - даже для двухпроцентого различия нужны выборки размером не меньше 5000 уникальных пользователей на группу. А в этом датасете в группах по 2500 уникальных пользователей.</p></li></ol>
