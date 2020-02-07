---
title: Требования к комнатам Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: В этой статье приводятся сведения о требованиях для поддержки комнат Microsoft Teams.
ms.openlocfilehash: 8a62a883d9e839d58f6e627d30422d867221e7e1
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825957"
---
# <a name="microsoft-teams-rooms-requirements"></a>Требования к комнатам Microsoft Teams

Комнаты Microsoft Teams масштабируются до разных размеров комнаты с помощью широкого спектра сертифицированных звуковых и видеоустройств в зависимости от размера и использования комнаты. Выбирая подходящее базовое устройство и консоль в сочетании с микрофонами, динамиками, камерами и выпусками, подходящими для сферы, вы можете развернуть комнаты Microsoft Teams в пробелах любого размера из очень мелких худдленых пробелов до очень больших пространств для конференц-связи. и боардрумс.  Полный набор всех доступных сертифицированных звуковых и видеоаппаратных устройств, которые можно использовать для настройки комнаты, находится на странице [демонстрация устройства](https://products.office.com/microsoft-teams/across-devices).

В этой статье приведены сведения о требованиях к развертыванию и конфигурации устройств для поддержки комнат Microsoft Teams.

Развертывание включает создание учетных записей, как описано в разделе [развертывание комнат Microsoft Teams](rooms-deploy.md) и настройка консолей собраний, как описано в разделе [Настройка консоли Microsoft Teams](console.md).

Кроме того, ознакомьтесь с разделами:

- [Лицензирование надстройки Skype для бизнеса](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Варианты лицензирования, основанные на вашем плане: комнаты Microsoft Teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Комнаты Microsoft Teams Войдите в Microsoft Teams, Skype для бизнеса Server 2019, Skype для бизнеса Server 2015 или Skype для бизнеса Online и могут присоединиться к собраниям, размещенным в любой из этих служб.
>
> Комнаты в Microsoft Teams не поддерживаются в более ранних платформах, таких как Lync Server 2013. Комнаты Microsoft Teams не поддерживаются в Office 365, предоставляемой 21Vianet, или в средах с функцией GCC-High или DoD.
>
> Если у вас есть локальный сервер Exchange Server, в помещениях Microsoft Teams требуется использование Exchange Server 2013 с пакетом обновления 1 (SP1) или более поздней версии.

## <a name="hardware-requirements"></a>Требования к оборудованию
Аппаратное развертывание включает в себя набор из системы комнаты Microsoft Teams, в сочетании с сертифицированными аудио-и видеосоединениями, а также устройство для совместной интеграции этих устройств.  Эти параметры описаны здесь.

**Поддерживаемые системы комнат Microsoft Teams**

Все текущие устройства и наборы комнат Microsoft Teams доступны в [демонстрации продуктов для системы помещений](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=).

  |консоль;|Воздуш|ДОСТУПНОЙ|Диск|
  |:-----|:-----|:-----|:-----|
  |[Крестрон Flex UC-M130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Основные i5|8 ГБ |128 ГБ |
  |[Крестрон Flex UC-B130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Основные i5|8 ГБ |128 ГБ |
  |[Крестрон Flex UC-B140-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Основные i5|8 ГБ |128 ГБ |
  |[Крестрон Flex UC-M150-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T) + [CCS-ука-MIC](https://www.crestron.com/en-US/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 ГБ |128 ГБ |
  [Крестрон Flex UC-B160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 ГБ |128 ГБ|
  |[Крестрон Flex UC-C160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 ГБ|128 ГБ|
  |[HP топовый Slice для комнат собраний G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Основные i5 |8 ГБ |128 ГБ |
  |[HP топовый сектор G2, готовая к работе с комнатами Microsoft Teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Основные i5 |8 ГБ |128 ГБ |
  |[Адаптер Lenovo Синксмарт Hub 500](https://www3.lenovo.com/us/en/hub500) |Основные i5 |8 ГБ |128 ГБ |
  |[Нажмите кнопку Logitech](https://www.logitech.com/product/microsoft-rooms)|Основные i5|8 ГБ |128 ГБ |
  |[Yealink MVC800](https://www.yealink.com/products_125.html)|Основные i5|8 ГБ|128 ГБ|
  |[Yealink MVC500](https://www.yealink.com/products_126.html)|Основные i5|8 ГБ |128 ГБ |
  |[Yealink MVC300](https://www.yealink.com/products_154.html)|Основные i5|8 ГБ |128 ГБ |
  ||||||

> [!NOTE]
> - Базовые процессоры M3 не поддерживаются.
> - Вам понадобится USB-накопитель емкостью 32 ГБ или больше, настроенный как загружаемый установочный носитель Windows для Windows 10 Корпоративная.

**Поддерживаемые планшеты Surface Pro для системы закрепляемого типа**

  |Планшете|Воздуш|ДОСТУПНОЙ|Диск|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Основные i5 |16 ГБ или 8 ГБ |128 ГБ или больше |
  |Surface Pro </br>(пятое Gen) |Основные i5 |8 ГБ или 4 ГБ |128 ГБ или больше |
  |Surface Pro 4 |Основные i5 |8 ГБ или 4 ГБ |128 ГБ или больше |

- Один из следующих вариантов стыковочных станций для обеспечения защиты планшета в таблице комнат для собраний.

  - [Logitech Смартдокк](https://www.logitech.com/product/smartdock)
  - [Набор исправлений крестрон](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Серия Polycom MSR](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>Сертифицированные версии микропрограмм для звуковых и видеоустройств USB

Эти устройства доступны на странице " [Обзор продуктов](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=) " в комнате и [https://office.com/teamsdevices](https://office.com/teamsdevices).

|Периферийные устройства комнат Microsoft Teams|Сертифицированная версия встроенного по | Камера поддерживает использование содержимого камерой|
|:--- |:--- | :--- |
|[Крестрон Худдли IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | &#x2714; |
|[Logitech Брио](https://www.logitech.com/product/brio)   |V 2.2.50| &#x2714; |
|[Logitech 930E](http://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech вечеринку](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech обсудим](http://www.logitech.com/product/meetup-conferencecam)   |Звук — 1.0.172 <br/> Видео — 1.0.156  |
|[Logitech Конференцекам Connect](http://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Группа Logitech](http://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech ПТЗ Pro](http://www.logitech.com/product/conferencecam-ptz-pro)   |  1.1.219   |
|[Logitech ПТЗ Pro 2](http://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Камера Куба поли Еагле глаз](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom Еаглие IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl)   |1.0.0   |
|[Polycom CX5100 ](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Директор Polycom Еагле глаз II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio Саундбар](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Polycom тройкой 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[Сеннхеисер SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml)   |1.2.15   |
|[Сеннхеисер SP30](https://en-us.sennheiser.com/sp-30)   |2.1.52  |
|[Сеннхеисер SP30T](https://en-us.sennheiser.com/sp-30)  |3.2.63  |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Спикерфон Yamaha ИВК-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Процессор Шуре Интеллимикс P300 Audio для конференций](https://www.shure.com/en-US/products/mixers/p300)+</br></br> [Микрофона массива Шуре МКСА 310](https://www.shure.com/en-US/products/microphones/mxa310) | 4,1 |
|[Процессор Шуре Интеллимикс P300 Audio Конференинг](https://www.shure.com/en-US/products/mixers/p300) + </br></br> [Шуре МКСА 910 с микрофонами Интеллимикс CEILING](https://www.shure.com/en-US/products/microphones/mxa910) | 4,1|
|[Биамп Тесира переднего плана АВБ VT4 фиксированного схемы аудио.](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Сеннхеисер Теамконнект 2 – микрофона](https://en-us.sennheiser.com/tcc2)+ &Dagger;</br></br> [ТЕСИРА ex-УБТ](https://www.biamp.com/products/tesira/tesira-expanders)&Dagger; |  Биамп DSP: 3.12.0.15  </br></br> TCC2:1.3.3 </br></br> EX-УБТ: 3.12.0.15 |  |
||||||

&Dagger;Пользователи могут выбрать либо интерфейс Данте, либо сетевой коммутатор, рекомендованный Биамп/Сеннхеисер для этого набора.

#### <a name="usb-extenders"></a>Медиаприставок USB

- Порты USB на стыковочных планшетах совместимы с USB 3,0. Вы можете использовать устройство с интерфейсом USB 2. x, но при этом вы сможете сделать так, чтобы вы использовали USB 2. x на дальнем краю. Для периферийных устройств USB 3,0 не рекомендуется использовать средства продления.
- Средство продления должно соблюсти спецификации USB 2,0 или более поздней версии.
  - Стыковочные планшеты поддерживают по крайней мере два этапа расширения внешнего USB-концентратора. Если вы подключаете более двух USB-концентраторов в серии, Узнайте у производителя подстыковочного устройства, чтобы убедиться, что они поддерживают подключение к ряду.
  - Проводное подключение к гигабитной GbE в комнате. Кабель Ethernet соответствующей длины.
  - До 2 1080-p дисплеев с подключением HDMI. Кабели HDMI для правильной длины.

> [!NOTE]
> Бытовой телевизор, используемый в качестве центрального дисплея, должен поддерживать функцию управления бытовой электронной техникой (CEC) стандарта HDMI для автоматического переключения на активный источник видеосигнала из режима ожидания. Эту функцию поддерживают не все телевизоры.
>
> Комнаты Microsoft Teams не используют клавиатуру. При необходимости администратор может использовать экранную клавиатуру. Клавиатура или мышь с интерфейсом USB потребуются при создании образа на устройстве Microsoft Teams.

В приведенных ниже таблицах приведены рекомендации по использованию периферийных устройств в зависимости от размера комнаты.

**Microsoft Teams — комнаты, сертифицированные звуковыми устройствами**

|Тип комнаты|Количество людей|Рекомендуемая максимальная дистанция между микрофоном и динамиком|Устройство для максимального размера комнаты|Комментарии|
|:-----|:-----|:-----|:-----|:-----|
|**Фокус-комната** <br/> 10 ' x 9 '   |2 – 4  |1,5 м  |Logitech Connect  |Устройства Logitech Connect включают камеру, которая должна располагаться на лицевой стороне комнаты (не в центре таблицы), чтобы захватывать местных участников собрания. |
|**Небольшая** <br/> 16 ' x 16 '  |4 – 6  |2,0 м  |Jabra 510 <br/> Sennheiser SP20  |Громкость воспроизведения может быть ограничена для больших комнат.  |
|**Средняя** <br/> 18 ' x 20 '  |6 – 12  |2,4 м  |Jabra 710 <br/> Jabra 810 <br/> Logitech обсудим <br/> Logitech Group <br/> Polycom Trio <br/> Polycom CX5100  <br/> Sennheiser SP 220 MS <br/> Спикерфон Yamaha ИВК-1000MS  |Камера Logitech обсудим включает камеру, поэтому ее нужно расположить на лицевой стороне комнаты (не в центре таблицы, в которой будут записаны локальные участники собрания). <br/> Как правило, в помещениях с длинными прямоугольными таблицами или на u-образной форме могут выиграть высоковыгодные Микрофоны спутниковой связи. <br/> Устройство SP 220 MS должно подключаться последовательно.  |
|**Большая** <br/> 15 ' x 32 '  |12 – 16  |3 м <br/> Эти расстояния также применимы к области, которая охватывается каждым подключенным микрофоном спутникового ТВ.  |Logitech Group + Спутниковое микрофонами <br/> Polycom тройкой + Спутниковое микрофонами <br/> Polycom CX5100 + Спутниковое микрофонами <br/> Sennheiser SP 220 MS <br/> Спикерфон Yamaha ИВК-1000MS + Спутниковое микрофонами  |Все звуковые устройства, указанные в этой строке, поддерживают подключение дополнительных микрофонов. <br/> CX5100 включает встроенную камеру с 360-градусами, позволяющую расположить устройство в центре таблицы. <br/> Устройство SP 220 MS должно подключаться последовательно.  |

**Карты Microsoft Teams, сертифицированные для видеооборудования**

|Тип комнаты|Количество людей|Устройство по оптимальному размеру комнаты|Комментарии|
|:-----|:-----|:-----|:-----|
|**Фокус-комната** <br/> 10 ' x 9 '  |2 – 4  |Logitech Connect <br/> Logitech обсудим <br/> Polycom CX5100   ||
|**Небольшая** <br/> 16 ' x 16 '  |4 – 6  |Logitech C930e <br/> Logitech обсудим <br/> Logitech Брио <br/> Logitech ПТЗ Pro <br/> Polycom MSR <br/> Polycom CX5100   |Технология Logitech ПТЗ Pro часто объединяется с группой Logitech  |
|**Средняя** <br/> 18 ' x 20 '  |6 – 12  |Logitech обсудим <br/> Logitech Брио <br/> Logitech ПТЗ Pro <br/> Polycom MSR <br/> Polycom CX5100   ||
|**Большая** <br/> 15 ' x 32 '  |12 – 16  |Logitech ПТЗ Pro <br/> Polycom MSR <br/> Polycom CX5100   ||

 > [!NOTE]
 > Для разрешения экрана в качестве внешнего дисплея должно быть установлено значение "не больше 1920x1080p".

## <a name="required-software-downloads"></a>Загрузка необходимого программного обеспечения

Чтобы создать собственный образ комнат Microsoft Teams, следуйте инструкциям в разделе [Настройка консоли Microsoft Teams](console.md). Эти инструкции помогут вам загрузить все программы, необходимые для установки.

> [!NOTE]
> ИТ-специалистам потребуется доступ к ISO-файлам Windows 10 для корпоративных лицензий по их корпоративному лицензионному соглашению.

[Скиперумпровисионингскрипт. ps1](https://go.microsoft.com/fwlink/?linkid=870105) — это необязательная Загрузка, которую можно использовать для подготовки учетных записей комнат Microsoft Teams.

## <a name="see-also"></a>См. также

[Просмотреть все пакеты](https://products.office.com/microsoft-teams/across-devices/devices)

[Планирование комнат Microsoft Teams](rooms-plan.md)

[Развертывание комнат Microsoft Teams](rooms-deploy.md)

[Настройка консоли Microsoft Teams](console.md)

[Управление приложением "Комнаты Microsoft Teams"](rooms-manage.md)

[Лицензирование надстройки Skype для бизнеса](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
