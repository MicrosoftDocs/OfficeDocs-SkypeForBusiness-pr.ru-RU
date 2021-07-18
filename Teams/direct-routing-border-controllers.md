---
title: Контроллеры границ сеанса, сертифицированные для прямой маршрутии
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: Администратор может узнать, какие контроллеры границ сеансов (SBCs) сертифицированы для прямой маршрутики.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 33df0f9d00d0c02d28c5f69ef26ae151586803d2
ms.sourcegitcommit: 9b794b579e57d478e5e4bd76b8ca79fdea6f90c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2021
ms.locfileid: "53465387"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>Список пограничных контроллеров сеансов, сертифицированных для прямой маршрутизации

Корпорация Майкрософт сотрудничает с рядом поставщиков пограничных контроллеров сеансов (SBC) и сертифицирует их контроллеры для работы с прямой маршрутизацией

Корпорация Майкрософт сотрудничает со всеми поставщиками, чтобы:

- Совместная работа над протоколами межсоединения SIP.
- Проводите активные тесты с помощью стороннее лабораторное тестирование. Сертифицированы только устройства, которые прошли тесты.
- Ежедневно проводите тесты со всеми сертифицированными устройствами в производственной и предварительной средах. проверка устройств в предварительных средах гарантирует, что новые версии кода прямой маршрутизации в облаке будут работать с сертифицированными контроллерами SBC;
- Создай совместную поддержку с поставщиками SBC.

  > [!NOTE]
  > Корпорация Майкрософт поддерживает телефонная система только в том случае, если сертифицированные устройства подключены через прямую маршрутику. Корпорация Майкрософт оставляет за собой право отклонить случаи поддержки, когда не сертифицированное устройство подключено к телефонная система прямой маршрутии. Если корпорация Майкрософт определяет, что проблема с прямой маршрутией клиента имеется в SBC-устройстве поставщика, клиенту потребуется привлечь его к поддержке.

