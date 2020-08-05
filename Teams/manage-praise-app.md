---
title: Управление приложением благодарность в центре администрирования Teams
author: CaitlynZawideh
ms.author: t-cazaw
manager: serdars
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: Сведения о параметрах администрирования в приложении благодарность в центре администрирования Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: deff9fca7cf1097399079482dc4667052a7be537
ms.sourcegitcommit: 5bcc25fb20ed72bac02bc78e40b591e67eb58686
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "46564080"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Управление приложением благодарность в центре администрирования Microsoft Teams

Приложение благодарность в Microsoft Teams помогает пользователям продемонстрировать повышение стоимости участникам своей организации или занятия. Выбрав один из наборов индикаторов, и вы сможете создавать собственные эмблемы, благодарность разработана для того, чтобы помочь вам понять усилия, которые переходят в широкий спектр работ, выполняемых пользователями Teams, от преподавателей до первой строки работников.

Администраторы могут управлять тем, какие эмблемы доступны для своей организации в центре администрирования Teams. На панели навигации слева выберите пункт **приложения teams > Управление приложениями**. Откройте благодарность в [каталоге приложений клиента](https://docs.microsoft.com/microsoftteams/manage-apps#view-apps-in-your-tenant-app-catalog)и перейдите в раздел " **Параметры**".

## <a name="use-built-in-badge-sets"></a>Использование встроенных наборов индикаторов

Встроенные наборы — это наборы индикаторов, разработанные корпорацией Майкрософт для приложения благодарность. Эти наборы нельзя редактировать с помощью администраторов. Установленный по умолчанию индикатор уже включен и доступен в приложении благодарность. Чтобы изменить доступность набора по умолчанию или любых наборов индикаторов, включите или отключите соответствующий переключатель. 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>Эмблемы по умолчанию

Установленный по умолчанию индикатор используется для того, чтобы пользователи Teams могли распознать их одноранговые элементы для работы над ними и более поздних версий.

![Предварительный просмотр набора значков по умолчанию](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>Эмоциональнаяные логотипы для образовательных учреждений и социальных сетей

Преподаватели могут распознавать отдельных учащихся в социальных и эмоциональная учебных материалах, а также поведений с помощью эмблем, иллюстрирующих эти идеи.

![Предварительный просмотр социальных и эмоциональнаяных логотипов для образовательных учреждений](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>Создание собственных эмблем

Установите переключатель **в положение** вкл., а затем выберите **создать настраиваемый индикатор**. На боковой панели вы можете создать настраиваемый индикатор.

1. Введите название эмблемы. Это имя, которое будет отображаться на индикаторе при отправке пользователями благодарность.

2. Настройка цветов индикаторов. Чтобы задать цвета текста и фона для эмблемы, нужно ввести их в виде шестнадцатеричных (шестнадцатеричных) значений.

   > [!TIP]
   > Если вы не знакомы с шестнадцатеричными значениями, в этой статье описано [Краткое введение](#hex-colors-intro) , в котором показано, как использовать их.

3. Добавьте изображение индикатора. Допустимый тип файла. Формат. Файл должен быть менее 25kb.
![Индикатор с надписью "фон", "текст" и "изображение"](media/praise-app-badge-fields.png)

4. Локализовать название эмблемы: в разделе **локализованные названия индикаторов**нажмите кнопку **Добавить**. Выберите нужный язык из раскрывающегося списка. Затем введите название эмблемы на определенном языке.

5. Исключите эмблему из определенных языков: в разделе **исключить эмблему из этих языков**нажмите кнопку **Добавить**. Выберите национальные настройки, которые вы хотите исключить из раскрывающегося списка.

6. Нажмите кнопку **Применить**. Теперь новая эмблема появится в таблице Custom "эмблемы".

> [!NOTE]
> Если пропускаются шаги 4 и 5, индикатор будет на языке по умолчанию для всех языков.
>
> Завершив внесение изменений в выбор значка, убедитесь, что выбран параметр **Отправить**. Для того чтобы эти изменения были доступны в вашей организации, может пройти несколько часов.

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>Определение цветов с использованием шестнадцатеричных значений

Шестнадцатеричные значения цвета — это строки из шести шестнадцатеричных цифр, представляющих интенсивность красного (RR), зеленого (GG) и синего (BB) определенного цвета в масштабе от 00 до FF. При одновременном помещении значений всех трех цветов получается шестнадцатеричное значение: #RRGGBB

Например, шестнадцатеричным значением для красного цвета является #FF0000, так как значение Red задано на максимально возможном значении, FF и зеленого и синего устанавливаются по меньшей мере равной 00.

Чтобы узнать другие цвета и их шестнадцатеричные значения, изучите [средство выбора цвета Bing](https://www.bing.com/search?q=color+picker).

Ниже приведен список примеров цветов, которые помогут вам приступить к работе.

|Цвет  |Шестнадцатеричное значение|
|-------|---------|
|![цвет #FF6666 Hex](media/hexColor1.png)|  #FF6666   |
|![цвет #7FFFD4 Hex](media/hexColor2.png)|  #7FFFD4   |
|![цвет #FF75F0 Hex](media/hexColor3.png)|  #FF75F0   |
|![цвет #00BFFF Hex](media/hexColor4.png)|  #00BFFF   |
|![цвет #800080 Hex](media/hexColor5.png)|  #800080   |
|![цвет #000000 Hex](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>Советы и рекомендации по созданию настраиваемых индикаторов

**Отправляйте сразу все свои эмблемы.** Так как для обработки новых эмблем потребуется добавить в нее все пользовательские эмблемы, прежде чем отправлять их.

**При выборе цветов имейте в виду специальные возможности.** Некоторые цвета работают лучше друг от друга.  Чтобы облегчить чтение названия индикатора, создайте контрастность между текстом и цветами фона. Например, если вы выбрали темный цвет фона, выберите светлый цвет текста.

**При выборе изображения следует учитывать размеры индикаторов.** Для наилучшего качества мы рекомендуем загрузить файл изображения в 216x216 точках. Избегайте растяжения и искажения изображения в соответствии с этими размерами.

**Если изображение индикатора не прямоугольное, сделайте изображение прозрачным.** Это необходимо сделать перед отправкой файла изображения в благодарность.

![Left: индикатор с непрозрачным изображением, справа: индикатор с прозрачным изображением](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>Настройка значков для ресурсов

Встроенные наборы индикаторов изменить нельзя, поэтому при включенном встроенном наборе все эмблемы в наборе добавляются в приложение благодарность. Если вы хотите добавить определенные эмблемы из встроенного множества и не развлекать другие, воссоздайте эмблемы, которые вы хотите использовать в качестве настраиваемых индикаторов. Вы можете загрузить изображение индикатора и найти текст и цвета фона индикаторов из встроенных наборов в приведенных ниже таблицах.

### <a name="default-badges-assets"></a>Ресурсы по умолчанию

</br>

|Название эмблемы     |Файл изображения  |Цвет текста | Цвет фона |
|---------------|------------|---------- |--------|
|Достижение       |[Формат PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|Замечательно        |[Awesome PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png>Awesome.PNG)</a>|#8283B2    |#D1EFF2|
|Coach          |[Формат PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Крайне        |[Рекомендуется в формате PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|Creative       |[Художественный формат PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|Иерархическ      |[Включительно PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|Сердечка     |[Формат сердца в формате PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|Руководства     |[По лидеру в формате PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership.pn)|#419098    |#D2EAEC|
|Optimism       |[Optimism PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|Проблемы с поиском решения |[Проблема с поиском в формате PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|Командный плеер    |[PNG-проигрыватель группы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|Спасибо      |[Спасибо, PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>Эмоциональнаяные логотипы для учебных заведений

</br>

|Название эмблемы        |Файл изображения  |Цвет текста | Цвет фона |
|------------------|------------|---------- |--------|
|Обращений     |[Связь в формате PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|Критический мышления |[Критический обдумываниный формат PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|Curiosity         |[Curiosity PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|Empathy           |[Empathy PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|Достижение цели      |[Цель использования PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|Мотиваци        |[Мотивация в формате PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|Сохранение       |[Сохраняемый PNG-формат](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|Операция           |[Учитывать формат PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|Обязанности    |[Ответственность в формате PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|Самостоятельное распознавание    |[Поддержка самоконтроля в формате PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|Самостоятельное управление   |[Файлы в формате PNG для автоматического управления](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Продуманность    |[ФОРМАТ "продуманная"](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
