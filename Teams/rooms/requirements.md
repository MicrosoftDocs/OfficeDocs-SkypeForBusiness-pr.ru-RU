---
title: Требования к комнатам Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: Узнайте о требованиях к поддержке Комнаты Microsoft Teams, включая выбор соответствующего устройства, микрофонов, динамиков, камер и дисплеев.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4919dd2cad8cfe3df0270dad27b53a9b62467d36
ms.sourcegitcommit: 70c07a6b1be81681eec32a89872e2218d70c514d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2021
ms.locfileid: "58866391"
---
# <a name="microsoft-teams-rooms-requirements"></a>Требования к комнатам Microsoft Teams

Комнаты Microsoft Teams разного размера комнаты. Комнаты Teams использовать широкий спектр сертифицированных периферийных устройств для аудио- и видеосвязи в зависимости от размера и использования комнаты. Выбрав нужное основное устройство и консоль в сочетании с микрофонами, динамиками, камерами и мониторами, вы можете развернуть Комнаты Microsoft Teams на любых пространствах любого размера от небольших мест для конференц-связи до больших конференц-залов и конференц-залов.  Полный набор доступных сертифицированных периферийных аудио и видео устройств, которые можно использовать для настройки комнаты, см. в статье [Демонстрация устройств](https://products.office.com/microsoft-teams/across-devices).

В этой статье представлены общие требования к развертыванию и конфигурации устройств для поддержки комнат Microsoft Teams.

Развертывание включает в себя создание учетной записи, как описано в статье [Развертывание комнаты Microsoft Teams](rooms-deploy.md) и настройку консолей собраний, как указано в статье [Настройка консоли Комнат Microsoft Teams](console.md).

Обратитесь к:

- [Лицензирование надстройки Skype для бизнеса](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Параметры лицензии с учетом плана: Комнаты Microsoft Teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Комнаты Microsoft Teams подключаются к Microsoft Teams, Skype для бизнеса Server 2019, Skype для бизнеса Server 2015 или Skype для бизнеса Online, и присоединяются к собраниям любой из этих служб.
>
> Такие приложения, как Lync Server 2013, не поддерживаются в Комнатах Microsoft Teams. Комнаты Microsoft Teams не поддерживается в Microsoft 365 или Office 365 под управлением 21Vianet или doD.
>
> Если вы используете локальный Exchange server, в комнатах Microsoft Teams необходимо использовать Exchange Server 2013 SP1 или более позднюю версию.

## <a name="hardware-requirements"></a>Требования к оборудованию
В развертывание оборудования входит выбор системы комнат Microsoft Teams, вместе с сертифицированными периферийными аудио и видео устройствами, и кабели для объединения этих устройств.  Эти параметры описаны ниже.

**Поддерживаемые системы комнат Microsoft Teams**

Все текущие устройства и пакеты комнат Microsoft Teams можно найти в статье [Демонстрация продуктов систем комнат](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=).

  |Консоль|Процессор|ОЗУ|Диск|
  |:-----|:-----|:-----|:-----|
  |[Uc-M130-T с Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 ГБ |128 ГБ |
  |[Uc-B130-T с Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 ГБ |128 ГБ |
  |[Uc-B140-T с Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 ГБ |128 ГБ |
  [Uc-C140-T с Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C140-T)|Core i7|8 ГБ |128 ГБ|
  |[Uc-M150-T с Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)  +  [CCS-UCA-MIC](https://www.crestron.com/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 ГБ |128 ГБ |
  |[Uc-MX150-T с Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8 ГБ |128 ГБ |
   [Uc-B160-T с Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 ГБ |128 ГБ|
  |[Uc-C160-T с Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 ГБ|128 ГБ|
  |[Uc-MMX30-T с UC Presentation Transmitter (UC-PR) и КОМПЬЮТЕРОМ ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MMX30-T)|Core i5|8 ГБ |128 ГБ |
  |[Uc-BX30-T с UC Presentation Transmitter (UC-PR) и КОМПЬЮТЕРОМ ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-BX30-T)|Core i5|8 ГБ |128 ГБ |
  |[Uc-CX100-T с UC Presentation Transmitter (UC-PR) и ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T)|Core i5|8 ГБ |128 ГБ |
  |[Uc-B30-T с КОМПЬЮТЕРОМ ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B30-T)|Core i5|8 ГБ |128 ГБ |
   |[Uc-C100-T с КОМПЬЮТЕРОМ ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)|Core i5|8 ГБ |128 ГБ |
   |[Uc-M50-T с КОМПЬЮТЕРОМ ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M50-T)|Core i5|8 ГБ |128 ГБ |
   |[Uc-M70-T с КОМПЬЮТЕРОМ ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M70-T)|Core i5|8 ГБ |128 ГБ |
   |[Uc-MX50-T с КОМПЬЮТЕРОМ ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX50-T)|Core i5|8 ГБ |128 ГБ |
   |[Uc-MX70-T с КОМПЬЮТЕРОМ ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX70-T)|Core i5|8 ГБ |128 ГБ |
  |[Манкрон Миллиметр (Mini UC-MM30-T)](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MM30-T)|Core i5|8 ГБ |128 ГБ |
  |[Dell OptiPlex 7080 с logitech TAP](https://www.dell.com/work/shop/cty/pdp/spd/optiplex-7080-xe-teams) | Core i7 |16 ГБ |128 ГБ|
  |[HP Elite Slice для Meeting Rooms G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 ГБ |128 ГБ |
  |[HP Elite Slice G2 с готовым аудио для комнат Microsoft Teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 ГБ |128 ГБ |
  |[HP Slice Partner Ready with Logitech TAP]( https://www.logitech.com/video-collaboration/partners/hp.html)|Core i5|8 ГБ|128 ГБ| 
  |[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8 ГБ |128 ГБ |
  |[Lenovo ThinkSmart Hub](https://news.lenovo.com/pressroom/press-releases/new-thinksmart-hub-collaboration-solution-from-lenovo-helps-organizations-embrace-hybrid-working-model/) |Core i5 |8 ГБ |128 ГБ|
  |Lenovo ThinkSmart Core Kit |Core i5|8 ГБ|128 ГБ|
  |[Logitech Tap with Intel NUC](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 ГБ |128 ГБ |
  |Logitech Tap and Intel Tiger Canyon NUC PC |Core i5|8 ГБ|128 ГБ|
  |[Logitech Tap and Lenovo ThinkSmart Tiny](https://www.logitech.com/video-collaboration/partners/lenovo.html)|Core i5|8 ГБ |128 ГБ|
  |[Poly G10-T with Lenovo ThinkSmart Tiny](https://www.poly.com/us/en/products/video-conferencing/g/g10) |Core i5| 8 ГБ | 128 ГБ|
  |[Yealink MVC300 с Intel NUC](https://www.yealink.com/products_154.html)|Core i5|8 ГБ |128 ГБ |
  |[Yealink MVC500 с Intel NUC](https://www.yealink.com/products_126.html)|Core i5|8 ГБ |128 ГБ |
  |[Yealink MVC800 с Intel NUC](https://www.yealink.com/products_125.html)|Core i5|8 ГБ|128 ГБ|
  |[Yealink MVC900 с Intel NUC](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8 ГБ|128 ГБ|
  |[Yealink MVC 300 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc300II) |Core i5|8 ГБ | 128 ГБ|
  |[Yealink MVC400](https://www.yealink.com/product/microsoft-teams-room-system-mvc400)        |Core i5|8 ГБ | 128 ГБ|
  |[Yealink MVC 500 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc500II) |Core i5|8 ГБ | 128 ГБ|
  |[Yealink MVC 800 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc800II) |Core i5|8 ГБ | 128 ГБ|
  |[Yealink MVC 900 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc900II) |Core i5|8 ГБ | 128 ГБ|
  |[Yealink MVC840](https://www.yealink.com/product/microsoft-teams-room-system-mvc840) |Core i5|8 ГБ | 128 ГБ|
  |[Yealink MVC940](https://www.yealink.com/product/microsoft-teams-room-system-mvc940) |Core i5|8 ГБ | 128 ГБ|
  |Yealink MVC660|Core i5|8 ГБ | 128 ГБ|
  |Yealink MVC640|Core i5|8 ГБ | 128 ГБ|
  |Yealink MVC320|Core i5|8 ГБ | 128 ГБ|
  
  
> [!NOTE]
> - Процессоры Core M3 не поддерживаются. 
> - Вам потребуется USB-накопитель емкостью до 32 ГБ или более, настроенный как загрузочный установочный носитель Windows для ОС Windows 10 Корпоративная.

**Поддерживаемые планшеты Surface Pro для док-систем**

  |Планшет|Процессор|ОЗУ|Диск|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 ГБ или 8 ГБ |128 ГБ или больше |
  |Surface Pro </br>(fifth Gen) |Core i5 |8 ГБ или 4 ГБ |128 ГБ или больше |
  |Surface Pro 4 |Core i5 |8 ГБ или 4 ГБ |128 ГБ или больше |

- Surface Pro требуется один из следующих параметров док-станции:

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>Сертифицированные версии встроенного ПО для периферийных аудио и видео USB устройств.

Устройства можно найти в статьях [Демонстрация аксессуаров систем комнаты](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=) и [https://office.com/teamsdevices](https://office.com/teamsdevices).

|Периферийные устройства комнат Microsoft Teams|Сертифицированная версия встроенного ПО | Камера поддерживающая использование содержимого|
|:--- |:--- | :--- |
|[Aver VC520 Pro Camera + Speakerphone](https://www.averusa.com/products/conference-camera/vc520pro) |1004.35|
|[Aver VB342+ Звуковая панель камеры](https://www.averusa.com/products/conference-camera/vb342plus) | Звуковая панель: 0.0.0000.97|
|[Aver CAM 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 520 Pro](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Aver CAM 520 Pro 2](https://www.averusa.com/products/conference-camera/cam520pro2) |0.0.7200.3 |
|[Aver CAM 130](https://www.averusa.com/products/conference-camera/cam130) |0.0.7400.03 |
|[Bose Video Bar VB1](https://pro.bose.com/en_us/products/conferencing/videobars/bose-videobar-vb1.html?mc=25_PS_VB_BO_00_BI_&&msclkid=fc99b79880f714727a63e86ea0e5642a&utm_source=bing&utm_medium=cpc&utm_campaign=US%20-%20Brand_Videobar%20VB1_Exact&utm_term=bose%20videobar%20vb1&utm_content=Bose%20Videobar%20VB1&gclid=fc99b79880f714727a63e86ea0e5642a&gclsrc=3p.ds) |19.2|
|[VioMp Devio SCR-20CX Web-Based Conferencing Hub с микрофоном окверха](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9|
|[Vio Devio SCR-20TX Web-Based Conferencing Hub с настольным микрофоном](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9 |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|[Huddly Canvas](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Huddly IQ Lite](https://www.huddly.com/conference-cameras/iq/) |1.3.29|
|[Huddly IQ Camera](https://www.huddly.com/conference-cameras/iq/) |1.3.27|
|[Камера Jabra Panacast3](https://www.jabra.com/business/video-conferencing/jabra-panacast)|1.3.9.12|
|[Jabra Panacast 50 Video Bar](https://www.jabra.com/business/video-conferencing/jabra-panacast-50)|1.9.3|
|[Lenovo ThinkSmart Cam Camera](https://www.lenovo.com/us/en/accessories-and-monitors/webcams-and-video/webcams/SMARTOF-BO-ThinkSmart-Cam/p/4Y71C41660)|1.0.111.4|
|[Lenovo ThinkSmart Bar](https://www.lenovo.com/us/en/virtual-reality-and-smart-devices/smart-collaboration/thinksmart/ThinkSmart-Bar/p/11SP1TSSDBR)|0.9.3|
|Lenovo ThinkSmart Bar Expand XL|5.9.5|
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech Висячий линечик](https://www.logitech.com/products/video-conferencing/room-solutions/rallybar.960-001308.html)   |10.3.82|
|[Logitech Висячий линечик mini](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/rallybarmini.960-001336.html) |10.5.880|
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |Звук — 1.0.172 <br/> Видео— 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Зауваева HDL300](https://www.nureva.com/audio-conferencing/hdl300) |2.3.6|
|[Камера Poly Eagle Eye Cube](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.poly.com/us/en/products/video-conferencing/eagleeye/eagleeye-iv)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Poly Sync 40](https://www.poly.com/us/en/products/phones/sync/sync-40)|0.0.94.1461|
|[Poly Sync 60](https://www.poly.com/us/en/products/phones/sync/sync-60)|0.0.150.1671|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Poly Trio C60](https://www.poly.com/us/en/products/phones/trio/trio-c60)  |5.9.5.3066|
|[Видеостудия Poly Studio P15](https://www.poly.com/us/en/products/video-conferencing/studio-p/studio-p15)|1.2.0.000287 |
|[EPOS SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[EPOS SP20](https://www.eposaudio.com/en/us/enterprise/products/sp-20-ml-142ee5ca-speakerphone-1000226)   |1.2.15   |
|[EPOS SP30](https://www.eposaudio.com/en/us/enterprise/products/sp-30-78c0cecc-bluetooth-speakerphone-1000223)   |2.1.52  |
|[EPOS SP30T](https://www.eposaudio.com/en/us/enterprise/products/sp-30t-b949fe9a-bluetooth-speakerphone-1000225)  |3.2.63  |
|[EPOS Expand 80T + 2 Extension Mics](https://www.eposaudio.com/en/us/enterprise/products/expand-80t-bluetooth-speakerphone-1000203) |Динамик — 4.6.55 <br/> Расширение микрофона — 0.2.314|
|[EpOS Expand Capture 5](https://www.eposaudio.com/en/us/enterprise/products/expand-capture-5-speakerphone-1000895)  |1.0.1|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Yealink UVC30](https://www.yealink.com/product/microsoft-teams-room-system-uvc30)| 105.420.0.11 |  &#x2714; |
|[Yealink UVC40 All-in-one Video bar](https://www.yealink.com/product/usb-videobar-uvc40) |128.410.0.10|  
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300)+</br></br> [Shure MXA 310 Table Array Mic ](https://www.shure.com/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) + </br></br> [Shure MXA 910 with Intellimix Ceiling Array Mic](https://www.shure.com/products/microphones/mxa910) | 4.1|
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300)+</br></br> [Микрофон таблицы в Таблице MXA 310 ](https://www.shure.com/products/microphones/mxa310) +</br></br> [Динамик октата MXN5W-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> Микрофон таблицы MXA310: 4.1.41 </br> Динамик MXN5W-C: 1.0.4 |
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) + </br></br> [Часовой диапазон MXA 910 с микрофоном Intellimix Ceiling Array](https://www.shure.com/products/microphones/mxa910) +</br></br> [Динамик октата MXN5W-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> Микрофон октата по окнам массива MXA910: 4.1.41 </br> Динамик MXN5W-C: 1.0.4 |
|[Microphonere MXA 710 2ft Table Linear Array Microphone](https://www.shure.com/products/microphones/mxa710) + </br></br> [Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) +</br></br> [Динамик октата MXN5-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 2ft Table Linear Array Mic: 1.2.0 </br> P300 DSP: 4.4.8 </br> Динамик MXN5-C: 1.1.1 |
|[Микрофон линейного массива стены 710 4ft](https://www.shure.com/products/microphones/mxa710) + </br></br> [Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) +</br></br> [Динамик октата MXN5-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 4ft Wall Linear Array Mic: 1.2.0 </br> P300 DSP: 4.4.8 </br> Динамик MXN5-C: 1.1.1 |
|[Телефона MXA 910 с микрофоном intellimix Ceiling Array](https://www.shure.com/products/microphones/mxa910) + </br> [Программное обеспечение комнаты Intellimix](https://www.shure.com/products/software/intellimix_room) +</br> [Crestron UC-C100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)| Программное обеспечение комнаты Intellimix: 3.0.4.14 </br> Телефона MXA 910 с микрофоном Intellimix Ceiling Array: 4.4.11 </br> Динамики MXN5-C: 1.2.1 </br> UC-C100-T: windows IOT 19h2/20h2 OS с версией приложения MTR 4.8.31.0 </br> БИО: ASUS Tek Computer INC 9934 27.08.2020 </br> ЦП: i5–9500TCPU </br> Физическая память: 8 ГБ ОЗУ |
|[Biamp Tesira Fore AVB VT4 Fixed audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Sennheiser TeamConnect Ceiling 2 Microphone](https://sennheiser.com/tcc2)+ &Dagger;</br></br> [Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP: 3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT: 3.12.0.15 |
|[Дефис Tesira FORTÉ AVB VT4 Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Дефис Parlé TCM-XA окне окне микрофона](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br> [Десоно C-IC6, повернутый в динамик](https://www.biamp.com/products/tesira-speakers)| Audio FW version: 3.15|
|[Дефис TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Parle TTM-X(Table Mic)](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br>[Ex-UBT]() |Audio FW version: 3.15|
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink Amplifier +</br> Sennheiser TCC2 Ceiling Microphone + </br> Bose EdgeMax EM180 Ceiling Speaker](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br> Bose P2600A AmpLink Amplifier + Sennheiser TCC2 Ceiling Microphone + </br> Bose DesignMax DM2C-P Ceiling Speaker](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A amplink amplifier +</br> [Микрофон в окне "Sennheiser TCC2"](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [DesignMax DM2C -LP Ceiling Speaker](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/designmax/designmax_dm2c_lp.html#v=designmax_dm2c_lp_black) | Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  | 
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Amplifier+</br> [Микрофон в окне "Sennheiser TCC2"](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [Потолочный динамик EdgeMax EM180](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/edgemax/edgemax_em180.html#v=edgemax_em180_white) | Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |
|QSC Q-SYS Core[(110f,](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-110f/) [8Рку,](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-8-flex/) [Google](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-nano/)или [NV-32-H](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/nv-32-h-core-capable/)) + </br> [Микрофон в окне "Sennheiser TCC2"](https://en-us.sennheiser.com/tcc2) + </br> QSC Amplifier[(SPA series](https://www.qsc.com/solutions-products/power-amplifiers/installed/non-network/low-power-applications/spa-series/) or [CX-Q series](https://www.qsc.com/solutions-products/power-amplifiers/installed/network/cx-q-series/)) + </br> [Динамики QSC AcousticDesign ряда](https://www.qsc.com/solutions-products/loudspeakers/installed/passive/solutions/acousticdesigntm-series-solutions/) + </br> IP-камера QSC[(PTZ-IP 20x60,](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/) [PTZ-IP 12x72](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/)) при желании + </br> [QSC Q-SYS I/O USB Bridge](https://www.qsc.com/solutions-products/q-sys-ecosystem/audio-io-peripherals/io-usb-bridge/) optional | QSC Q-SYS Core, PTZ-IP Camera и I/O USB Bridge: QSC Q-SYS Designer 9.0.1-2104.022 </br> Микрофон октата Sennheiser TCC2: TCC2 - 1.5.1, Dante 1.2.0 </br> Amplifiers QSC: N/A </br> QSC AcousticDesign Series Loudspeakers: N/A | 


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
|**Среднее** <br/> 18' x 20'  |6–12  |2.4 м  |Jabra 710 <br/> Jabra 810 <br/> Logitech MeetUp <br/> Logitech Group <br/> Polycom Trio <br/> Polycom CX5100 <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS  |Устройство Logitech MeetUp оснащено камерой, поэтому его следует размещать в стороне от стола, за которым проходит собрание, а не в его центре. <br/> В помещениях с длинным прямоугольным столом или столом в форме буквы "U" лучше использовать спутниковые микрофоны. <br/> В конфигурации последовательной цепочки необходимо использовать пакет SP 220 MS.  |
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
