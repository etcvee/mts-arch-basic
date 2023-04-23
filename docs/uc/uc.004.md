# UC.004 Просмотр статуса рассмотрения доклада
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
        <th>Просмотр статуса рассмотрения доклада</th>
    </thead>
    <tbody>
        <tr>
            <td>Описание</td>
            <td>Пользователь получает информацию о статусе рассмотрения доклада. Если доклад отклонен, пользователь узнает причину отклонения</td>
        </tr>
        <tr>
            <td>Участники</td>
            <td>Докладчик</td>
        </tr>
        <tr>
            <td>Триггер</td>
            <td>Докладчик находится в личном кабинете и узнать статус рассмотрения доклада</td>
        </tr>
        <tr>
            <td>Предусловия</td>
            <td>
                1. Пользователь зарегистрирован на конференции в качестве докладчика<br/>
                2. Пользователь подавал хотя бы один доклад на рассмотрение<br/>
            </td>
        </tr>
        <tr>
            <td>Постусловия</td>
            <td>Пользователь ознакомлен с текущим статусом рассмотрения доклада</td>
        </tr>
        <tr>
            <td>Успешный сценарий</td>
            <td>
                1. Система отображает список зарегистрированных докладов текущего пользователя и их статусы<br/>
                2. Пользователь ищет интересующий его доклад и ознакамливается c его статусом<br/>
            </td>
        </tr>
        <tr>
            <td>Требования</td>
            <td>FR.004, FR.005</td>
        </tr>
    </tbody>
</table>