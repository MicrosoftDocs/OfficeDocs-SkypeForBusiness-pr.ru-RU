---
title: Управление приложением "Praise" в Центре администрирования Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: adotey
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: Параметры администрирования в приложении "Praise" в Центре администрирования Microsoft Teams
ms.openlocfilehash: acb9d000aeec61daa35421c5ded389888032873f
ms.sourcegitcommit: d2e67f2eed7b817c2c5f76015ec11582d0e0cb9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2021
ms.locfileid: "50037855"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Управление приложением "Praise" в Центре администрирования Microsoft Teams

> [!NOTE]
> Для доступа к этой функции администраторам должна быть лицензия на Teams. При попытке доступа к этой функции без лицензии на Teams вы получите сообщение об ошибке.

Приложение "Благодарность" в Microsoft Teams помогает пользователям продемонстрировать признательность сотрудникам своей организации или класса. Благодаря набору эмблем на выбор и возможности создавать собственные эмблемы praise помогает распознать усилия, которые делают пользователи Teams: от преподавателей до сотрудников, работающих прямой телефон. Для получения дополнительных информации, ознакомьтесь с [отправкой praise to people.](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)

Администраторы могут управлять тем, какие эмблемы доступны для организации в Центре администрирования Microsoft Teams. В левой области навигации перейдите в приложения **Teams и > управление приложениями.** В списке приложений нажмите кнопку **"Praise"** и выберите **"Параметры".**  Здесь вы можете включить наборы эмблем по умолчанию и встроенные, а также создать собственные эмблемы.

![Снимок экрана вкладки "Параметры" для приложения "Praise"](media/manage-praise-app-settings.png)

> [!NOTE]
> Приложение "Praise" не доступно для облачных облаков государственных органов США.

## <a name="use-built-in-badge-sets"></a>Использование встроенных наборов эмблем

Встроенные наборы — это наборы эмблем, разработанных корпорацией Майкрософт для приложения "Praise". Администраторы не могут изменять эти наборы. Набор эмблем по умолчанию уже включен и доступен в приложении "Praise". Чтобы изменить доступность набора по умолчанию или других наборов эмблем, установите соответствующий переключатель в переключатель "Вкл." или "Выкл.". 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>Эмблемы по умолчанию

Набор эмблем по умолчанию помогает пользователям Teams распознавать своих коллег, чтобы затем работать над ними и за их пределами.