Таблицы, которые следуют за устройствами списка, сертифицированными для прямой маршрутии. (Сведения о том, какие поставщики SBC [](direct-routing-media-optimization-configure.md)поддерживают оптимизацию локальных мультимедиа, см. в этой ссылке.

[Дополнительные сведения о прямой маршрутизации](https://aka.ms/dr).
Если у вас есть вопросы о программе сертификации SBC для прямой маршрутации, обратитесь в drsbccertification@microsoft.com.
<br/>

## <a name="certified-sbc-vendors"></a>Сертифицированные поставщики SBC

|                                                       Поставщик                                                        |       ПРОИЗВЕД       | Обход без мультимедиа | Обход мультимедиа | Версия программного обеспечения | 911 Service Provider Capable* | С возможностью ELIN |  
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|  
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  Поддерживаемая 7.20A.250 (рекомендуется 7.20A.258)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  Поддерживаемая 7.20A.250 (рекомендуется 7.20A.258)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  Поддерживаемая 7.20A.250 (рекомендуется 7.20A.258)   |   &#10004;   |  &#10004;  |
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  Поддерживаемая 7.20A.250 (рекомендуется 7.20A.258)   |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   Pending     |  Поддерживаемая 7.20A.250 (рекомендуется 7.20A.258)  |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 9000 SBC  |     &#10004;     |   &#10004;     |  Поддерживаемая 7.20A.250 (рекомендуется 7.20A.258)   | &#10004;     |  &#10004;  |
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  Поддерживаемая 7.20A.250 (рекомендуется 7.20A.258) |  &#10004;    |  &#10004;  |
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       Поддерживаемые 8.2 и 7.2 (рекомендуется 9.2)       | &#10004;   |     |
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       Поддерживаемые 8.2 и 7.2 (рекомендуется 9.2)       |   &#10004; |    |
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       Поддерживаемые 8.2 и 7.2 (рекомендуется 9.2)       |   &#10004;  | |
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       Поддерживаемые 8.2 и 7.2 (рекомендуется 9.2)       |    &#10004;  |  |
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       Поддерживаемые 8.2 и 7.2 (рекомендуется 9.2)          |  &#10004;    |    |
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x или 9.x     |   &#10004;  |  &#10004;     |
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x или 9.x     |   &#10004;   |     &#10004;     |
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x или 9.x    |   &#10004;    |     &#10004;     |
| | Ряд EdgeMarc |  &#10004; | | 15.6.1 | |  
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1.4       |     |    |
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      Поддерживаемая 3.20 (рекомендуется 4.0)        |  &#10004;    |  &#10004;   |
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   | &#10004; |      4.7 (4.9 для обхода мультимедиа)      |     |    |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     Cisco Unified Border Element (CUBE) для маршрутизаторов интегрированных служб 1000 рядов        |     &#10004;   | &#10004; |      Поддерживаемый IOS XE 17.2.1r (рекомендуется 17.3.2)         |    &#10004;     |   |  
|                                   |     Cisco Unified Border Element (CUBE) для маршрутизаторов интегрированных служб 4000 рядов        |     &#10004;   | &#10004; |   Поддерживаемый IOS XE 17.2.1r (рекомендуется 17.3.2)         |   &#10004;      |    |  
|                                   |     Cisco Unified Border Element (CUBE) for 1000V Series Cloud Services Router       |     &#10004;   | &#10004; |      Поддерживаемый IOS XE 17.2.1r (рекомендуется 17.3.2)         |    &#10004;     |    |  
|                                 |     Cisco Unified Border Element (CUBE) for 1000 Series Aggregation Services Routers      |     &#10004;   | &#10004; |      Поддерживаемый IOS XE 17.2.1r (рекомендуется 17.3.2)         |    &#10004;     |    |
|                                 |     Cisco Unified Border Element (CUBE) для Платформы Edge 8000      |     &#10004;   | &#10004; |      IOS XE 17.3.2      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    Av прогорная граница сеанса для Enterprise (ASBCE)    |     &#10004;     |       &#10004;     |       Выпуск 8.1.1 (8.1.2 для обхода мультимедиа)      |     |    |
|                     [Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Контроллер границы Сеанса Nokia    |     &#10004;     |           |       19.5 (1908)       |     |    |
|                     |    Контроллер границы Сеанса Nokia    |     &#10004;     |           |       20.8       |      &#10004;        |    |
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |           |       Поддерживаемая 5.0 (рекомендуется 5.1)     |     |    |
|                     [Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    |
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    Ссылка "Orchid"    |     &#10004;     |           |      3.1        |     |    |
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    Teams Sbc    |     &#10004;     |     &#10004;      |      1.6        |     |    |
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Atos Unify OpenScape Session Border Controller   |     &#10004;     |          |      10R1.2       |     |    |
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Enghouse Networks](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    Диалоговое окно BorderNet SBC   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [Patton Electronics Co.](https://www.patton.com/microsoft/)|    Глатон SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |
|                     [M5 Technologies (ранее — Media5 Corporation)](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|    Mediatrix Sentinel Series   |     &#10004;     |         |      DGW 48.0.2340 (рекомендуется DGW 48.1.2503)      |     |    |
|                     [Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|    Ekinops Session Border Controller (ONeSBC)   |     &#10004;     |     &#10004;     |      6.6.1m5ha1      |     |    |
|                     |    Контроллер границы виртуального сеанса Ekinops (ONEvSBC)   |     &#10004;     |    &#10004;      |      6.6.1m5ha1      |     |    |
|                     [46 Labs LLC](https://46labs.com/docs/hcvoice/teams/)|    Hyperconverged Voice   |     &#10004;     |         |      HCVoice 1.0.6       |     |    |

<br/>

* 911 поставщиков услуг

- [Маршрутия динамического расположения пропускной способности](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Служба маршрутинга экстренных служб Интрадо (ERS)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Шлюз для экстренного экстренного ситуация Intrado (EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
<br/>

## <a name="direct-routing-and-analog-devices-interoperability"></a>Прямое перенаправка и аналоговые устройства для обеспечения взаимосвязи

В следующей таблице перечислены устройства, которые проверены на interoperability между Direct Routing и Analog Devices.

|                                                       Поставщик                                                        |       ПРОИЗВЕД       | Проверить
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     | 
| [Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  ATA 191 Multiplatform Analog Telephone Adapter |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   Программное обеспечение AP1100 версии 8.3.0.1.2 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Программное обеспечение AP3900 версии 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Программное обеспечение AP4600 версии 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Программное обеспечение AP6300 версии 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Программное обеспечение AP6350 версии 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Программное обеспечение VME версии 8.3.0.1.2 |     &#10004;     |
| [Ленты](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000. Версия программного обеспечения: 8.1.1 (сборка 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Ленты](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000. Версия программного обеспечения: 8.1.1 (сборка 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  anynode с grandstream GXW42xx (V1.0.7.10) |     &#10004;     |
  
Чтобы предоставить нам отзывы о новых Teams, например идеи для новых функций, см. [uservoice.](https://microsoftteams.uservoice.com)


[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

Обратите внимание на сертификацию, предоставленную основной версии. Это означает, что поддерживается программное обеспечение с любым номером в версии SBC после основной версии.
