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
- Teams_ITAdmin_Rooms
description: Узнайте о требованиях к поддержке Комнаты Microsoft Teams, включая выбор соответствующего устройства, микрофонов, динамиков, камер и дисплеев.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90372af0b5fed4a56344003bc94174a8832fbb19
ms.sourcegitcommit: e8c7a5ddc3399492485680e9a6f2593658cecca3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2022
ms.locfileid: "68686077"
---
# <a name="microsoft-teams-rooms-requirements"></a>Требования к комнатам Microsoft Teams

Комнаты Microsoft Teams масштабирование помещений разных размеров. Комнаты Teams использовать широкий спектр сертифицированных аудио- и видео периферийных устройств в зависимости от размера и использования помещения. Выбрав правильное основное устройство и консоль в сочетании с микрофонами, динамиками, камерами и дисплеями, подходящими для пространства, вы можете развернуть Комнаты Microsoft Teams в пространствах любого размера, от небольших ютых пространств до больших конференц-залов и залов заседаний.  Полный набор доступных сертифицированных периферийных аудио и видео устройств, которые можно использовать для настройки комнаты, см. в статье [Демонстрация устройств](https://products.office.com/microsoft-teams/across-devices).

В этой статье представлены общие требования к развертыванию и конфигурации устройств для поддержки комнат Microsoft Teams.

Развертывание включает создание учетной записи ресурса и настройку Комнаты Teams, как описано в разделе [Развертывание Комнаты Microsoft Teams](rooms-deploy.md).

См. раздел:

- [Параметры лицензии с учетом плана: Комнаты Microsoft Teams](rooms-licensing.md)

> [!NOTE]
> Комнаты Microsoft Teams войдите в Microsoft Teams Skype для бизнеса Server 2019 или Skype для бизнеса Server 2015 г. и могут присоединяться к собраниям, размещенным в любой из этих служб.
>
> Такие приложения, как Lync Server 2013, не поддерживаются в Комнатах Microsoft Teams. Комнаты Microsoft Teams не поддерживается в Microsoft 365 или Office 365, управляемых средами 21Vianet или DoD.
>
> Если вы используете локальный Exchange server, в комнатах Microsoft Teams необходимо использовать Exchange Server 2013 SP1 или более позднюю версию.

## <a name="hardware-requirements"></a>Требования к оборудованию
Аппаратное развертывание включает в себя выбор Комнаты Microsoft Teams системы в сочетании с сертифицированными аудио- и видео периферийными устройствами, а также кабельное решение для интеграции этих устройств.  Эти параметры описаны ниже.

**Поддерживаемые системы Комнаты Microsoft Teams**

Все текущие Комнаты Microsoft Teams устройства и пакеты доступны в [демонстрации продукта Комнаты Teams](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=).

  |Консоль|Процессор|ОЗУ|Диск|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130-T с Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 ГБ |128 ГБ |
  |[Crestron Flex UC- B130-T с Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 ГБ |128 ГБ |
  |[Crestron Flex UC-B140-T с Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 ГБ |128 ГБ |
  [Crestron Flex UC-C140-T с Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C140-T)|Core i7|8 ГБ |128 ГБ|
  |[Crestron Flex UC-M150-T с Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T) +  [CCS-UCA-MIC](https://www.crestron.com/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 ГБ |128 ГБ |
  |[Crestron Flex UC-MX150-T с Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8 ГБ |128 ГБ |
   [Crestron Flex UC-B160-T с Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 ГБ |128 ГБ|
  |[Crestron Flex UC-C160-T с Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 ГБ|128 ГБ|
  |[Crestron Flex UC-MMX30-T с UC Presentation Transmitter (UC-PR) и ПК ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MMX30-T)|Core i5/i7|8 ГБ |128 ГБ |
  |[Crestron Flex UC-BX30-T с UC Presentation Transmitter (UC-PR) и ПК ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-BX30-T)|Core i5/i7|8 ГБ |128 ГБ |
  |[Crestron Flex UC-CX100-T с UC Presentation Transmitter (UC-PR) и ПК ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T)|Core i5/i7|8 ГБ |128 ГБ |
  |[Crestron Flex UC-B30-T с ПК ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B30-T)|Core i5/i7|8 ГБ |128 ГБ |
   |[Crestron Flex UC-C100-T с ПК ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)|Core i5/i7|8 ГБ |128 ГБ |
   |[Crestron Flex UC-M50-T с ПК ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M50-T)|Core i5/i7|8 ГБ |128 ГБ |
   |[Crestron Flex UC-M70-T с ПК ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M70-T)|Core i5/i7|8 ГБ |128 ГБ |
   |[Crestron Flex UC-MX50-T с ПК ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX50-T)|Core i5/i7|8 ГБ |128 ГБ |
   |[Crestron Flex UC-MX70-T с ПК ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX70-T)|Core i5/i7|8 ГБ |128 ГБ |
   |Crestron FLEX UC-B30-T с Dell OPTIPLEX|Core i5|8 ГБ|128 ГБ|
   |Crestron FLEX UC-Bx30-T с Dell OPTIPLEX|Core i5|8 ГБ|128 ГБ|
   |Crestron FLEX UC-MM30-T с Dell OPTIPLEX|Core i5|8 ГБ|128 ГБ|
   |Crestron FLEX UC-MMX30-T с Dell OPTIPLEX|Core i5|8 ГБ|128 ГБ|
   |Crestron FLEX UC-M50-T с Dell OPTIPLEX|Core i5|8 ГБ|128 ГБ|
   |Crestron FLEX UC-MX50-T с Dell OPTIPLEX|Core i5|8 ГБ|128 ГБ|
   |Crestron FLEX UC-M70-T с Dell OPTIPLEX|Core i5|8 ГБ|128 ГБ|
   |Crestron FLEX UC-MX70-T с Dell OPTIPLEX|Core i5|8 ГБ|128 ГБ|
   |Crestron FLEX UC-C100-T с Dell OPTIPLEX|Core i5|8 ГБ|128 ГБ|
   |Crestron FLEX UC-CX100-T с Dell OPTIPLEX|Core i5|8 ГБ|128 ГБ|
  |[Crestron Mercury Mini UC-MM30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MM30-T)|Core i5|8 ГБ |128 ГБ |
  |[Dell OptiPlex 7080 с Logitech TAP](https://www.dell.com/en-us/work/shop/cty/pdp/spd/optiplex-7080-xe-teams) | Core i7 |16 ГБ |128 ГБ|
  |[HP Elite Slice для Meeting Rooms G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 ГБ |128 ГБ |
  |[HP Elite Slice G2 с готовым аудио для комнат Microsoft Teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 ГБ |128 ГБ |
  |[HP Slice Partner Ready with Logitech TAP]( https://www.logitech.com/video-collaboration/partners/hp.html)|Core i5|8 ГБ|128 ГБ| 
  |[Решение HP Presence Small Space с Комнаты Microsoft Teams](https://www.hp.com/us-en/solutions/presence.html)|Core i5/i7|8 ГБ/16 ГБ|256 ГБ|
  |[Решение HP Presence Small Space и камера ИИ с Комнаты Microsoft Teams](https://www.hp.com/us-en/solutions/presence.html)|Core i5/i7|8 ГБ/16 ГБ|256 ГБ|
  | Lenovo ThinkSmart Hub 500 |Core i5 |8 ГБ |128 ГБ |
  |[Lenovo ThinkSmart Hub](https://news.lenovo.com/pressroom/press-releases/new-thinksmart-hub-collaboration-solution-from-lenovo-helps-organizations-embrace-hybrid-working-model/) |Core i5 |8 ГБ |128 ГБ|
  |Lenovo ThinkSmart Core Kit |Core i5|8 ГБ|128 ГБ|
  |[Logitech Tap с Intel NUC](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 ГБ |128 ГБ |
  |Logitech Tap и Intel Tiger Canyon NUC PC |Core i5|8 ГБ|128 ГБ|
  |Консоль Logitech TAP с Lenovo Core Compute |Core i5|8 ГБ|128 ГБ|
  |[Logitech Tap и Lenovo ThinkSmart Tiny](https://www.logitech.com/video-collaboration/partners/lenovo.html)|Core i5|8 ГБ |128 ГБ|
  |[Poly G10-T с Lenovo ThinkSmart Tiny](https://www.poly.com/us/en/products/video-conferencing/g/g10) |Core i5| 8 ГБ | 128 ГБ|
  |[Комплект Poly G40-T с Poly Studio USB и Lenovo](https://www.poly.com/us/en/support/products/video-conferencing/poly-room-solutions/g40) |Core i5| 8 ГБ | 128 ГБ|
  |[Poly G85-T Kit с Poly Eagle Eye Director II, с Lenovo](https://www.poly.com/us/en/support/products/video-conferencing/poly-room-solutions/g85) |Core i5| 8 ГБ | 128 ГБ|
  |Консоль Poly GC8 с Lenovo Thinksmart Core|Core i5|8 ГБ|128 ГБ|
  |Консоль Poly GC8 с Dell Optiplex 7080|Core i5|8 ГБ|128 ГБ|
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
  |Yealink MVC340|Core i5|8 ГБ | 128 ГБ|
  
  
> [!NOTE]
> - Процессоры Core M3 не поддерживаются. 
> - Вам потребуется USB-накопитель емкостью до 32 ГБ или более, настроенный как загрузочный установочный носитель Windows для ОС Windows 10 Корпоративная.

**Поддерживаемые планшеты Surface Pro для док-систем**

  |Планшет|Процессор|ОЗУ|Диск|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 ГБ или 8 ГБ |128 ГБ или больше |
  |Surface Pro </br>(fifth Gen) |Core i5 |8 ГБ или 4 ГБ |128 ГБ или больше |
  |Surface Pro 4 |Core i5 |8 ГБ или 4 ГБ |128 ГБ или больше |

- Surface Pro устройствам требуется один из следующих вариантов док-станции:

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>Сертифицированные версии встроенного ПО для периферийных аудио и видео USB устройств.

Устройства можно найти в статьях [Демонстрация аксессуаров систем комнаты](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=) и [https://office.com/teamsdevices](https://office.com/teamsdevices).

|Периферийные устройства комнат Microsoft Teams|Сертифицированная версия встроенного ПО | Поддерживает камеру содержимого|Интеллектуальная камера|
|:--- |:--- | :--- |:--- |
|[Камера Aver VC520 Pro + динамик](https://www.averusa.com/products/conference-camera/vc520pro) |1004.35|
|[Система конференц-связи Aver VC520 PRO2](https://www.averusa.com/products/conference-camera/vc520pro2) | 00.0.7200.79 |
|[Звуковая панель камеры Aver VB342+](https://www.averusa.com/products/conference-camera/vb342plus) | Soundbar: 0.0.0000.97|
|[Панель видео Aver VB342 pro](https://www.averusa.com/products/video-collaboration-bar/vb342pro) | 0.0.7800.61 |
|[Aver CAM 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 550](https://www.averusa.com/products/conference-camera/cam550) |0.0.8000.51 |
|[Aver CAM 520 Pro](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Aver CAM 520 Pro 2](https://www.averusa.com/products/conference-camera/cam520pro2) |0.0.7200.3 |
|[Aver CAM 130](https://www.averusa.com/products/conference-camera/cam130) |0.0.7450.02 | &#x2714; |
|[Авер Fone540](https://www.averusa.com/products/vc-accessories/fone540) |0.0.7002.17|
|[Звуковая панель камеры Aver VB130](https://www.averusa.com/products/conference-camera/vb130) |0.0.7300.71 |
|[Аудиокоды RXVCAM50L](https://www.audiocodes.com/solutions-products/products/room-experience-rx-suite/rxvcam50lm-video-camera) |1.0.5 |
|[Bose Видео бар VB1](https://pro.bose.com/en_us/products/conferencing/videobars/bose-videobar-vb1.html?mc=25_PS_VB_BO_00_BI_&&msclkid=fc99b79880f714727a63e86ea0e5642a&utm_source=bing&utm_medium=cpc&utm_campaign=US%20-%20Brand_Videobar%20VB1_Exact&utm_term=bose%20videobar%20vb1&utm_content=Bose%20Videobar%20VB1&gclid=fc99b79880f714727a63e86ea0e5642a&gclsrc=3p.ds) |19.2|
|[Biamp Devio SCR-20CX Web-Based конференц-центр с потолочным микрофоном](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9|
|[Biamp Devio SCR-20TX Web-Based конференц-центр с микрофоном Tabletop](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9 |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|HP Presence See Camera| 1.0.23.0 |
|[Huddly Canvas](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Huddly IQ Lite](https://www.huddly.com/conference-cameras/iq/) |1.3.29|
|[Huddly IQ Camera](https://www.huddly.com/conference-cameras/iq/) |1.3.27|
|[Huddly L1](https://www.huddly.com/conference-cameras/l1/) | 1.2.9 |
|Huddly L1 Камера с [Crestron UC-C100-T MTR](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T) комплект | Huddly L1 Камера: 1.2.1 </br> Crestron UC-C100-T с ASUS Tek Computer INC 9934 compute 1.0.20.246 или более поздней версии |
|Huddly L1 Камера с [Crestron UC-CX100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T) MTR-W Kit | Huddly L1 Камера: 1.2.9 </br> Crestron UC-CX100-T с ASUS Tek Computer INC 9934 1.00.20.246 или более поздней версии |
|Huddly L1 Камера с Crestron UC-M70-T MTR комплект | Huddly L1 Камера: 1.2.1 </br> Crestron UC-M70-T с ASUS Tek Computer INC 9934 compute 1.0.20.246 или более поздней версии |
|Huddly L1 Камера с Crestron UC-MX70-T MTR комплект | Huddly L1 Камера: 1.2.1 </br> Crestron UC-MX70-T с ASUS Tek Computer INC 9934 compute 1.0.20.246 или более поздней версии |
|[Камера Jabra Panacast3](https://www.jabra.com/business/video-conferencing/jabra-panacast)|1.3.9.12|
|[Jabra Panacast 50 Видео бар](https://www.jabra.com/business/video-conferencing/jabra-panacast-50)|4.0.15| &#x2714; | &#x2714;|
|[Камера Lenovo ThinkSmart Cam](https://www.lenovo.com/us/en/accessories-and-monitors/webcams-and-video/webcams/SMARTOF-BO-ThinkSmart-Cam/p/4Y71C41660)|1.0.111.4|
|[Lenovo ThinkSmart Bar](https://www.lenovo.com/us/en/virtual-reality-and-smart-devices/smart-collaboration/thinksmart/ThinkSmart-Bar/p/11SP1TSSDBR)|0.9.3|
|Lenovo ThinkSmart Bar Expand XL|5.9.5|
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech Rally Bar](https://www.logitech.com/products/video-conferencing/room-solutions/rallybar.960-001308.html)   |10.3.82|
|[Logitech Rally Bar Mini](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/rallybarmini.960-001336.html) |10.5.880|
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |Звук — 1.0.172 <br/> Видео— 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Logitech Scribe](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/scribe.960-001332.html) | 1.1.1 | &#x2714; |
|[Nureva HDL300](https://www.nureva.com/audio-conferencing/hdl300) |2.3.6|
|[Камера Poly Eagle Eye Cube](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.poly.com/us/en/products/video-conferencing/eagleeye/eagleeye-iv)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.md)   | 1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://support.polycom.com/content/dam/polycom-support/products/peripherals/eagle-eye-director-ii/user/en/eagleeye-director-ii-admin-guide-2-0.pdf#:~:text=The%20Polycom%C2%AE%20EagleEye%E2%84%A2%20Director%20II%20camera%20is%20a,while%20the%20other%20camera%20tracks%20the%20second%20speaker.)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Poly Sync 40](https://www.poly.com/us/en/products/phones/sync/sync-40)|0.0.94.1461|
|[Poly Sync 60](https://www.poly.com/us/en/products/phones/sync/sync-60)|0.0.150.1671|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Poly Trio C60](https://www.poly.com/us/en/products/phones/trio/trio-c60)  |5.9.5.3066|
|[Панель видео Poly Studio P15](https://www.poly.com/us/en/products/video-conferencing/studio-p/studio-p15)|1.2.0.000287 |
|[Камера Poly Studio E70](https://www.poly.com/us/en/products/video-conferencing/studio/studio-e70)|1.1|
|[Poly Studio R30](https://www.poly.com/us/en/products/video-conferencing/studio/studio-r30)|2.0.0.001096|
|[EPOS SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[EPOS SP20](https://www.eposaudio.com/en/us/enterprise/products/sp-20-ml-142ee5ca-speakerphone-1000226)   |1.2.15   |
|[EPOS с пакетом обновления 30 (SP30)](https://www.eposaudio.com/en/us/enterprise/products/sp-30-78c0cecc-bluetooth-speakerphone-1000223)   |2.1.52  |
|[EPOS SP30T](https://www.eposaudio.com/en/us/enterprise/products/sp-30t-b949fe9a-bluetooth-speakerphone-1000225)  |3.2.63  |
|[EPOS: развернуть 80T + 2 микрофона расширения](https://www.eposaudio.com/en/us/enterprise/products/expand-80t-bluetooth-speakerphone-1000203) |Динамик — 4.6.55 <br/> Микрофон расширения — 0.2.314|
|[EPOS Expand Capture 5](https://www.eposaudio.com/en/us/enterprise/products/expand-capture-5-speakerphone-1000895)  |1.0.1|
|[Extron DMP128 PLUS C V AT DSP System (DMP 128 Plus C V AT, DMP 128 Plus C AT, DMP 128 Plus C V, DMP 128 Plus C, DMP 128 Plus AT, DMP 128 Plus, DMP 128 FlexPlus C AT, DMP 128 FlexPlus C V AT)](https://www.extron.com/product/dmp128plus) | 1.08 |
|[Extron DMP 64 PLUS C V AT DSP System (DMP 64 Plus C V AT, DMP 64 Plus C AT, DMP 64 Plus C V, DMP 64 Plus C)](https://www.extron.com/product/dmp64plus) | 1.08|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yamaha YVC-1000MS](https://uc.yamaha.com/products/conference-phones/usb-bluetooth/) |1.0.0 |
|[Потолочное решение Yamaha ADECIA](https://uc.yamaha.com/products/microphone-systems/adecia/)|1.2.0|
|[Решение yamaha ADECIA Tabletop](https://uc.yamaha.com/products/adecia/adecia-tabletop/)|E1.2.0 для табличного микрофона, D1.2.0 для процессора (то же содержимое, что и версия 1.5.1)|
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Yealink UVC30](https://www.yealink.com/product/microsoft-teams-room-system-uvc30)| 105.420.0.11 |  &#x2714; |
|[Панель видео Yealink UVC34 "Все в одном"](https://www.yealink.com/product/usb-videobar-uvc34) | 265.410.0.9 |
|[Панель видео Yealink UVC40 "Все в одном"](https://www.yealink.com/product/usb-videobar-uvc40) |128.410.0.10|  
|[Yealink UVC84](https://www.yealink.com/product/camera-uvc84) |262.410.0.10|
|[Yealink UVC86]( https://www.yealink.com/product/camera-uvc86) |151.410.0.5|
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300)+</br>[Shure MXA 310 Table Array Mic ](https://www.shure.com/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) +</br>[Shure MXA 910 with Intellimix Ceiling Array Mic](https://www.shure.com/products/microphones/mxa910) | 4.1|
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300)+</br>[Микрофон массива таблиц Shure MXA 310 ](https://www.shure.com/products/microphones/mxa310) +</br>[Потолочный динамик MXN5W-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> Микрофон массива таблиц MXA310: 4.1.41 </br> Динамик MXN5W-C: 1.0.4 |
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) + </br>[Shure MXA 920 с микрофоном Intellimix Ceiling Array](https://www.shure.com/en-US/products/microphones/mxa920?utm_source=linkedin&utm_medium=social&sfid=&prod=) +</br>[Потолочный динамик MXN5W-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.7.7 </br> Микрофон mxA920 Ceiling Array: 1.1.56 </br> Динамик MXN5W-C: 1.5.6 |
|ANIUSB + </br> [Shure MXA 920 с микрофоном Intellimix Ceiling Array](https://www.shure.com/en-US/products/microphones/mxa920?utm_source=linkedin&utm_medium=social&sfid=&prod=) +</br>[Потолочный динамик MXN5](https://www.shure.com/en-US/products/loudspeakers/mxn5)| ANIUSB: 4.4.7 </br> MXA920: 1.1.56 </br> MXN5: 1.5.6|
|[Shure MXA 710 2ft Table Linear Array Микрофон](https://www.shure.com/products/microphones/mxa710) + </br>[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) +</br>[Потолочный динамик MXN5-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 2ft Table Linear Array Микрофон: 1.2.0 </br> P300 DSP: 4.4.8 </br> MxN5-C Динамик: 1.1.1 |
|[Shure MXA 710 4ft Wall Linear Array Микрофон](https://www.shure.com/products/microphones/mxa710) + </br>[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) +</br>[Потолочный динамик MXN5-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 4ft Wall Linear Array Микрофон: 1.2.0 </br> P300 DSP: 4.4.8 </br> MxN5-C Динамик: 1.1.1 |
|[Shure MXA 910 с микрофоном Intellimix Ceiling Array](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Room Software](https://www.shure.com/products/software/intellimix_room) +</br> [Crestron UC-C100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)| Shure Intellimix Room Software: 3.0.4.14 </br> Shure MXA 910 с потолочным микрофоном Intellimix: 4.4.11 </br> Shure MXN5-C Динамики: 1.2.1 </br> Crestron UC-C100-T с asus Tek Computer INC 9934 compute | 
|[Shure MXA 910 с микрофоном Intellimix Ceiling Array](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Room Software](https://www.shure.com/products/software/intellimix_room) +</br>Lenovo ThinkSmart Core | Shure Intellimix Room Software: 3.2.0.52 </br> Shure MXA 910 с потолочным микрофоном Intellimix: 4.4.11 </br> Shure MXN5-C Динамики: 1.2.1 |
|[Микрофон массива круглого потолка Shure MXA920XX-R](https://www.shure.com/en-US/products/microphones/mxa920?variant=MXA920AL-R) + </br> [Процессор P300](https://www.shure.com/en-US/products/mixers/p300?variant=P300-IMX) + </br> [Динамики MXN5](https://www.shure.com/en-US/products/loudspeakers/mxn5) | MXA920XX-R: 1.1.56 </br> Процессор P300: 4.7.7 </br> Динамики MXN5: 1.5.6 |
|[Shure MXA 910 с микрофоном Intellimix Ceiling Array](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Room Software](https://www.shure.com/products/software/intellimix_room) +</br>Dell Optiplex 7080 | Shure Intellimix Room Software: 3.2.0.52 </br> Shure MXA 910 с потолочным микрофоном Intellimix: 4.4.11 </br> Shure MXN5-C Динамики: 1.2.1 |
|[Sennheiser TeamConnect Intelligent Speaker/TC ISP (T-Rock)](https://en-us.sennheiser.com/tcisp)|1.0.2|
|[Biamp Tesira Fore AVB VT4 Fixed audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br>[Sennheiser TeamConnect Ceiling 2 Microphone](https://sennheiser.com/tcc2)+ &Dagger;</br>[Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP: 3.12.0.15 </br> TCC2: 1.3.3 </br>EX-UBT: 3.12.0.15 |
|[Biamp Tesira FORTÉ AVB VT4 Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+</br>[Потолочный микрофон Biamp Parlé TCM-XA](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br>[Biamp Desono C-IC6 потолок установлен громкоговоритель](https://www.biamp.com/products/tesira-speakers)| Версия Аудио FW: 3.15|
|[Biamp TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br>[Parle TTM-X(Table Mic)](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br>[Ex-UBT]() |Версия Аудио FW: 3.15|
|[Biamp Devio SCX Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br>[Потолочный микрофон Biamp Parlé TCM-XA](https://www.biamp.com/products/product-families/parle/parle-microphones) + </br> [Biamp Desono C-IC6 потолок установлен громкоговоритель](https://www.biamp.com/products/tesira-speakers) | Devio SCX Series: 4.2.5 |
|[Biamp Tesira Forte Серии X Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br>[Потолочный микрофон Biamp Parlé TCM-XA](https://www.biamp.com/products/product-families/parle/parle-microphones) + </br> [Biamp Desono C-IC6 потолок установлен громкоговоритель](https://www.biamp.com/products/tesira-speakers) | Tesira FORTE X Series: 4.2.5 |
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink Amplifier +</br> Sennheiser TCC2 Ceiling Microphone + </br> Bose EdgeMax EM180 Ceiling Speaker](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink Усилитель + sennheiser TCC2 Потолочный микрофон + </br> Bose DesignMax DM2C-P Потолочный динамик](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Усилитель +</br> [Sennheiser TCC2 Потолочный микрофон](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [Потолочный динамик DesignMax DM2C -LP](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/designmax/designmax_dm2c_lp.html#v=designmax_dm2c_lp_black) | Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  | 
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Усилитель+</br> [Sennheiser TCC2 Потолочный микрофон](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [Потолочный динамик EdgeMax EM180](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/edgemax/edgemax_em180.html#v=edgemax_em180_white) | Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  |
|QSC Q-SYS Core ([110f](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-110f/), [8 Flex](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-8-flex/), [Nano](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-nano/) или [NV-32-H](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/nv-32-h-core-capable/)) + </br> [Sennheiser TCC2 Потолочный микрофон](https://en-us.sennheiser.com/tcc2) + </br> Усилитель QSC ([серия SPA](https://www.qsc.com/solutions-products/power-amplifiers/installed/non-network/low-power-applications/spa-series/) или [серия CX-Q](https://www.qsc.com/solutions-products/power-amplifiers/installed/network/cx-q-series/)) + </br> [Динамики серии QSC AcousticDesign](https://www.qsc.com/solutions-products/loudspeakers/installed/passive/solutions/acousticdesigntm-series-solutions/) + </br> IP-камера QSC ([PTZ-IP 20x60](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/), [PTZ-IP 12x72](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/)) необязательно + </br> [QSC Q-SYS I/O USB Bridge](https://www.qsc.com/solutions-products/q-sys-ecosystem/audio-io-peripherals/io-usb-bridge/) необязательный | QSC Q-SYS Core, PTZ-IP-камера и USB-мост ввода-вывода: QSC Q-SYS Designer 9.0.1-2104.022 </br> Sennheiser TCC2 Потолочный микрофон: TCC2 - 1.5.1, Данте 1.2.0 </br> Усилители QSC: Н/Д </br> Громкоговорители серии QSC AcousticDesign: Н/Д | 
|[Vaddio IntelliSHOT-M](https://www.legrandav.com/products/cameras/hd_fixed_camera/intellishot-eptz-camera) | 1.0.0 |


&Dagger; Для этого набора можно использовать интерфейс Dante или сетевой коммутатор, рекомендованный Biamp/Sennheiser для этого пакета.

#### <a name="usb-extenders"></a>USB расширители

- USB-порты док-станций планшетов совместимы с USB 3.0. Вы можете использовать расширитель USB 2.x, но вы будете ограничены скоростями USB 2.x на дальнем конце. Такие расширители не рекомендуются для периферийных устройств USB 3.0.
- Расширитель должен соответствовать спецификациям USB 2.0 и более поздних версий.
  - Док-станции планшета поддерживают хотя бы две стадии внешнего расширения USB-концентратора. При подключении более двух USB-концентраторов в ряд, уточните у производителя док-станции, поддерживает ли она подключение ряда.
  - Проводное подключение GbE в комнате. Кабель Ethernet соответствующей длины.
  - До двух дисплеев с разрешением 1080p с подключениями HDMI. Кабели HDMI соответствующей длины.

> [!NOTE]
> A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode. This feature is not supported on all TVs.
>
> Комнаты Microsoft Teams не используют клавиатуру. При необходимости администратор может использовать экранную клавиатуру. USB-клавиатура или мышь потребуются при создании образа устройства комнат Microsoft Teams.

В таблицах ниже представлены рекомендации в отношении периферийных устройств в соответствии с размером комнаты:

**Сертифицированные периферийные аудио-устройства комнат Microsoft Teams**

|Тип комнаты|Количество людей|Рекомендованное максимальное расстояние от микрофона до выступающего|
|:-----|:-----|:-----|
|**Фокус** <br/> 10' x 9'   |2–4  |1.5 м  |
|**Маленькое** <br/> 16' x 16'  |4–6  |2.0 м  |
|**Среднее** <br/> 18' x 20'  |6–12  |2.4 м  |
|**Большое** <br/> 15' x 32'  |12–16  |3 м <br/> Это расстояние также распространяется на область, охватываемую каждым подключенным микрофоном.  |

**Сертифицированные периферийные видео-устройства комнат Microsoft Teams**

|Тип комнаты|Количество людей|
|:-----|:-----|
|**Фокус** <br/> 10' x 9'  |2–4  |
|**Маленькое** <br/> 16' x 16'  |4–6  |
|**Среднее** <br/> 18' x 20'  |6–12  |
|**Большое** <br/> 15' x 32'  |12–16  |

 > [!NOTE]
 > Разрешение экрана в передней части зала не должно превышать 1920x1080p.


## <a name="see-also"></a>См. также

[Обзор всех пакетов](https://products.office.com/microsoft-teams/across-devices/devices)

[Планирование комнат Microsoft Teams](rooms-plan.md)

[Развертывание комнат Microsoft Teams](rooms-deploy.md)

[Настройка консоли комнат Microsoft Teams](console.md)

[Управление комнатами Microsoft Teams](rooms-manage.md)
