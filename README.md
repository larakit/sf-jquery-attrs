# larakit/sf-jquery-attrs

Плагин добавляет для всех jQuery-объектов возможность получения списка аттрибутов в виде ключ:значени

### Установка пакета
~~~bash
composer require larakit/sf-jquery-attrs
~~~
Ничего дополнительно инициализировать не надо, добавив этот пакет в зависимости в composer.json, он сам установится и пропишется на всех страницах автоматически.

### Использование

~~~html
<div class="qwe" data-id="123" id="block"></div>
~~~

<img src="https://habrastorage.org/files/9d0/0ed/629/9d00ed629b534094a0642fd502be2e2c.png"/>


### Отключение пакета на некоторых роутах
В файле  ./app/Http/staticfiles.php добавьте
~~~php
\Larakit\StaticFiles\Manager::package('larakit/sf-jquery-attrs')
    ->addExclude('home')
    ->addExclude('admin.*');
~~~
тогда пакет не будет включен на главной странице и на всех страницах админки.