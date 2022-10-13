# dishwasher-siemens home assistant

Добавление посудомоечной машины siemens в lovelas home assistent c использованием интеграции 
https://www.home-assistant.io/integrations/home_connect/

## 
| ON                                                                                     | OFF                                                                          |
|----------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| ![ON](https://github.com/ananyevgv/dishwasher-siemens/blob/main/foto2.jpg)             | ![OFF](https://github.com/ananyevgv/dishwasher-siemens/blob/main/foto.jpg)  |


Загрузите в /config/www  7segment.css, 7segment.woff, siemens.jpg

На панели управления Lovelace щелкните три точки в правом верхнем углу и выберите Редактировать панель управления. Теперь снова щелкните три точки и выберите пункт Управление ресурсами. Нажмите Добавить ресурс в правом нижнем углу, затем введите /local/7 segment.css и убедитесь, что для типа задано значение Stylesheet. Сохраните запись.

Добовляем сенсоры в configuration.yaml
{{(  as_timestamp(states('sensor.posudomoechnaia_mashina_remaining_program_time')) - as_timestamp(now()) - 60*60*3 ) | timestamp_custom('%H:%M')  }}

- 60*60*3 (скорее всего проблема с таймзоной),вылечил пока так... (у вас может быть другое значение, 3 количество часов разночтения)

# Notes
7segment font (c) Jan Bobrowski (OFL) - http://torinak.com/7segment

https://github.com/alryaz/lg-washer-dryer-card

https://github.com/custom-cards/circle-sensor-card
