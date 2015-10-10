# Rackman
Утилита, позволяющая измерять растояния в пикселях, миллиметрах, дюймах и пунктах Adobe на экране вашего монитора. 
Представляет собой два окна:
  1. **главное** (*Master*), содержащее численную информацию и меню;
  2. **дочернее** (*Slave*), представляющее собой некий измерительный инструмент.

Написана на Python и GTK.

![Главное окно](https://leto13f.storage.yandex.net/rdisk/83da2574401a797cf1e9fc55a4f6b157efea66d656a67be37ff4bdd29933046f/inf/nCP3UpOegGpBSReEjv4i7VzLOqy08WIEkBBDGuVYljZk6YkOrnd-QXg3YkeK7wS23szsVPkUIpyKN_V2YqrWhA==?uid=84330535&filename=master_1.9.0.png&disposition=inline&hash=&limit=0&content_type=image%2Fpng&tknv=v2&rtoken=5ab844437887d2e4a2555aab636f2d71&force_default=yes&ycrid=na-12b166efaf52cf94cf0fc3e3c8d4d1e2-downloader10g)

## Размеры
Rackman позволяет измерять высоту и ширину объектов на экране.

![Измерение высоты](https://img-fotki.yandex.ru/get/4512/84330535.0/0_ac93c_9af2e4be_orig)

## Диагональ
Rackman позволяет измерять длину диагонали.

## Углы
Rackman позволяет измерять горизональные и вертикальные углы.

![Измерение углов](https://img-fotki.yandex.ru/get/6302/84330535.0/0_ac7db_66af0cdf_orig)

## Центры
Rackman позволяет визуально отслеживать центрирование.

![Центровка](https://img-fotki.yandex.ru/get/1/84330535.0/0_ac842_121e24fb_orig)

## Управление дочерним окном измерения (Slave)
* Попиксельное изменение ширины и высоты окна
  - <kbd>&#8592;</kbd>, <kbd>&#8593;</kbd>, <kbd>&#8594;</kbd>, <kbd>&#8595;</kbd>

* Попиксельное перемещение окна
  - <kbd>Ctrl</kbd> + <kbd>&#8592;</kbd>, <kbd>&#8593;</kbd>, <kbd>&#8594;</kbd>, <kbd>&#8595;</kbd>
  
* Быстрое изменение размеров и перемещение окна
  - <kbd>Shift</kbd> + <kbd>&#8592;</kbd>, <kbd>&#8593;</kbd>, <kbd>&#8594;</kbd>, <kbd>&#8595;</kbd>
  - <kbd>Shift</kbd> + <kbd>Ctrl</kbd> + <kbd>&#8592;</kbd>, <kbd>&#8593;</kbd>, <kbd>&#8594;</kbd>, <kbd>&#8595;</kbd>
  - используйте нативные методы вашего DE.

## Установка и запуск
### Stand-alone версия
``` bash
# скачивание последней версии
$ wget https://github.com/FRiMN/Rackman/archive/master.zip
# распаковка
$ unzip master.zip
# переход в директорию
$ cd ./Rackman-master/
# установка прав на чтение и выполнение всем и на запись пользователю
$ chmod u=rwx,g=rx,o=rx rackman.py
# запуск Rackman
$ ./rackman.py
```

### Установка из репозиториев (только для Ubuntu)
``` bash
$ sudo add-apt-repository ppa:freezemandix/rackman
$ sudo apt-get update
$ sudo apt-get install rackman
```

### ebuild для Gentoo
https://github.com/msva/mva-overlay/blob/master/x11-misc/rackman/rackman-9999.ebuild

## Известные баги и особенности
- Измеритель -- обычное окно, со всеми вытекающими (например: нельзя померить в местах недоступных для размещения окон)
- Быстрое перемещение и изменение размера окна измерения полностью зависит от натроек вашего DE
- Если в вашем DE есть умное поведение окон (прилипание и т.п.), то оно будет применяться и к измерителю, что не всегда удобно
- Изменение цвета и прозрачности с клавиатуры работает только для Master-окна (окно должно быть в фокусе)
- Центральные прерывистые линии могут быть несколько размазаны при чётных высоте или ширине окна. Это особенности рендринга gtk и cairo линий располагающихся "между пикселей"
- Размеры по вертикали для производных единиц (все кроме px) могут быть несколько меньше реальных (~0.5mm)
