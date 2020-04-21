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
description: В этой статье представлены общие требования к поддержке комнат Microsoft Teams.
ms.openlocfilehash: 2496fcb1af7d85a3d1c3ba755a2431aff40d5a70
ms.sourcegitcommit: df4dde0fe6ce9e26cb4b3da4e4b878538d31decc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/15/2020
ms.locfileid: "43521605"
---
# <a name="microsoft-teams-rooms-requirements"></a>Требования к комнатам Microsoft Teams

Комнаты Microsoft Teams меняют размер, используя множество сертифицированных периферийных аудио и видео устройств, в зависимости от размера и использования комнаты. Выбрав основное устройство и консоль, вместе с микрофоном, динамиками, камерами и экранами, подходящими для пространства, можно развернуть комнаты Microsoft Teams до любого размера, начиная с небольшой переговорной до огромных залов для конференций и заседаний.  Полный набор доступных сертифицированных периферийных аудио и видео устройств, которые можно использовать для настройки комнаты, см. в статье [Демонстрация устройств](https://products.office.com/microsoft-teams/across-devices).

В этой статье представлены общие требования к развертыванию и конфигурации устройств для поддержки комнат Microsoft Teams.

Развертывание включает в себя создание учетной записи, как описано в статье [Развертывание комнаты Microsoft Teams](rooms-deploy.md) и настройку консолей собраний, как указано в статье [Настройка консоли Комнат Microsoft Teams](console.md).

Также см. статью:

- [Лицензирование надстройки Skype для бизнеса](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Параметры лицензии с учетом плана: Комнаты Microsoft Teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Комнаты Microsoft Teams подключаются к Microsoft Teams, Skype для бизнеса Server 2019, Skype для бизнеса Server 2015 или Skype для бизнеса Online, и присоединяются к собраниям любой из этих служб.
>
> Такие приложения, как Lync Server 2013, не поддерживаются в Комнатах Microsoft Teams. Комнаты Microsoft Teams не поддерживаются в Office 365, предоставляемой 21Vianet, или в среде GCC-High или DoD.
>
> Если вы используете локальный Exchange server, в комнатах Microsoft Teams необходимо использовать Exchange Server 2013 SP1 или более позднюю версию.

## <a name="hardware-requirements"></a>Требования к оборудованию
В развертывание оборудования входит выбор системы комнат Microsoft Teams, вместе с сертифицированными периферийными аудио и видео устройствами, и кабели для объединения этих устройств.  Эти параметры описаны ниже.

**Поддерживаемые системы комнат Microsoft Teams**

Все текущие устройства и пакеты комнат Microsoft Teams можно найти в статье [Демонстрация продуктов систем комнат](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=).

  |Консоль|Процессор|ОЗУ|Диск|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 ГБ |128 ГБ |
  |[Crestron Flex UC- B130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 ГБ |128 ГБ |
  |[Crestron Flex UC-B140-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 ГБ |128 ГБ |
  |[Crestron Flex UC-M150-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T) + [CCS-UCA-MIC](https://www.crestron.com/ru-RU/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 ГБ |128 ГБ |
  [Crestron Flex UC-B160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 ГБ |128 ГБ|
  |[Crestron Flex UC-C160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 ГБ|128 ГБ|
  |[HP Elite Slice для Meeting Rooms G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 ГБ |128 ГБ |
  |[HP Elite Slice G2 с готовым аудио для комнат Microsoft Teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 ГБ |128 ГБ |
  |[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8 ГБ |128 ГБ |
  |[Logitech Tap](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 ГБ |128 ГБ |
  |[Yealink MVC800](https://www.yealink.com/products_125.html)|Core i5|8 ГБ|128 ГБ|
  |[Yealink MVC500](https://www.yealink.com/products_126.html)|Core i5|8 ГБ |128 ГБ |
  |[Yealink MVC300](https://www.yealink.com/products_154.html)|Core i5|8 ГБ |128 ГБ |
  |[Yealink MVC900](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8 ГБ|128 ГБ|
  ||||||

> [!NOTE]
> - Процессоры Core M3 не поддерживаются. 
> - Вам потребуется USB-накопитель емкостью до 32 ГБ или более, настроенный как загрузочный установочный носитель Windows для ОС Windows 10 Корпоративная.

**Поддерживаемые планшеты Surface Pro для док-систем**

  |Планшет|Процессор|ОЗУ|Диск|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 ГБ или 8 ГБ |128 ГБ или больше |
  |Surface Pro </br>(fifth Gen) |Core i5 |8 ГБ или 4 ГБ |128 ГБ или больше |
  |Surface Pro 4 |Core i5 |8 ГБ или 4 ГБ |128 ГБ или больше |

- Устройства Surface Pro требуют наличие одной из следующих док-станций для установки планшета в конференц-зале.

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>Сертифицированные версии встроенного ПО для периферийных аудио и видео USB устройств.

Устройства можно найти в статьях [Демонстрация аксессуаров систем комнаты](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=) и [https://office.com/teamsdevices](https://office.com/teamsdevices).

|Периферийные устройства комнат Microsoft Teams|Сертифицированная версия встроенного ПО | Камера поддерживающая использование содержимого|
|:--- |:--- | :--- |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  |  |
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |Звук — 1.0.172 <br/> Видео— 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Камера Poly Eagle Eye Cube](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml)   |1.2.15   |
|[Sennheiser SP30](https://en-us.sennheiser.com/sp-30)   |2.1.52  |
|[Sennheiser SP30T](https://en-us.sennheiser.com/sp-30)  |3.2.63  |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/ru-RU/products/mixers/p300)+</br></br> [Shure MXA 310 Table Array Mic ](https://www.shure.com/ru-RU/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/ru-RU/products/mixers/p300) + </br></br> [Shure MXA 910 with Intellimix Ceiling Array Mic](https://www.shure.com/ru-RU/products/microphones/mxa910) | 4.1|
|[Biamp Tesira Fore AVB VT4 Fixed audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Sennheiser TeamConnect Ceiling 2 Microphone](https://en-us.sennheiser.com/tcc2)+ &Dagger;</br></br> [Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP: 3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT: 3.12.0.15 |
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink Amplifier +</br> Sennheiser TCC2 Ceiling Microphone + </br> Bose EdgeMax EM180 Ceiling Speaker](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
||||||

&Dagger; Для этого набора можно использовать интерфейс Dante или сетевой коммутатор, рекомендованный Biamp/Sennheiser для этого пакета.

#### <a name="usb-extenders"></a>USB расширители

- USB-порты док-станций планшетов совместимы с USB 3.0. Использование USB расширителей версии 2.x. ограничит скорость работы. Такие расширители не рекомендуются для периферийных устройств USB 3.0.
- Расширитель должен соответствовать спецификациям USB 2.0 и более поздних версий.
  - Док-станции планшета поддерживают хотя бы две стадии внешнего расширения USB-концентратора. При подключении более двух USB-концентраторов в ряд, уточните у производителя док-станции, поддерживает ли она подключение ряда.
  - Проводное подключение GbE в комнате. Кабель Ethernet соответствующей длины.
  - До двух 1080-p дисплеев с подключением HDMI. Кабели HDMI соответствующей длины.

> [!NOTE]
> Бытовой телевизор, используемый в качестве центрального дисплея, должен поддерживать функцию управления бытовой электронной техникой (CEC) стандарта HDMI для автоматического переключения на активный источник видеосигнала из режима ожидания. Эту функцию поддерживают не все телевизоры.
>
> Комнаты Microsoft Teams не используют клавиатуру. При необходимости администратор может использовать экранную клавиатуру. USB-клавиатура или мышь потребуются при создании образа устройства комнат Microsoft Teams.

В таблицах ниже представлены рекомендации в отношении периферийных устройств в соответствии с размером комнаты:

**Сертифицированные периферийные аудио-устройства комнат Microsoft Teams**

|Тип комнаты|Количество людей|Рекомендованное максимальное расстояние от микрофона до выступающего|Устройство для максимального размера комнаты|Комментарии|
|:-----|:-----|:-----|:-----|:-----|
|**Фокус** <br/> 10' x 9'   |2–4  |1.5 м  |Logitech Connect  |Устройство Logitech Connect оснащено камерой, поэтому его следует размещать в стороне от стола, за которым проходит собрание, а не в его центре. |
|**Маленькое** <br/> 16' x 16'  |4–6  |2.0 м  |Jabra 510 <br/> Sennheiser SP20  |Для комнат большего размера громкости воспроизведения может быть недостаточно.  |
|**Среднее** <br/> 18' x 20'  |6–12  |2.4 м  |Jabra 710 <br/> Jabra 810 <br/> Logitech MeetUp <br/> Logitech Group <br/> Polycom Trio <br/> Polycom CX5100  <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS  |Устройство Logitech MeetUp оснащено камерой, поэтому его следует размещать в стороне от стола, за которым проходит собрание, а не в его центре. <br/> В помещениях с длинным прямоугольным столом или столом в форме буквы "U" лучше использовать спутниковые микрофоны. <br/> В конфигурации последовательной цепочки необходимо использовать пакет SP 220 MS.  |
|**Большое** <br/> 15' x 32'  |12–16  |3 м <br/> Это расстояние также распространяется на область, охватываемую каждым подключенным микрофоном.  |Logitech Group + спутниковые микрофоны <br/> Polycom Trio+ спутниковые микрофоны <br/> Polycom CX5100 + спутниковые микрофоны <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS + спутниковые микрофоны  |Все перечисленные звуковые устройства поддерживают дополнительные параметры спутникового микрофона. <br/> Устройство CX5100 оснащено встроенной камерой с круговым обзором, что позволяет размещать его в центре стола. <br/> В конфигурации последовательной цепочки необходимо использовать пакет SP 220 MS.  |

**Сертифицированные периферийные видео-устройства комнат Microsoft Teams**

|Тип комнаты|Количество людей|Устройства (в зависимости от размера помещения)|Комментарии|
|:-----|:-----|:-----|:-----|
|**Фокус** <br/> 10' x 9'  |2–4  |Logitech Connect <br/> Logitech MeetUp <br/> Polycom CX5100  ||
|**Маленькое** <br/> 16' x 16'  |4–6  |Logitech C930e <br/> Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  |Logitech PTZ Pro вместе с Logitech Group  |
|**Среднее** <br/> 18' x 20'  |6–12  |Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||
|**Большое** <br/> 15' x 32'  |12–16  |Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||

 > [!NOTE]
 > Разрешение экрана в передней части зала не должно превышать 1920x1080p.

## <a name="required-software-downloads"></a>Необходимое программное обеспечение

Чтобы создать образ комнаты Microsoft Teams, следуйте инструкциям в статье [Настройка консоли комнат Microsoft Teams](console.md). Инструкции помогут скачать необходимое для установки программное обеспечение.

> [!NOTE]
> ИТ-специалистам потребуется доступ к ISO-файлам ОС Windows 10 Корпоративная, в рамках соглашения о корпоративном лицензировании.

[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) — необязательный пакет, который можно использовать для подготовки учетных записей комнат Microsoft Teams.

## <a name="see-also"></a>См. также

[Обзор всех пакетов](https://products.office.com/microsoft-teams/across-devices/devices)

[Планирование комнат Microsoft Teams](rooms-plan.md)

[Развертывание комнат Microsoft Teams](rooms-deploy.md)

[Настройка консоли комнат Microsoft Teams](console.md)

[Управление комнатами Microsoft Teams](rooms-manage.md)

[Лицензирование надстройки Skype для бизнеса](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
