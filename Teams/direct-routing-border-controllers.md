---
title: Пограничные контроллеры сеансов, сертифицированные для прямой маршрутизации
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: Узнайте, какие пограничные контроллеры сеансов (SCS) были сертифицированы для прямой маршрутизации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3805a87171a770298e41337dfdd569c1b7d76985
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039997"
---
# <a name="session-border-controllers-certified-for-direct-routing"></a>Пограничные контроллеры сеансов, сертифицированные для прямой маршрутизации

Корпорация Майкрософт сотрудничает с рядом поставщиков пограничных контроллеров сеансов (SBC) и сертифицирует их контроллеры для работы с прямой маршрутизацией

Корпорация Майкрософт работает с каждым поставщиком для следующих действий:

- совместная работа над протоколами межсетевого взаимодействия SIP.
- выполнение интенсивных тестов в сторонней службе. Сертифицированы только устройства, которые прошли тесты.
- проведение ежедневных тестов на всех сертифицированных устройствах в рабочей и предварительной средах. проверка устройств в предварительных средах гарантирует, что новые версии кода прямой маршрутизации в облаке будут работать с сертифицированными контроллерами SBC;
- установка технической поддержки совместно с поставщиками SBC.

  > [!NOTE]
  > Корпорация Майкрософт поддерживает телефонную систему с прямой маршрутизацией только при использовании с сертифицированными устройствами. При возникновении проблем сначала обратитесь в службу поддержки клиентов вашего поставщика SBC. При необходимости поставщик SBC перенаправит проблему в Майкрософт по внутренним каналам. Корпорация Майкрософт оставляет за собой право отклонять запросы, направленные в службу поддержки, при подключении к телефонной системе несертифицированных устройств с прямой маршрутизацией. Если корпорация Майкрософт определяет, что проблема прямой маршрутизации клиента связана с устройством SBC поставщика, клиенту необходимо будет снова обратиться за поддержкой к поставщику SBC.
  >
  > Сертификация предоставляется определенным версиям встроенного ПО SBC. Любая версия встроенного ПО SBC, указанная ниже, является сертифицированной и поддерживаемой. Поддерживаются более поздние (чем указанные) версии встроенного ПО, если совпадает основной и дополнительный номер версии.
  >
  > Пример.
  >
  > - Поддерживается версия 6.10.258 — в этом случае корпорация Майкрософт поддерживает встроенное ПО версии 6.10.(258 или более поздних версий).
  > - Рекомендуется версия 6.20.100 — в этом случае корпорация Майкрософт рекомендует использовать версию 6.20.(100 или более позднюю версию).
  > - Чтобы узнать о поддержке конкретной версии, обратитесь к поставщику SBC.

В следующих таблицах перечислены устройства, сертифицированные для прямой маршрутизации. (Сведения о том, какие поставщики SBC поддерживают оптимизацию локальных файлов мультимедиа, см. в разделе [Настройка оптимизации локальных файлов мультимедиа для прямой маршрутизации](direct-routing-media-optimization-configure.md).)

