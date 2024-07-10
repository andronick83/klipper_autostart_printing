# Klipper Autostart Printing

Autostart printing on klipper boot
- Author: [andronick83.mail@gmail.com](mailto:andronick.mail@gmail.com) :shipit:
- License: [MIT License](http://opensource.org/licenses/MIT) :+1:

<hr>

(Further in Ukrainian)

# Макрос автостарту друку при завантаженні принтеру

## Для встановлення треба:
- Завантажити файл "printer_autostart.cfg" в папку з файлами конфігурації
- Додати в файл printer.cfg рядок:
```[include printer_autostart.cfg]```
- Додати gcode-файл "autostart.gcode" на USB-флешку(SD-картку)
- При наступному перезавантаженні запуститься таймер на 15 секунд, та почнеться друк файлу "sda1/autostart.gcode" (при наявності флешки з файлом в принтері)

## Команди макросу:
- Таймер перед початком друку можна прервати командою: ```AUTOSTART_BREAK```
- Подивитись/змінити поточні налаштування: ```AUTOSTART_SET```
- Для ввімкнення/вимкнення макросу є команди: ```AUTOSTART_SET ENABLED=True```, ```AUTOSTART_SET ENABLED=False```
- Шлях до флешки/картки (за замовчуванням "sda1/" для "ELEGOO Neptune 4", на інших принтерах шлях може відрізнятись) можна змінити командою: ```AUTOSTART_SET PATH="path-to-sda/"```
- Час таймеру (за замовчуванням 15 секунд) можна змінити командою: ```AUTOSTART_SET TIMEOUT=30```

## Процес друку:
- При початку друку файл "autostart.gcode" переіменовується на "autostart-printing.gcode". Це зроблено для відміни друку при повторному перезавантаженні принтеру.
- На кінці друку файл переіменовується на "autostart-done-{date}.gcode".
- Для повторного автозапуску дрку перейменуйте цей файл назад, або додайте новий "autostart.gcode"
