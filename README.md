### Описание
Волшебный скрипт, блокирующий Ваш сайт. По крайней мере изумлённый пользователь будет так думать.  
Надо всего-лишь добавить к себе одним из следующих способов:

```HTML
<!-- Используя CDN от jsDelivr -->
<script src="https://cdn.jsdelivr.net/npm/runet/dist/runet.min.js" async></script>

<!-- ...или же от unpkg. -->
<script src="https://unpkg.com/runet/dist/runet.min.js" data-cdn="https://unpkg.com/runet/dist/" async></script>
```
Обратите внимание, во втором случае у тега `<script>` присутствует аттрибут `data-cdn`, в котором также указан unpkg. Это необходимо, чтобы ресурсы подгружались не с jsDelivr.  
В случае, если на вашем сайте включен Content Security Policy, обязательно убедитесь, добавлена ли нужная CDN в `script-src` и `style-src`.

Также, Вам никто не мешает скачать скачать всё себе и залить на свой сайт вручную. В таком случае, от всего проекта вам понадобится только папка `dist/`, а к тегу `<script>` необходимо будет добавить аттрибут `data-is-self-hosted` (обязательно без значения!).  
В результате должно получиться что-то вот такое:

```HTML
<script src="path/to/dist/runet.min.js" data-is-self-hosted async></script>
```

### Кастомизация
Её мало, но есть у меня. Пока что можно воздействовать только на следущие вещи:  

* Отключение заглушки

Достигается добавлением аттрибута `data-disabled` (обязательно без значения).

```HTML
<script src="..." data-disabled async></script>
```

* Показ IP-адреса пользователя

Достигается добавлением этого-самого IP-адреса значением аттрибута `data-user-ip` средствами сервера. Иначе, просто-напросто ничего не покажется.

```HTML
<script src="..." data-user-ip="127.0.0.1" async></script>
```

* Смена времени у таймера, показывающего футер с "разгадкой"

По-умолчанию равно 8 секундам, но с помощью аттрибута `data-timer` возможно указать другое значение (в миллисекундах).

```HTML
<script src="..." data-timer="3000" async></script>
<!-- футер покажется через 3 секунды -->
```