[Дополнительные сведения о прямой маршрутизации](https://aka.ms/dr).
Если у вас есть вопросы по программе сертификации SBC для прямой маршрутизации, напишите нам по адресу drsbccertification@microsoft.com. Обратите внимание: мы не принимаем новые заявки на сертификацию до дополнительного уведомления.
<br/>

## <a name="certified-sbc-vendors"></a>Сертифицированные поставщики SBC

|                                                       Поставщик                                                        |       ПРОИЗВЕД       | Без обхода сервера-посредника | Обход сервера-посредника | Версия программного обеспечения | Поставщики службы 911* разрешены | С поддержкой ELIN |  
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|  
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  Поддерживается 7.20A.258 (рекомендуется 7.40A.250)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  Поддерживается 7.20A.258 (рекомендуется 7.40A.250)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  Поддерживается 7.20A.258 (рекомендуется 7.40A.250)   |   &#10004;   |  &#10004;  |
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  Поддерживается 7.20A.258 (рекомендуется 7.40A.250)   |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   &#10004;     |  Поддерживается 7.20A.250 (рекомендуется 7.40A.250)  |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 9000  SBC  |     &#10004;     |   &#10004;     |  Поддерживается 7.20A.258 (рекомендуется 7.40A.250)   | &#10004;     |  &#10004;  |
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  Поддерживается 7.20A.258 (рекомендуется 7.40A.250) |  &#10004;    |  &#10004;  |   
|                                                                                                                     | Mediant Cloud Edition SBC  |     &#10004;     |   &#10004;     |  Поддерживается 7.20A.258 (рекомендуется 7.40A.250) |  &#10004;    |  &#10004;  |
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       Поддерживаются: 9.2, 8.2 и 7.2 (рекомендуется 10.1)       | &#10004;   |     |
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       Поддерживаются: 9.2, 8.2 и 7.2 (рекомендуется 10.1)       |   &#10004; |    |
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       Поддерживаются: 9.2, 8.2 и 7.2 (рекомендуется 10.1)       |   &#10004;  | |
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       Поддерживаются: 9.2, 8.2 и 7.2 (рекомендуется 10.1)       |    &#10004;  |  |
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       Поддерживаются: 9.2, 8.2 и 7.2 (рекомендуется 10.1)          |  &#10004;    |    |
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x или 9.x     |   &#10004;  |  &#10004;     |
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x или 9.x     |   &#10004;   |     &#10004;     |
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x или 9.x    |   &#10004;    |     &#10004;     |
| | Серия EdgeMarc |  &#10004; | | 15.6.1 | |  
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1.4       |     |    |
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      Поддерживается 3.20 (рекомендуется 4.0)        |  &#10004;    |  &#10004;   |
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   | &#10004; |      4.7 (4.9 для обхода сервера-посредника)      | &#10004; | &#10004; |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     Cisco Unified Border Element (CUBE) для маршрутизаторов интегрированных служб серии 1000        |     &#10004;   | &#10004; |      Поддерживается IOS XE Amsterdam 17.2.1r (рекомендуется 17.6.1a)         |    &#10004;     |   |  
|                                   |     Cisco Unified Border Element (CUBE) для маршрутизаторов интегрированных служб серии 4000        |     &#10004;   | &#10004; |   Поддерживается IOS XE Amsterdam 17.2.1r (рекомендуется 17.6.1a)         |   &#10004;      |    |  
|                                   |     Cisco Unified Border Element (CUBE) для маршрутизатора облачных служб серии 1000V       |     &#10004;   | &#10004; |      Поддерживается IOS XE Amsterdam 17.2.1r (рекомендуется 17.3.3)         |    &#10004;     |    |  
|                                 |     Cisco Unified Border Element (CUBE) для маршрутизаторов служб агрегации серии 1000      |     &#10004;   | &#10004; |      Поддерживается IOS XE Amsterdam 17.2.1r (рекомендуется 17.6.1a)         |    &#10004;     |    |
|                                 |     Cisco Unified Border Element (CUBE) для пограничных платформ Catalyst 8000      |     &#10004;   | &#10004; |      Поддерживается IOS XE Amsterdam 17.3.2 (рекомендуется 17.6.1a)      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    Пограничный контроллер сеансов Avaya для предприятий (ASBCE)    |     &#10004;     |       &#10004;     |       Выпуск 8.1.1 (8.1.2 для обхода сервера-посредника)      |     |    |
|                     [Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Пограничный контроллер сеанса Nokia    |     &#10004;     |           |       19.5 (1908)       |     |    |
|                     |    Пограничный контроллер сеанса Nokia    |     &#10004;     |           |       20.8       |      &#10004;        |    |
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |      &#10004;     |       Поддерживаются: 5.0, 5.1 (рекомендуется 5.3)     |     |    |
|                     [Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    |
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    Ссылка Orchid    |     &#10004;     |           |      3.1        |     |    |
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    SBC Teams    |     &#10004;     |     &#10004;      |      1.6        |     |    |
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Пограничный контроллер сеансов Atos Unify OpenScape   |     &#10004;     |   &#10004;        |     V10R2.2.0     |     |    |
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Сети Enghouse](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    Пограничный контроллер сеансов Dialogic BorderNet   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [Patton Electronics Co.](https://www.patton.com/microsoft/)|    Patton SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |
|                     [M5 Technologies (прежнее название — Media5 Corporation)](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|    Серия Mediatrix Sentinel   |     &#10004;     |         |      DGW 48.0.2340 (рекомендуется DGW 48.1.2503)      |     |    |
|                     [Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|    Ekinops Session Border Controller (ONeSBC)   |     &#10004;     |     &#10004;     |      6.6.1m5ha1      |     |    |
|                     |    Ekinops Virtual Session Border Controller (ONEvSBC)   |     &#10004;     |    &#10004;      |      6.6.1m5ha1      |     |    |
|                     [46 Labs LLC](https://46labs.com/docs/hcvoice/teams/)|    Hyperconverged Voice   |     &#10004;     |     &#10004;      |      HCVoice 1.0.6       |     |    |

<br/>

\* **Поставщики услуг 911**

- [Маршрутизация динамического расположения пропускной способности](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Служба маршрутизации службы экстренной помощи (ERS) Intrado](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Шлюз экстренных служб Intrado (EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Inteliquent](https://www.inteliquent.com/services/emergency-services/e911)

<br/>

## <a name="support-for-local-media-optimization"></a>Поддержка оптимизации локальных файлов мультимедиа

В таблице ниже описано, какие поставщики SBC поддерживают [оптимизацию локальных файлов мультимедиа](direct-routing-media-optimization.md). 

| Поставщик | ПРОИЗВЕД |    Версия программного обеспечения |
|:------------|:-------|:-------|
| [Audiocodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    Mediant 500 SBC |   7.20A.256 | 
|            |  Mediant 800 SBC |   Поддерживается 7.20A.258 (рекомендуется 7.40A.100)  |  
|            |  Mediant 2600 SBC |  Поддерживается 7.20A.258 (рекомендуется 7.40A.100)  |  
|            |  Mediant 4000 SBC |  Поддерживается 7.20A.258 (рекомендуется 7.40A.100)  |  
|            |  Mediant 1000B SBC | Поддерживается 7.20A.258 (рекомендуется 7.40A.100)  |  
|            |  Mediant 9000 SBC |  Поддерживается 7.20A.258 (рекомендуется 7.40A.100)  |  
|            |  Mediant Virtual Edition SBC |   Поддерживается 7.20A.258 (рекомендуется 7.40A.100)  |  
|            |  Mediant Cloud Edition SBC | Поддерживается 7.20A.258 (рекомендуется 7.40A.100)  |
| [Ribbon SBC Core](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [Ribbon SBC Edge](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  SBC SWe Lite | 8.1.5 |
|               | SBC 1000 | 8.1.5  |
|               | SBC 2000 | 8.1.5  |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1+ |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |




## <a name="direct-routing-and-analog-devices-interoperability"></a>Прямая маршрутизация и взаимодействие аналоговых устройств

В следующей таблице перечислены устройства, проверенные на взаимодействие между прямой маршрутизацией и аналоговыми устройствами.

|                                                       Поставщик                                                        |       ПРОИЗВЕД       | Проверено
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     | 
| [Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  Многоплатформенный аналоговый телефонный адаптер ATA 191 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   Программное обеспечение AP1100 версии 8.3.0.1.2 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Программное обеспечение AP3900 версии 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Программное обеспечение AP4600 версии 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Программное обеспечение AP6300 версии 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Программное обеспечение AP6350 версии 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Программное обеспечение VME версии 8.3.0.1.2 |     &#10004;     |
| [Лента](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000. Версия программного обеспечения: 8.1.1 (сборка 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Лента](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000. Версия программного обеспечения: 8.1.1 (сборка 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Лента](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 302. Версия программного обеспечения: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Лента](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 304. Версия программного обеспечения: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Лента](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 2900A. Версия программного обеспечения: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Лента](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 4806. Версия программного обеспечения: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Лента](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 4808. Версия программного обеспечения: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Лента](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 6000. Версия программного обеспечения: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  anynode с Grandstream GXW42xx (V1.0.7.10) |     &#10004;     |
  

Обратите внимание на сертификат, предоставленный основной версии. Это означает, что поддерживается прошивка с любым номером во встроенном ПО пограничного контроллера сеансов, следующим за основной версией.

Чтобы оставить отзыв о Teams, например поделиться идеями новых функций, используйте [портал отзывов Майкрософт](https://feedbackportal.microsoft.com/).


