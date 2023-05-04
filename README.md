### Data_analysis_E-learning
*Предварительный анализ данных, расчет показателей, RFM-анализ*

**Задача**
Продакт-менеджер Василий попросил вас проанализировать завершенные уроки и ответить на следующие вопросы:
 - Сколько студентов успешно сдали только один курс? (Успешная сдача — это зачёт по курсу на экзамене)
 - Выяви самый сложный и самый простой экзамен: найди курсы и экзамены в рамках курса, которые обладают самой низкой и самой высокой завершаемостью*.
 - По каждому предмету определи средний срок сдачи экзаменов (под сдачей понимаем последнее успешное прохождение экзамена студентом).
 - Выяви самые популярные предметы (ТОП-3) по количеству регистраций на них. А также предметы с самым большим оттоком (ТОП-3).
 - Используя pandas, в период с начала 2013 по конец 2014 выяви семестр с самой низкой завершаемостью курсов и самыми долгими средними сроками сдачи курсов.
 - Используя python, построй адаптированные RFM-кластеры студентов, чтобы качественно оценить свою аудиторию. В адаптированной кластеризации можешь выбрать следующие метрики: R - среднее время сдачи одного экзамена, F - завершаемость курсов, M - среднее количество баллов, получаемое за экзамен. Подробно опиши, как ты создавал кластеры. Для каждого RFM-сегмента построй границы метрик recency, frequency и monetary для интерпретации этих кластеров.
 - Для решения задачи проведи предварительное исследование данных и сформулируй, что должно считаться курсом. Обосновать свой выбор ты можешь с помощью фактов сдачи экзаменов, распределения студентов и уникальный идентефикатор курса. *завершаемость = кол-во успешных экзаменов / кол-во всех попыток сдать экзамен

**Выполнено**
- проведено предварительное исследование данных, данные очищены, выявлены аномалии
- рассчитаны необходимые показатели
- перед проведением RFM-анализа проведена проверка данных и обоснован выбор показателей для деления на группы. Выявлена аномалия в распределении оценок студентов
![scores distribution e-learning](https://user-images.githubusercontent.com/128238543/236151070-507cd3e9-ba65-48b4-b45b-39408b5e7962.png)
- проведен RFM-анализ (деление пользователей на группы в соответствии с их поведением) и полученные данные визуализированы.
![rfm](https://user-images.githubusercontent.com/128238543/236152049-00e5024c-5b2f-4fd3-b8c4-fb042aa5d907.png)
 - визуализировано распределение пользователей по оценкам
![rfm distributions](https://user-images.githubusercontent.com/128238543/236152294-ed554b5e-e3b3-4c5f-9c8d-26afb2f36c0d.png)
 - визуализировано распределение оценки F относительно M и R
![distribution of F](https://user-images.githubusercontent.com/128238543/236152553-d8fce0ec-6f3e-4b58-be6d-0fe35e8a17a0.png)

**Выводы и рекомендации**

 - Провести мероприятия по усовершенствованию сбора данных, так как часть данных почему-то не попала в таблицы (оценки за экзамены), часть ячеек была не заполнена.
 - Выявлено, что основной причиной незавершения курса является отмена регистрации, а не несдача экзамена или проблемы при обучении. В среднем отток составляет 30%. Рекомендовала бы принять решение нужны ли такие студенты платформе (приносят ли они прибыль или наоборот наносят репутационный вред). Если прибыли не приносят, то можно разработать ряд мероприятий, позволяющий студентам предварительно оценить насколько они готовы к прохождению курса: разместить демонстрационный доступ, тест, более полную программу курса с ссылками на дополнительные материалы.
 - Я считаю, что отток студентов слишком велик. Я бы рекомендовала провести опрос среди студентов, которые отменили регистрацию и выяснить причины отмены, чтобы повлиять на них и в будущем снизить количество отмен регистраций.
 - Данные по сдаче экзаменов выглядят так, как будто в них искусственно вмешались (выбросы на значениях, кратных 20). Я бы рекомендовала проверить механизм сдачи экзаменов и попытаться выяснить почему так велико число студентов, сдавших его на 100%.
