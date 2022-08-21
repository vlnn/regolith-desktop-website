---
title: Вступ
type: docs
bookToc: false
---

# Робочий стіл Regolith

![](/regolith-empty.png)

{{< columns >}}

### Продуктивність понад усе

Regolith оснований на [i3](https://i3wm.org/): поширеному, швидкому, та настроюваному мозаїчному менеджері вікон, що чудово підходить для швидкого робочого процесу з використанням гарячих клавіш. Regolith поєднує i3 з іншими компонентами робочого столу, такими як  `i3bar`, `rofication`, `gnome-flashback` та  [`ilia`](https://github.com/regolith-linux/ilia#readme), щоб сформувати повноцінний інтерфейс робочого столу.

<--->

### Системне управління GNOME

Regolith використовує механізм gnome-сесій [`gnome-flashback`](https://wiki.gnome.org/Projects/GnomeFlashback), тому він простіший за стандартні робочі середовища, що базуються на `gnome-shell`. Водночас, це робить можливим просте та послідовне управління системою.

{{< /columns >}}

***

# Встановіть Regolith 2.1

{{< tabs "uniqueid" >}}
{{< tab "Ubuntu 22.04" >}}

Regolith можна встановити як системний пакет. Це зробить оновлення та видалення простішим та більш послідовним. Наступні кроки (також доступні у вигляді [скріпта, що можна завантажити](/install-release-ubuntu-22.04-amd64.txt)) описують, як налаштувати вашу систему, аби завантажити пакети з репозіторія Regolith, та встановити пакет робочего столу.

1. Додайте публічний ключ Regolith до вашого локального `apt`:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | \
   gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   ```

1. Додайте URL репозиторія до вашого локального `apt`:

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/release-ubuntu-jammy-amd64 jammy main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

{{< hint info >}}
Замініть `arm64` на `amd64` в двох місцях у попередньому рядку, якщо вашу систему побудовано на архітектурі ARM.
{{< /hint >}}

1. Оновіть `apt` та встановіть Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop
   sudo apt upgrade
   ```

{{< hint info >}}
Пакет `regolith-desktop` включає в себе мінімальну (але функціональну) систему, що буде працювати на більшості обладнання. Аби розширити функціональність за допомогою додаткових пакетів, ознайомтесь з [Recommended Packages for New Users](/docs/using-regolith/configuration/#recommended-packages-for-new-users).
{{< /hint >}}

1. Перезапуск Системи

Задля того, щоб можна було розпочати сесію в новому робочому середовищі, потрібно перезапустити менеджер входу (login manager). Якщо ви не знаєте, як це зробити, просто перезавантажте свій комп'ютер.

{{< hint warning >}}
Робочий стіл Regolith Desktop дуже відрізняється від звичайних робочих середовищ. За замовчуванням на ньому немає доків, значків папок, або стандартних спадних меню. Ознайомтесь з [Getting Started guide]({{< ref "/docs/using-regolith/first-launch" >}}), аби дізнатися важливі деталі.

{{< /hint >}}

{{< /tab >}}

{{< tab "Ubuntu 20.04" >}}

Regolith можна встановити як системний пакет. Це зробить оновлення та видалення простішим та більш послідовним. Наступні кроки (також доступні у вигляді [скріпта, що можна завантажити](/install-release-ubuntu-20.04-amd64.txt)) описують, як налаштувати вашу систему, аби завантажити пакети з репозиторія Regolith, та встановити пакет робочего столу.

1. Додайте публічний ключ Regolith до вашого локального `apt`:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | sudo apt-key add -
   ```

1. Додайте URL репозиторія до вашого локального `apt`:

   ```console
   echo deb "[arch=amd64] https://regolith-desktop.org/release-ubuntu-focal-amd64 focal main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

{{< hint info >}}
Замініть `arm64` на `amd64` в двох місцях у попередньому рядку, якщо вашу систему побудовано на архітектурі ARM.
{{< /hint >}}

1. Оновіть `apt` та встановіть Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop
   sudo apt upgrade
   ```

{{< hint info >}}
Пакет `regolith-desktop` включає в себе мінімальну (але функціональну) систему, що буде працювати на більшості обладнання. Аби розширити функціональність за допомогою додаткових пакетів, ознайомтесь з [Recommended Packages for New Users](/docs/using-regolith/configuration/#recommended-packages-for-new-users).
{{< /hint >}}

1. Перезапуск Системи

Задля того, щоб можна було розпочати сесію в новому робочому середовищі, потрібно перезапустити менеджер входу (login manager). Якщо ви не знаєте, як це зробити, просто перезавантажте свій комп'ютер.

{{< /tab >}}

{{< tab "Debian Bullseye" >}}

Regolith можна встановити як системний пакет. Це зробить оновлення та видалення простішим та більш послідовним. Наступні кроки (також доступні у вигляді [скріпта, що можна завантажити](/install-release-debian-11-amd64.txt)) описують, як налаштувати вашу систему, аби завантажити пакети з репозиторія Regolith, та встановити пакет робочего столу.

1. Додайте публічний ключ Regolith до вашого локального `apt`:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | \
   gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   ```

1. Додайте URL репозиторія до вашого локального `apt`:

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/release-debian-bullseye-amd64 bullseye main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```
{{< hint info >}}
Замініть `arm64` на `amd64` в двох місцях у попередньому рядку, якщо вашу систему побудовано на архітектурі ARM.
{{< /hint >}}

1. Оновіть `apt` та встановіть Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop
   sudo apt upgrade
   ```

{{< hint info >}}
Пакет `regolith-desktop` включає в себе мінімальну (але функціональну) систему, що буде працювати на більшості обладнання. Аби розширити функціональність за допомогою додаткових пакетів, ознайомтесь з [Recommended Packages for New Users](/docs/using-regolith/configuration/#recommended-packages-for-new-users).
{{< /hint >}}

1. Перезапуск Системи

Задля того, щоб можна було розпочати сесію в новому робочому середовищі, потрібно перезапустити менеджер входу (login manager). Якщо ви не знаєте, як це зробити, просто перезавантажте свій комп'ютер.

{{< /tab >}}
{{< tab "Образ Regolith Linux 2.1 ISO" >}}

Regolith Linux -- це середовище Regolith Desktop, що встановлено у спеціально налаштований образ інсталятора Ubuntu 22.04.  Він дозволяє завантажитися з USB диска і запустити Regolith без інсталляції. Він також дозволяє встановити Regolith Linux на диск вашого комп'ютера. Regolith Linux відрізняється від Regolith Desktop наступними додатковими можливостями:

* Логотип Regolith під час завантаження та на екрані входу
* Використання менеджера екранів `lightdm` замість `gdm3`, щоб уникнути зайвих залежностей
* Наступні пакети не встановлено за замовчуванням: `gdm3`, `gnome-shell`, `ubuntu-session`, `evolution-data-server`, `snapd`.  Їх можна встановити за потреби додатково.

Образ диска ISO поставляється у двох форматах: "mini ISO" з дещо зменшеними можливостями та тільки одною візуальною темою, та "default ISO", який дещо більший за розміром, але має вбудовану підтримку всіх офіційних тем та встановлюється з дещо більшою кількістю індикаторів стану.

* [Regolith Linux 2.1.1](https://github.com/regolith-linux/regolith-ubuntu-iso-builder/releases/download/ubuntu-jammy-2.1.1-20220807_181202/regolith-ubuntu-jammy-2.1.1.zip)
* [Regolith Linux 2.1.1 Mini](https://github.com/regolith-linux/regolith-ubuntu-iso-builder/releases/download/mini-ubuntu-jammy-2.1.1-20220807_180918/regolith-mini-ubuntu-jammy-2.1.1.zip)

За додатковою інформацією зверніться до [Regolith 2.1 release notes](docs/reference/Releases/regolith-2.1-release-notes).

В різних операційних системах образ ISO записується на USB диск по-різному: у Linux використовуйте [dd](https://www.man7.org/linux/man-pages/man1/dd.1.html), [GNOME Disk Utility](https://wiki.gnome.org/Apps/Disks), чи [KDE ISO Image Writer](https://community.kde.org/ISOImageWriter). У macOS використовуйте [Etcher](https://www.balena.io/etcher/). У Windows використовуйте [Rufus](https://rufus.ie/) та робіть запис у режимі DD mode.

{{< /tab >}}
{{< tab "Оновлення з Regolith 1.6" >}}

Щоб встановити Regolith 2 поверх існуючої системи Ubuntu, що можливо оновити до версії 22.04, виконайте наступні дії:

1. Оновіть систему до найновітніших пакетів, доступних у поточній версії (або Ubuntu 20.04 або 21.10)
1. Виконайте [оновлення Ubuntu до 22.04](https://www.omgubuntu.co.uk/2022/04/how-to-upgrade-to-ubuntu-22-04-lts), але **НЕ ПЕРЕЗАВАНТАЖУЙТЕСЬ ДОПОКИ НЕ ВИКОНАЄТЕ НАСТУПНИХ ДІЙ!**
1. Одразу після оновлення до 22.04, додайте репозиторій Regolith 2:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] https://regolith-desktop.org/release-ubuntu-jammy-amd64 jammy main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   sudo apt update
   ```

1. Далі установіть пакет з Regolith 2:

   ```console
   sudo apt install regolith-desktop
   sudo apt dist-upgrade
   ```

{{< hint info >}}
Пакет `regolith-desktop` включає в себе мінімальну (але функціональну) систему, що буде працювати на більшості обладнання. Аби розширити функціональність за допомогою додаткових пакетів, ознайомтесь з [Recommended Packages for New Users](/docs/using-regolith/configuration/#recommended-packages-for-new-users).
{{< /hint >}}

1. Далі перезавантажте систему та оберіть сесію regolith під час входу в систему

Індивідуальні конфігурації з Regolith 1.6 потрібно вручну змінити так, щоб вони працювали з Regolith 2.  Задля того, щоб спростити цей процес, Regolith 2 читає налаштування користувача з директорії `~/.config/regolith2`.  Він не читає конфігураційні файли Regolith 1.x з директорії `~/.config/regolith`.  Будь ласка, прочтіть [the configuration page](docs/using-regolith/configuration) за більш деталізованим описом конфігурації.

{{< /tab >}}
{{< /tabs >}}


## Візуальний тур
***

{{< columns >}}

![](/regolith-ilia-keybindings.png)
Після першого запуска з'явиться допоміжне вікно (його можна де-активувати чи активувати знов за допомогою <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">?</span></span>) з найважливішими клавіатурними командами, що використовуються в i3-wm.

<--->

![](/regolith-floating-terminal.png)
Якщо ви звикли працювати в терміналі, все що вам потрібно, аби почати роботу, це натиснути <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">enter</span></span>.

{{< /columns >}}

{{< columns >}}

![](/regolith-ilia-apps.png)
Запускайте будь-які застосунки через єдиний глобальний інтерфейс за допомогою <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">space</span></span>.</p>

<--->

![](/regolith-desktop-terminals.png)
Потрібно більше терміналів? Створюйте різні розкладки вікон на льоту, перемикайтесь між горизонтальним та вертикальним розміщеннями вікон за допомогою <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">backspace</span></span>, а після <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">enter</span></span>.  Перемикайтесь між вікнами за допомогою <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">h</span> <span class="badge badge-warning">j</span> <span class="badge badge-warning">k</span> <span class="badge badge-warning">l</span></span>.

{{< /columns >}}

{{< columns >}}

![](/regolith-floating-windows.png)
Вмикайте і вимикайте режим плаваючого вікна за допомогою <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">F</span></span>.  Змінюйте розміри вікна з <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">r</span></span> та переміщайте його по екрану мишою, одночасно натискаючи клавішу <span class="badge badge-warning">super</span>.

<--->

![](/regolith-gnome-flashback.png)
Gnome Flashback надає можливості послідовного та простого управління системою. Підлаштовуйте інтерфейс користувача, автоматично підключайте USB диски, підключайтесь до бездротових мереж. Запустіть контрольну панель за допомогою <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">c</span></span>.

{{< /columns >}}

{{< columns >}}

![](/regolith-screenshot-look-selector.png)
Легко переключайтесь до будь-яких тем (наприклад <a href="https://ethanschoonover.com/solarized">Solarized</a>) командою <code>regolith-look</code>. Оскільки <b>теми (looks)</b> використовують пакетний менеджер, на ваш диск встановляться лише ті ресурси, якими ви користуєтесь.

<--->

![](/regolith-ilia-windows.png)
Багато чого відбувається? Швидко знаходьте вікно, яке вам потрібне, за допомогою <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">ctrl</span> <span class="badge badge-warning">space</span></span> або переходьте між робочими столами за допомогою <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">[0 - 19]</span></span>.

{{< /columns >}}

{{< columns >}}

![](/regolith-many-windows.png)
Не витрачайте екранне місце на легковажний інтерфейс користувача, та використовуйте кожний піксель (і вам не буде потрібно вручну налаштовувати віконні розкладки).

<--->

![](/regolith-ilia-notifications.png)
Сповіщення вашого робочого столу не конкурують за вашу увагу, а просто зібрані у спеціальному вікні, яке можна визвати натисненням <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">n</span></span>.

{{< /columns >}}

# Interaction

{{< columns >}}

### Announcements

* [Слідкуйте за нами на Twitter, щоб отримати останні новини](https://twitter.com/RegolithL)
* [Слідкуйте за нами на Mastodon, щоб отримати останні новини](https://fosstodon.org/@regolith)
* [Підпишіться на поштову розсилку для оголошень про нові релізи](https://www.freelists.org/list/regolith-linux)

<--->

### Обговорення та допомога

* Приєднуйтесь до нас у [Обговореннях GitHub](https://github.com/orgs/regolith-linux/discussions), якщо ви потребуєте допомоги чи бажаєте щось обговорити
* Шукайте по [активним звітах о проблемах чи зробіть новий звіт](https://github.com/regolith-linux/regolith-desktop/issues) щоб отримати інформацію щодо програмних помилок та запитів на нові функції
<--->

### Розробка

* Вся розробка відбувається на [Regolith GitHub org](https://github.com/regolith-linux)

{{< /columns >}}
