#sf-larakit-js

Навешиваем обработчик событие клика на все элементы с селектором ".js-click-alert"

~~~js
LarakitJs.initSelector('.js-click-alert', function () {
    $(this).on('click', function () {
        alert('Нажата кнопка!');
    });
});
~~~
И теперь система будет сама отслеживать появление в DOM элементов с таким селектором (как при первоначальной загружке, так и при обновлении дерева при помощи AJAX-запросов).

Фактически это работает таким образом:

1) есть кастомное событие "larakit.js", которое вызывается при $(document).ready()  и завершении AJAX-запроса.

2) делается запрос для всех зарегистрированных через LarakitJs.initSelector() селекторов наличие класса с префиксом "js-init-...", т.е. для приведенного примера будет проверяться наличие класса "js-init-click-alert" и, если он не будет обнаружен, то сперва навешивается обработчик события, а затем класс "js-init-...", символизирующий флаг навешенности обработчика
