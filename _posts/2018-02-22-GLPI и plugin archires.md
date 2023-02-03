---
layout: post
title: GLPI и plugin archires  
---
Для собственной памяти запишу особенности настройки плагина [archires](https://forge.glpi-project.org/projects/archires), в переводе *Сетевые архитектуры* системы glpi --- оф.сайт [glpi-project.org/](https://glpi-project.org/).  
Далее описывается для версий glpi --- 9.2.4 и  archires --- 2.5.1.

### Для корректного отображения схемы необходимо чтобы каждый Объект из Активов:  
-   имел заполненное поле «Местоположение»  
-   имел сетевой порт  
-   сетевой порт был подключен к другому объекту  
-   для отображения иконок оборудования необходимо назначить типу оборудования изображение  

### Сопоставление иконки типу оборудования:  
-   поместить изображение (например размером 64*64 в формате png) в папку *glpi-root/plugins/archires/pics*  
-   назначить изображения типам объектов (Настройки\Плагины\Сетевые архитектуры --- /plugins/archires/front/config.form.php)  
![alt text](img/2018-02-22-GLPI и plugin archires-img0.png)  

[Иконки для Объектов](/img/pics.zip).

### Формирование схемы:  
Добавить Вид  (*Инструменты/Сетевые архитектуры\Просмотры* plugins/archires/front/view.php)  
![alt text](/img/2018-02-22-GLPI и plugin archires-img1.png)  
Добавить *Сетевая архитектура --- Местоположение* (*Инструменты/Сетевые архитектуры\Сетевая архитектура --- Местоположение* plugins/archires/front/locationquery.php)  
![alt text](/img/2018-02-22-GLPI и plugin archires-img2.png)  
В поле *Посмотреть* выбрать Вид созданный ранее, остальные поля менять в зависимости от ситуации.  
Если есть подчиненные местоположения --- то в поле *Подчинённые* указать *Да*.  
Нажав на *Сформировать* можно будет увидеть интерактивную карту сети --- нажатие на Объект откроет этот объект.  
![alt text](/img/2018-02-22-GLPI и plugin archires-img3.png)  

Написано автором[Ершов Сергей](https://blog.erchov.ru/author/serge/)[22.08.201806.09.2018](https://blog.erchov.ru/2018/08/glpi-%d0%b8-plugin-archires/)Написано в[Без рубрики](https://blog.erchov.ru/category/%d0%b1%d0%b5%d0%b7-%d1%80%d1%83%d0%b1%d1%80%d0%b8%d0%ba%d0%b8/)Метки: [glpi](https://blog.erchov.ru/tag/glpi/), [инвентаризация](https://blog.erchov.ru/tag/%d0%b8%d0%bd%d0%b2%d0%b5%d0%bd%d1%82%d0%b0%d1%80%d0%b8%d0%b7%d0%b0%d1%86%d0%b8%d1%8f/)[Оставьте комментарий к GLPI и plugin archires](https://blog.erchov.ru/2018/08/glpi-%d0%b8-plugin-archires/#respond)
