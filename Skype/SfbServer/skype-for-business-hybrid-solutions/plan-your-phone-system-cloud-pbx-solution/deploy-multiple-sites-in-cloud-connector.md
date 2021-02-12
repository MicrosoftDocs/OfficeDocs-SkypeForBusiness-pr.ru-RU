---
title: Развертывание нескольких сайтов в Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Узнайте о развертывании нескольких сайтов PSTN в Cloud Connector Edition.
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358925"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Развертывание нескольких сайтов в Cloud Connector

> [!Important] 
> Выпуск Cloud Connector Edition завершится 31 июля 2021 г. вместе со Skype для бизнеса Online. После обновления вашей организации до Teams узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутизации.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Узнайте о развертывании нескольких сайтов STN в Cloud Connector Edition.
  
В этом разделе описывается развертывание нескольких сайтов телефонной сети общего чения (PSTN). Сайты развертываются по одному, используя те же действия, что и при развертывании одного сайта. В этом разделе описываются вопросы и различия между сайтами в развертывании с несколькими сайтами. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Несколько сайтов телефонной сети общего ского ского уровня (PSTN)

Ниже показан пример конфигурации для развертывания Skype для бизнеса Cloud Connector Edition для разных сайтов ЗВОНКОВ. Перед началом развертывания убедитесь, что параметры конфигурации правильны.
  
Сайт STN 1
  
```console
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

Сайт STN 2
  
```console
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

Для каждого сайта STN, который нужно добавить, выполните действия, которые необходимо развернуть в [Cloud Connector.](deploy-a-single-site-in-cloud-connector.md)
  
> [!IMPORTANT]
> Общая папка для подготовки высокой доступности (HA) находится на сайте STN. Общая папка должна **быть** разной между сайтами STN. Не используйте общую папку для нескольких сайтов.> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Один сайт с высокой доступностью по сравнению с развертываниями с несколькими сайтами
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

В следующей таблице перечислены различия между одним сайтом с поддержкой ha и развертыванием нескольких сайтов.
  
|**Категория**|**Элемент**|**Один сайт с ha**|**Multi-Site**|
|:-----|:-----|:-----|:-----|
|Настройка  <br/> |Имя хоста устройства <br/> |**Разные устройства** <br/> |**Разные** для разных сайтов STN <br/> |
|Настройка  <br/> |Общая папка  <br/> |Требуется та **же общая** папка на разных устройствах <br/> |Требуется другая **общая** папка на разных устройствах <br/> |
|Настройка  <br/> |VirtualMachineDomain  <br/> |Требуется один и **тот же** домен для всех устройств <br/> |Требуется один и **тот же** домен на сайтах STN <br/> |
|Настройка  <br/> |SIPDomains  <br/> |Доменные имена и порядок должны быть **одинаковыми** для всех устройств <br/> |Доменные имена и порядок должны быть **одинаковыми** на сайтах STN <br/> |
|Настройка  <br/> |имя сайта.  <br/> |**То же самое** Имя сайта на разных устройствах <br/> |**Разные** Имя сайта на сайтах STN <br/> |
|Настройка  <br/> |Имена серверов  <br/> |**Разные устройства** <br/> |**Разные** для разных сайтов STN <br/> |
|Настройка  <br/> |FQDNs внутреннего пула  <br/> |**Одинаково для** всех устройств <br/> |**То же** самое на сайтах STN <br/> |
|Настройка  <br/> |Внутренние IPS  <br/> |**Разные устройства** <br/> |**Разные** для разных сайтов STN <br/> |
|Настройка  <br/> |Внешнее FQDN  <br/> |**Одинаково для** всех устройств <br/> |**Разные** для разных сайтов STN <br/> |
|Настройка  <br/> |Внешние IPS  <br/> |**Разные устройства** <br/> |**Разные** для разных сайтов STN <br/> |
|Настройка  <br/> |Параметры PSTN GW  <br/> |**Одинаково для** всех устройств <br/> |**Разные** для разных сайтов STN <br/> |
|Настройка  <br/> |Запись DNS  <br/> |Добавление записей  с одинаковыми FQDNs внешнего доступа и **разными** IP-адресами <br/> |Добавление записей **с** разными FQDNs внешнего доступа и **разными** IP-адресами <br/> |
|Настройка  <br/> |Гибридный клиент  <br/> |Настройка HybridPSTNSite  <br/> Настройка peerDestination для отката  <br/> |Настройка HybridPSTNSite  <br/> Настройка peerDestination для отката  <br/> |
|Настройка  <br/> |Шлюз  <br/> |Сопоставление MS GW **M:N** на этом сайте <br/> |Шлюзы STN на каждом сайте STN должны подключаться только к серверам-посредникам на одном сайте  <br/> |
|Настройка  <br/> |Пользователь  <br/> |Set UserPSTNSettings  <br/> |Set UserPSTNSettings  <br/> |
   

