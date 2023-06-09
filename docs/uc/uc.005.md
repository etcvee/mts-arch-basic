# UC.005 Отзыв доклада из рассмотрения
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
        <th>Отзыв доклада из рассмотрения</th>
    </thead>
    <tbody>
        <tr>
            <td>Описание</td>
            <td>Пользователь передумал выступать на конференции и хочет отозвать доклад из рассмотрения</td>
        </tr>
        <tr>
            <td>Участники</td>
            <td>Докладчик</td>
        </tr>
        <tr>
            <td>Триггер</td>
            <td>Пользователь находится в личном кабинете и хочет отозвать доклад из рассмотрения</td>
        </tr>
        <tr>
            <td>Предусловия</td>
            <td>
                1. Пользователь зарегистрирован на конференции в качестве докладчика<br/>
                2. Пользователь подавал хотя бы один доклад на рассмотрение<br/>
                3. Доклад находится на рассмотрении<br/>
            </td>
        </tr>
        <tr>
            <td>Постусловия</td>
            <td>Доклад снят с рассмотрения, статус доклада изменен на "Отозван"</td>
        </tr>
        <tr>
            <td>Успешный сценарий</td>
            <td>
                1. Система отображает список зарегистрированных докладов текущего пользователя и их статусы<br/>
                2. Пользователь выбирает нужный доклад<br/>
                3. Пользователь нажимает кнопку "Отозвать"<br/>
                   Если доклад не находится на рассмотрении, система переходит к Сценарию исключения 1<br/>
                4. Система переводит доклад в статус "Отозван"<br/>
                5. Система выводит сообщение об успешном отзыве доклада<br/>
            </td>
        </tr>
        <tr>
            <td>Сценарий исключения 1</td>
            <td>Система отображает сообщение о невозможности отозвать доклад</td>
        </tr>
        <tr>
            <td>Требования</td>
            <td>FR.004, FR.007</td>
        </tr>
    </tbody>
</table>