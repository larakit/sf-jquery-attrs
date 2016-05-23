# larakit/sf-jquery

### Установка пакета
~~~bash
composer require larakit/sf-jquery
~~~
Ничего дополнительно инициализировать не надо, добавив этот пакет в зависимости в composer.json, он сам установится и пропишется на всех страницах автоматически.

### Отключение пакета на некоторых роутах
В файле  ./app/Http/staticfiles.php добавьте
~~~php
\Larakit\StaticFiles\Manager::package('larakit/sf-jquery')
    ->addExclude('home')
    ->addExclude('admin.*');
~~~
тогда пакет не будет включен на главной странице и на всех страницах админки.

### Изменение состава подключаемой статики пакета
Если вы использовали какой-то пакет, который за собой потянул этот пакет, но вас не устраивает версия библиотеки, подключаемая по умолчанию (например не хотите использовать CDN, а хотите отдавать со своего сайта), то вместо базового способа инициализации пакета
~~~php
\Larakit\StaticFiles\Manager::package('larakit/sf-jquery')
  ->js('//cdnjs.cloudflare.com/ajax/libs/jquery/2.1.4/jquery.min.js');
  ~~~
  вы можете переопределить его, вызвав инициализацию пакета еще раз
  ~~~php
\Larakit\StaticFiles\Manager::package('larakit/sf-jquery')
  //очистить список подключенных JS
  ->clearJs()
  //добавить свой
  ->js('/jquery.js');
  ~~~
