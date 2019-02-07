---
title: Системы комнат Skype версии 2 — требования
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
description: В этой статье приведены требования для поддержки систем комнаты Скайп версии 2.
ms.openlocfilehash: d54ace878e45344075a166c257efa18aa150b0e3
ms.sourcegitcommit: d400c8f83a2325c4a8bbb963ddad685a346bc4d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "29760608"
---
# <a name="skype-room-systems-v2-requirements"></a>Системы комнат Skype версии 2 — требования

В этой статье приведены требования для поддержки систем комнаты Скайп версии 2. 

Развертывание включает создание учетной записи, как описано в разделе [Развертывание системы комнаты Скайп версии 2](../../deploy/deploy-clients/room-systems-v2.md) и о настройке консоли собрания, как описано в статье [Настройка консоли систем комнаты Скайп версии 2](../../deploy/deploy-clients/console.md). 

Может также потребоваться обращайтесь к:

- [Скайп для лицензирования дополнительный компонент Business](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Назначение лицензий на основе плана параметры: систем комнаты Скайп версии 2](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Версии 2 Скайп комнаты систем предназначен для использования с Скайп для Business Server 2019, Скайп Business Server 2015, группами Майкрософт или Скайп для бизнеса в Интернет. <br><br>Более ранних платформы, как Lync Server 2013 не требуются для работы с системами комнаты Скайп версии 2.

> [!NOTE]
> При использовании Exchange server на prem Скайп комнаты систем v2 необходимо использовать Exchange Server 2013 с пакетом обновления 1 или более поздней версии.

## <a name="hardware-requirements"></a>Требования к оборудованию

Версии 2 Скайп комнаты систем можно масштабировать для размеров другой комнате через стандартные в зависимости от периферийных аудио- и видеоконференций. Оборудование, указанные в этой статье поддерживает режимы собрания Скайп и рабочих групп.  Аудио- и видеоконференций периферийных подключиться к версии 2 Скайп комнаты систем через подключение к USB или HDMI закрепления устройства. Кроме того, вам потребуется следующее.

- 32 ГБ или больше дисков USB необходимо настроить как загрузочного установочного носителя Windows для Windows 10 Enterprise. 

- Один из следующих планшетные ПК и консоли:

**Поддерживаемые планшетные ПК**

|Планшет|Процессор|ОЗУ|Диск|
|:-----|:-----|:-----|:-----|
|Surface Pro 6  |Основные i5 (8350U)  |16 ГБ или 8 ГБ  | 128 ГБ или больше  |
|Surface Pro 6  |Core i7 (8650U) |16 ГБ или 8 ГБ  |128 ГБ или больше  |
|Surface Pro (2017)  |Основные i5  |8 ГБ или 4 ГБ  |128 ГБ или больше  |
|Surface Pro 4       |Основные i5  |8 ГБ или 4 ГБ  |128 ГБ или больше  |

> [!NOTE]
> M3 ядрами процессора, не поддерживаются.

**Поддерживаемые консоли**

|консоль;|Процессор|ОЗУ|Диск|
|:-----|:-----|:-----|:-----|
|[Сервер-концентратор ThinkSmart Lenovo 500](https://www3.lenovo.com/us/en/hub500) |Основные i5  |8 ГБ  |128 ГБ  |  
|[HP интеллектуальных Slice к собранию G2 комнат](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Основные i5  |8 ГБ  |128 ГБ  |  

- Один из следующих параметров закрепления станции для обеспечения безопасности планшетном ПК к собранию комнаты в таблице. 

  - [Logitech SmartDock](https://partnersolutions.skypeforbusiness.com/solutionscatalog/all/logitech-smart-dock)

  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )

  - [Polycom MSR серии](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)



**Сертифицированный встроенное периферийных устройств USB аудио- и видеоконференций**

|Периферийных систем комнаты Скайп версии 2|Версия микропрограммы сертифицированный для систем комнаты Скайп версии 2|
|:-----|:-----|
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> |v240|
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |Аудио - 1.0.172  <br/> Видео - 1.0.156  <br/> |
|[Logitech ConferenceCam Connect](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Logitech Group](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> |  1.1.219 <br/> |
|[PTZ Logitech специалистов 2](http://www.logitech.com/en-us/product/conferencecam-ptz-pro2) <br/> |
|[Polycom RealPresence Trio](http://www.polycom.com/voice-conferencing-solutions/conference-phones/realpresence-trio.mdl) <br/> |5.4.4.7511  <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0.70232 <br/> |
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[1000 Yamaha YVC](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100c  <br/> |

- **Расширения USB**:

  - Порты USB на планшетном ПК фиксирует элемент управления, совместимые 3.0 USB. Расширитель 2.x USB, можно использовать, но это так будет ограничивают скорость 2.x USB на другой стороне и выполняя это не рекомендуется для периферийных USB 3.0.

  - Расширитель должны соответствовать USB 2.0 или более новое спецификаций.

  - Фиксирует элемент управления планшетного ПК поддерживает по крайней мере два этапа внешних расширений сервера-концентратора USB. Если требуется подключаться с более чем двух концентраторов USB в серии, необходимо будет обратитесь к производителю закрепления для подтверждения это так поддерживается.

- Проводное подключение GbE в помещении. Кабель Ethernet соответствующей длины.

- До двух отображает 1080p с подключениями HDMI. Кабели HDMI соответствующей длины.

    > [!NOTE]
    > Бытовой телевизор, используемый в качестве центрального дисплея, должен поддерживать функцию управления бытовой электронной техникой (CEC) стандарта HDMI для автоматического переключения на активный источник видеосигнала из режима ожидания. Эту функцию поддерживают не все телевизоры. 

> [!NOTE]
> Версии 2 Скайп комнаты систем не использует клавиатуру. При необходимости администратор может использовать экранную клавиатуру. USB-клавиатуры или мыши требуется указать при обработки изображений устройства версии 2 Скайп комнаты систем. 

В следующих таблицах приводятся рекомендации по для устройств на размер комнаты основе:

**Сертифицированный аудиоустройств v2 систем Скайп комнаты**

|Тип комнаты|Количество людей|Рекомендованное максимальное расстояние от микрофона до выступающего|Устройство для максимального размера комнаты|Комментарии|
|:-----|:-----|:-----|:-----|:-----|
|**Фокус-комната** <br/> 10' x 9'  <br/> |2 – 4  <br/> |1.5m   <br/> |Logitech Connect  <br/> |Относятся следующие устройства подключения Logitech камера, должен быть установлен на передней части комнаты (не Центр таблицы) для записи локального участников.  <br/> |
|**Небольшая** <br/> 16' x 16'  <br/> |4-6  <br/> |2.0m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |Для комнат большего размера громкости воспроизведения может быть недостаточно.  <br/> |
|**Средняя** <br/> 18' x 20'  <br/> |6-12  <br/> |2.4m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Logitech Group  <br/> Polycom Trio  <br/> Polycom CX5100   <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000 мс  <br/> |Logitech MeetUp включает в себя камера, он должен быть установлен на передней части комнаты (не Центр таблицы для записи локального участников).  <br/> В общем случае комнат с таблицами длинный прямоугольный или u образный может преимущества Дополнительные сопутствующие микрофонов.  <br/> Устройство SP 220 MS должно подключаться последовательно.  <br/> |
|**Большая** <br/> 15' x 32 °  <br/> |12-16  <br/> |3 м  <br/> Здесь также учитывается расстояние до каждого дополнительного микрофона, подключенного к звуковому устройству.   <br/> |Группа Logitech + вспомогательных микрофона  <br/> Polycom Trio + вспомогательных микрофона  <br/> Polycom CX5100 + вспомогательных микрофона  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000 мс + вспомогательных микрофона  <br/> |Все звуковые устройства, указанные в этой строке, поддерживают подключение дополнительных микрофонов.  <br/> Устройство CX5100 оснащено встроенной камерой с круговым обзором, что позволяет размещать его в центре стола.  <br/> Устройство SP 220 MS должно подключаться последовательно.  <br/> |

**Сертифицированный видео периферийных v2 систем Скайп комнаты**

|Тип комнаты|Количество людей|Устройство по размеру оптимальную комнаты|Комментарии|
|:-----|:-----|:-----|:-----|
|**Фокус-комната** <br/> 10' x 9'  <br/> |2 – 4  <br/> |Logitech Connect  <br/> Logitech MeetUp  <br/> Polycom CX5100   <br/> ||
|**Небольшая** <br/> 16' x 16'  <br/> |4-6  <br/> |Logitech C930e  <br/> Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> |Logitech PTZ специалистов обычно входит в состав группы Logitech  <br/> |
|**Средний уровень** <br/> 18' x 20'  <br/> |6-12  <br/> |Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||
|**Большая** <br/> 15' x 32 °  <br/> |12-16  <br/> |Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||

 > [!NOTE]
 > Передней части разрешение экрана комнаты должен иметь значение не более 1920x1080p.

## <a name="required-software-downloads"></a>Необходимое программное обеспечение

Для создания образа версии 2 Скайп комнаты систем, следуйте инструкциям в статье [Настройка консоли систем комнаты Скайп версии 2](../../deploy/deploy-clients/console.md). Эти инструкции поможет выполнить загрузку все необходимое программное обеспечение для процесса установки. 

> [!NOTE]
> ИТ-специалистов требуется доступ к Windows 10 Enterprise ISO файлов с помощью их соглашением о корпоративном лицензировании.

Кроме того можно копию [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), часто используется для подготовки учетных записей систем комнаты Скайп версии 2.

## <a name="see-also"></a>См. также

[Plan for Skype Room Systems v2](skype-room-systems-v2-0.md)

[Развертывание Систем комнат Skype версии 2](../../deploy/deploy-clients/room-systems-v2.md)

[Настройка консоли для Систем комнат Skype версии 2](../../deploy/deploy-clients/console.md)

[Управление Системами комнат Skype версии 2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[Скайп для лицензирования дополнительный компонент Business](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
