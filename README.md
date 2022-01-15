# Описание
Ручей (Ruchey) - это универсальные инженерные раскладки, имеющие одинаковый набор и расположение символов, как для кириллицы, так и для латиницы. Отличительными чертами является полный набор спецсимволов, минимальные изменения по сравнению с русской раскладкой и удобство набора. Основное назначение - это набор технических текстов, а также кода программ с комментариями на Русском языке. Уделено внимание и минимизации переобучения. 

# Подробности
* Раскладки разработаны для операционных систем Linux и Windows.
* Часть спецсимволов вынесены на третий уровень, т.е. набираются при зажатом правом Alt (AltGr).
* Часть спецсимволов смещена в для удобства набора программного кода.
* Предусмотрено, чтобы набор был комфортен для большого пальца и не было перекрещивания с указательным.
* Переключаются именно раскладки, а не языки ввода. Язык ввода один - Русский.

**Рис 1: Русская (инженерная, кириллица)**

![RUCHEY_C](https://user-images.githubusercontent.com/38563625/149615209-fb63cbaf-8c34-4eae-9e38-3cd9df908e43.png)

**Рис 2: Русская (инженерная, латиница)**

![RUCHEY_L](https://user-images.githubusercontent.com/38563625/149615211-83f1486e-3db0-4505-9724-8cb65ec1df79.png)

# Не которые рекомендации
При наборе фигурных и квадратных скобок, а так же символов меньше и больше, во время "слепой печати", рекомендуется переносить кисть так, чтобы маркером являлась не клавиша "О", а правый Alt (AltGr). Т.е. кисть смещается, как если бы была необходимость воспользоваться стрелками.

# Ограничения и решение проблем
В Windows могут появляться штатные раскладки (Русская, Английская). Проблема общая, например, у Американцев появляется Британская раскладка. Решение проблемы - перейти в **"Настройки зяыка"** - **"Административные параметры"** и применить раскладки для **"Экран приветствия и учётных записей"**. А также в настройках реестра для каталога **"Компьютер\HKEY_USERS\.DEFAULT\Keyboard Layout\Preload"** выключить наследовании и указать для всех права только на чтение. 

Для Linux, на данный момент, нет возможности разработать пакет, раскладки должны быть приняты в код апстрима, поэтому разработан инсталлятор, который нужно запускать всегда после системных обновлений. Надеюсь , что патчи примут и эта проблема просто уйдёт.

Знак ₽ отсутствует в раскладке для Windows т.к. является символом юникода. 
