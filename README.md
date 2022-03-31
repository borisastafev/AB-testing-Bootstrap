# AB-testing-Bootstrap
# Основные даннные взяты с https://www.kaggle.com/datasets/zhangluyuan/ab-testing.

Данный дата-сет содержит наблюдения для контрольной группы(пользователям, которым был предложен старый дизайн сайта) и тестовая(которым доступен новый дизайн)
Также есть данные по конверсии для каждой из групп (какое-либо целевое действие), данные о времени эксперимента(он длится 22 дня).
Чтобы было больше данных для анализа метрик и применения различных иструментов при аб-тестировании - я  смоделировал данные о первой покупке для каждой группы пользователей. Данные имеют нормальное рапределение и у тестовой группы немного больше мат.ожидание этой величины(цены первой покупки).

# Дизайн АБ-теста:
 - Оценивать будем следующие метрики: конверсия (что нам уже дано) и средний чек (то, что я смоделирую), ARPU
 - Соответственно, выдвигаются следущие гипотезы: для конверсии, что значимых различий между двумя группами нету - это будет нулевой гипотезой, а альтернативной - что они есть; для среднего чека нулевая гипотеза будет та же - что различий нету (то есть в среднем, если мы будем вычитать средний чек контрольной группы из среднего чека тестовой - это разница будет равна нулю, в противном случае - число, отличное от нуля); ARPU - равны в качестве нулевой гипотезы и что ARPU тестовой группы > контрольной в качестве альтернативной 
 - Для конверсии я буду использовать Хи-квадрат в качестве стат.критерия(так как конверсия имеет биномиальное распределение), для среднего чека (AOV) буду использовать Bootstrap, для ARPU Bootstrap и t-test
 - уровень значимости при проверке гипотез буду использвать равным 0.01 и соответсвенно ДИ для данного уровня значимости будет составлять 99%
 - будем исходить из предположения, что контрольная и тестовая группы имеют равномерное распределение в данном рассматриваемом сегменте и что пользователи групп независимы

# Посмотрим, что из этого вышло и какие выводы я сделал.

 