![Предварительный просмотр набора эмблем по умолчанию](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>Социальные и эмоциональные индикаторы обучения для образовательных сфере

Преподаватели могут распознать отдельных учащихся для достижения и поведения в социальных и эмоциональных сетях (SEL) с помощью эмблем, которые показывают эти понятия.

![Предварительный просмотр социальных и эмоциональных индикаторов обучения для образовательных сфере](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>Создание собственных эмблем

Выберите **"Создать настраиваемый значок".** Здесь вы можете создать настраиваемый значок на боковой панели. Можно создать до 25 настраиваемой эмблемы. 

![Снимок экрана: создание настраиваемой области эмблем](media/manage-praise-app-create-custom-badge.png)

1. Введите имя эмблемы. Это имя, которое будет отображаться на значке при отправке пользователями praise.

2. Настройка цветов эмблемы. Чтобы настроить цвета текста и фона эмблемы, необходимо ввести их в виде hexadecimal (hex).

   > [!TIP]
   > Если вы еще не знаете, как использовать hex-значения, в этой статье вы сможете быстро узнать, как их использовать. [](#hex-colors-intro)

3. Загрузить эмблему. Тип файла: PNG. Размер файла изображения должен быть меньше 40 КБ и максимальным размером 216 X 216 пикселей.
![Эмблема с полями фона, текста и изображений](media/praise-app-badge-fields.png)

4. Локализование имени эмблемы: В **локализованных именах эмблем** выберите **"Добавить".** Выберите нужный локализованный в списке. Затем введите имя эмблемы на назначенном языке.

5. Исключите эмблему из определенных стран: в области **"Исключение эмблемы из этих локали"** выберите **"Добавить".** Выберите в списке региональные органы, которые нужно исключить.

6. Выберите **"Применить".** Новый значок появится в таблице настраиваемой эмблемы.

> [!NOTE]
> Если шаги 4 и 5 пропускаются, эмблема будет на языке по умолчанию для всех языков.
>
> Завершив внесение изменений в выбор эмблемы, выберите **"Отправить".** Для того чтобы эти изменения появились в вашей организации, может потребоваться до нескольких часов.

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>Указание цветов с помощью hex-значений

Шестн.значения цветов — это строки из шести шестеренки, которые представляют интенсивность красного (RR), зеленого (GG) и синего (BB) цвета определенного цвета в масштабе от 00 до FF. При сложении значений всех трех цветов вы получаете hex value: #RRGGBB

Например, значение в hex красного цвета #FF0000 так как красный — максимально возможное значение, FF и зеленый и синий — имеют минимальное возможное значение 00.

Чтобы изучить различные цвета и их hex-значения, ознакомьтесь с палитрой [цветов Bing.](https://www.bing.com/search?q=color+picker)

Ниже приведен список примеров цветов, с которые можно начать.

|Цвет  |Hex value|
|-------|---------|
|![цвет hex #FF6666](media/hexColor1.png)|  #FF6666   |
|![цвет hex #7FFFD4](media/hexColor2.png)|  #7FFFD4   |
|![цвет hex #FF75F0](media/hexColor3.png)|  #FF75F0   |
|![цвет hex #00BFFF](media/hexColor4.png)|  #00BFFF   |
|![цвет hex #800080](media/hexColor5.png)|  #800080   |
|![цвет hex #000000](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>Создание настраиваемой эмблемы

**Отправьте все эмблемы одновременно.** Так как обработка новых эмблем занимает некоторое время, лучше всего добавить в таблицу все настраиваемые эмблемы перед их отправкой.

**При выборе цветов помните о доступности.** Одни цвета лучше остальных.  Создайте контраст между текстом и цветами фона, чтобы имя эмблемы было легко читать. Например, если вы выбрали темный цвет фона, выберите светлый цвет текста.

**При выборе изображения не нужно помнить о размерах эмблемы.** Для лучшего качества рекомендуется добавить файл изображения размером 216 x 216 пикселей (это максимальный размер). Избегайте растяжения или искажения изображения в таких размерах.

**Если изображение эмблемы не прямоугольное, сделайте его прозрачным.** Это необходимо сделать перед отправкой файла изображения в praise.

![Слева: эмблема с непрозрачным изображением, справа: эмблема с прозрачным изображением](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>Эмблема для набора активов

Встроенные наборы эмблем изменить нельзя, поэтому если включен встроенный набор, все эмблемы в наборе добавляются в приложение "Praise". Если вы хотите добавить определенные эмблемы из встроенного набора и оставить их другими, создайте их повторно. Вы можете скачать эмблему и найти цвета текста и фона эмблем из встроенных наборов в таблицах ниже.

### <a name="default-badges-assets"></a>Эмблемы по умолчанию

</br>

|Имя эмблемы     |Файл изображения  |Цвет текста | Цвет фона |
|---------------|------------|---------- |--------|
|Achiever       |[Achiever PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|Замечательно        |[Отличный PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png)</a>|#8283B2    |#D1EFF2|
|Тренер          |[Coach PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Заметь        |[PNG-png Изве-ва](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|Творческий       |[Creative PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|Включительно      |[Включительно PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|Kind Heart     |[Kind Heart PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|Руководство     |[Leadership PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership-badge.png)|#419098    |#D2EAEC|
|Веха       |[Веха PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|Решение проблемы |[PNG-решение проблем](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|Игрок команды    |[Team player PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|Спасибо      |[Благодарим за PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>Эмблемы социального и эмоциональных обучения для образовательных активов

</br>

|Имя эмблемы        |Файл изображения  |Цвет текста | Цвет фона |
|------------------|------------|---------- |--------|
|Связь     |[Связь PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|Критическое мысли |[Критический анализ PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|Амино         |[PNG-png](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|Эмомития           |[Эмопсийский PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|Цель      |[Goal в PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|Мотивация        |[Мотивация PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|Сохраняемость       |[Сохранение PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|Соблюдение           |[Соблюдение PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|Ответственность    |[PNG с ответственностью](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|Самосознание    |[Самосознание PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|Самоуправление   |[Самостоятельное управление PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Задумка    |[Продуманность PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
