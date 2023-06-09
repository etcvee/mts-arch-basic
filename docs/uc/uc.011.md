# UC.011 Изменение места выступления
<!-- Подробное описание сценария использования системы с привязкой к ролям участников и задействованным бизнес-сущностям 
https://confluence.mts.ru/pages/viewpage.action?pageId=375782119 
-->

<!-- 
    Примечание для проверяющего:
    Поменял формат таблицы на HTML, т.к. в Markdown-таблицах очень трудно работать с многострочным текстом
-->

<table>
    <thead>
        <th>Название</th>
        <th>Изменение места выступления</th>
    </thead>
    <tbody>
        <tr>
            <td>Описание</td>
            <td>Пользователь вносит корректировки в место выступления докладчика (изменяет зал)</td>
        </tr>
        <tr>
            <td>Участники</td>
            <td>Администратор</td>
        </tr>
        <tr>
            <td>Триггер</td>
            <td>
                1. Пользователь находится в личном кабинете администратора</br>
                2. Появилась необходимость изменить место выступления</br>
            </td>
        </tr>
        <tr>
            <td>Предусловия</td>
            <td>
                1. Доклад утвержден экспертом<br/>
                2. Доклад ранее был добавлен в расписание<br/>
            </td>
        </tr>
        <tr>
            <td>Постусловия</td>
            <td>Место выступления изменено</td>
        </tr>
        <tr>
            <td>Успешный сценарий</td>
            <td>
                1. Система отображает расписание выступлений<br/>
                2. Пользователь выбирает доклад<br/>
                3. Пользователь выбирает из списка новый зал<br/>
                4.  Система проверяет, что интервал выстуления не пересекается с другими выступлениями<br/>
                    Если есть пересечения, запускается Альтернативный сценарий 1<br/>
                5.  Система проверяет, что в указанный интервал времени докладчик не выступает в других залах<br/>
                    Если есть пересечения, запускается Альтернативный сценарий 2<br/>
                6.  Система изменяет время выступления<br/>
                7.  Система отображает сообщение об успешном изменении времени выступления<br/>
            </td>
        </tr>
        <tr>
            <td>Альтернативный сценарий 1</td>
            <td>
                1.  Система отображает сообщение о пересечении с другим выступлением</br>
                2.  Пользователь изменяет время начала и/или продолжительность выступления</br>
                3. Система продолжает Успешный сценарий с шага 4.
            </td>
        </tr>
        <tr>
            <td>Альтернативный сценарий 2</td>
            <td>
                1. Система отображает сообщение о пересечении с другим выступлением (в другом зале)</br>
                2. Пользователь изменяет время начала и/или продолжительность выступления</br>
                3. Система продолжает Успешный сценарий с шага 4.
            </td>
        </tr>
        <tr>
            <td>Требования</td>
            <td>FR.015, FR.018</td>
        </tr>
    </tbody>
</table>