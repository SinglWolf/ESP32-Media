# ESP32-Radiola
Форк проекта https://github.com/karawin/Ka-Radio32 на VSCode+PlatformIO

**Используемое железо (HARDWARE):**
  + Корпус - старый системный блок компьютера.
  + Силовой трансформатор - от УЛПЦТ, перемотанный на несколько напряжений.
  + Радиаторы - от усилителя Вега 50У-122С.
  + Аудиоколонки - от усилителя Вега 50У-122С.
  + 2 платы усилителя на TDA7293.
  + TDA7313 - аудиопроцессор.
  + VS1053B (MP3-декодер для web-радио).
  + UPC1237 - защита колонок от щелчков при включении/выключении и появлении постоянного напряжения.
  + BA3121 - изолирующий усилитель для подавления помех (шумов) при подключении VS1053B к TDA7313.
  + DS3231SN - часы реального времени. (Если нет интернета, короче :-)).
  + Вентилятор охлаждения радиаторов усилителя - 4-х пиновый (с ШИМ) от какой-то материнской платы компьютера.
  + DS1820 - датчик температуры для контроля нагрева радиаторов усилителя.
  + Цветной TFT дисплей 18x320x240 3,2 дюйма. Драйвер SPI на ILI9341.
  + Тачскрин на XPT2046.
  + IR-модуль с простым пультом.
  + ESP32-WROVER 16M flash, 8M SPIRAM - микроконтроллер, который рулит всем доступным железом в проекте ;-).

  **Внешний вид некоторых компонентов можно глянуть в каталоге [pictures](https://github.com/SinglWolf/ESP32-Radiola/tree/master/pictures).**


Проект делаю для себя. Никаких хроник изменений не веду. Как только реализую основные задачи, напишу развёрнутый мануал.
Проект на стадии Beta 1 :-)

**Вырезано из Ka-Radio32:**
  - Вырезаны все аудиокодеки, аудиодекодеры, кроме VS1053b
  - Вырезана поддержка всех дисплеев, кроме TFT ILI9341 18x240x320
  - Вырезаны все интерфейсы, кроме веб-интерфейса, тачскрина, энкодеров и ик-пульта
  - ...будет вырезано всё, что не используется :-)

**Реализовано сейчас:**
  + Написана библиотека для TDA7313 (аудиопроцессор)
  + Реализована тестовая поддержка TDA7313 в виде переключения каналов в зависимости от состояния проигывания станций радио. Play - вход 2 (VS1053), Stop - вход 1 (Компьютер).
  + Реализовано полное управление всеми функциями TDA7313 через web-интерфейс (в отдельной вкладке).
  + Реализован датчик температуры DS18B20 для контроля температуры радиаторов усилителя.
  + Реализован вывод показаний датчика температуры DS18B20 на странице веб-интерфейса.
  + Реализован тахометр (счётчик оборотов) вентилятора охлаждения радиаторов усилителя.
  + Реализован вывод показаний тахометра на странице веб-интерфейса.
  + Русифицирован веб-интерфейс.

**TODO (В ближайшее время):**
  + Реализовать другой механизм переназначения пинов ESP32.
  + Добавить ручное управление оборотами вентилятора охлаждения радиаторов усилителя
  + Добавить автоматическое управление оборотами вентилятора охлаждения радиаторов усилителя в зависимости то температуры радиаторов
  + Добавить звуковую индикацию событий BUZZER (пищалки).
  + etc...

![Image alt](https://github.com/SinglWolf/ESP32-Radiola/raw/master/pictures/ESP32-Radiola.png)
![Image alt](https://github.com/SinglWolf/ESP32-Radiola/raw/master/pictures/amplifier.jpg)
![Image alt](https://github.com/SinglWolf/ESP32-Radiola/raw/master/pictures/ESP32WROVER.jpg)
![Image alt](https://github.com/SinglWolf/ESP32-Radiola/raw/master/pictures/display.jpg)
