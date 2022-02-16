# Описание
Ручей (Ruchey) - это универсальные инженерные раскладки, имеющие одинаковый набор и расположение символов, как для кириллицы, так и для латиницы. Отличительными чертами является полный набор спецсимволов, минимальные изменения по сравнению с русской раскладкой и удобство набора. Основное назначение - это набор технических текстов, а также кода программ с комментариями на Русском языке. Уделено внимание и минимизации переобучения. 

# Подробности
* Полный набор спецсимволов как в кириллической, так и в латинской раскладке
* Раскладки разработаны для операционных систем Linux (Debian/Ubuntu) и Windows
* Часть спецсимволов вынесены на третий уровень, т.е. набираются при зажатом правом Alt (AltGr)
* Часть спецсимволов смещена для удобства набора программного кода
* Предусмотрено, чтобы набор был комфортен для большого пальца и не было перекрещивания с указательным
* Переключаются именно раскладки, а не языки ввода. Язык ввода один - Русский

**Рис 1: Русская (инженерная, кириллица)**

![RUCHEY_C](https://user-images.githubusercontent.com/38563625/154332862-81e848c9-3eae-4a47-b5b1-bb62b1c27d15.png)

**Рис 2: Русская (инженерная, латиница)**

![RUCHEY_L](https://user-images.githubusercontent.com/38563625/154332902-a3118325-877f-464b-b8c1-4492f407ad7b.png)

# Некоторые рекомендации
При наборе фигурных и квадратных скобок, а так же символов меньше и больше, во время "слепой печати", рекомендуется переносить кисть так, чтобы маркером являлась не клавиша "О" ("J"), а правый Alt (AltGr). Т.е. кисть смещается, как если бы была необходимость воспользоваться стрелками.

# Установка и настройка в Windows
Для установки необходимо запустить файл **setup.exe** пакетов RUCHEY_L, RUCHEY_С из архива win-ruchey-\<version\>.zip.
В языковых параметрах **удалить раскладку Русская (ЙЦУКЕН)**, в предпочитаемых языках **удалить Английский**, применить раскладки для **экрана приветствия и учётных записей**.

> ![изображение](https://user-images.githubusercontent.com/38563625/154340117-ff1e9ce8-c613-4ee0-a31e-29406341a1f6.png)
  
> ![изображение](https://user-images.githubusercontent.com/38563625/154340195-95136751-4ba7-48e3-b0a0-98e6e6b27bdc.png)
  
> ![изображение](https://user-images.githubusercontent.com/38563625/154341690-fc78ea91-1e37-43b0-b6e4-48cb53f275ab.png)

[Ограничения и решение проблем](https://github.com/A-Projects/Ruchey/wiki/%D0%9E%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B8-%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%BE%D0%B1%D0%BB%D0%B5%D0%BC)

# Установка и настройка в Linux
В Linux раскладки будут доступны из коробки, начиная с пакета **xkeyboard-config-2.36**. Для установки в Debian 12 и ниже, Ubuntu 21.10 и ниже  достаточно установить пакет **xkb-ruchey_\<version\>_all.deb**. Для ранних версий Linux используется автоматический патчер, который добавляет раскладку даже после обновления пакета XKB.

#### Для применения раскладок в консоли 
Необходимо изменить файл "_/etc/default/keyboard_":
<pre>
XKBMODEL="pc104"
XKBLAYOUT="ru,ru"
XKBVARIANT="ruchey_latin,ruchey_cyrillic"
XKBOPTIONS="grp:caps_toggle,lv3:ralt_switch,grp_led:scroll"
BACKSPACE="guess"
</pre>

Где "grp:caps_toggle" - это метод переключения, а "lv3:ralt_switch" - это использование клавиши AltGr (правый Alt) для третьего уровня.
Методы переключения можно посмотреть командой <code>localectl list-x11-keymap-options</code>.

После изменения файла выполнить команду <code>update-initramfs -u</code>, в Debian/Ubuntu лучше выполнить <code>dpkg-reconfigure -phigh console-setup</code>.

#### Для применения раскладок в initramfs
Необходимо изменить файл: "_/etc/initramfs-tools/initramfs.conf_":
<pre>
KEYMAP=y
</pre>

После изменения файла выполнить команду: <code>update-initramfs -u</code>
