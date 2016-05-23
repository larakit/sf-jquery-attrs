# larakit/sf-jquery-attrs

### Установка пакета
~~~bash
composer require larakit/sf-jquery-attrs
~~~
Ничего дополнительно инициализировать не надо, добавив этот пакет в зависимости в composer.json, он сам установится и пропишется на всех страницах автоматически.

### Отключение пакета на некоторых роутах
В файле  ./app/Http/staticfiles.php добавьте
~~~php
\Larakit\StaticFiles\Manager::package('larakit/sf-jquery-attrs')
    ->addExclude('home')
    ->addExclude('admin.*');
~~~
тогда пакет не будет включен на главной странице и на всех страницах админки.