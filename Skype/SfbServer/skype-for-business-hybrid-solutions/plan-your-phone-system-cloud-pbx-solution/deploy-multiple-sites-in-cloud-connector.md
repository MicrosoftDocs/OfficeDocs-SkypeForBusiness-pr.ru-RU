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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Узнайте о развертывании нескольких сайтов PSTN в cloud Connector Edition.
ms.openlocfilehash: 7f771875605ffef130b430fd7c7a00d9d1a63873
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613769"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Развертывание нескольких сайтов в Cloud Connector

> [!Important] 
> Cloud Connector Edition завершится 31 июля 2021 г. вместе с Skype для бизнеса Online. После обновления организации Teams, узнайте, как подключить локальной телефонной сети к Teams с помощью прямой [маршрутизации](/MicrosoftTeams/direct-routing-landing-page).

Узнайте о развертывании нескольких сайтов PSTN в cloud Connector Edition.
  
В этом разделе описывается развертывание нескольких сайтов телефонной сети с общедоступными переключениями (PSTN). Сайты развертываются по одному, используя те же действия, что и развертывание одного сайта. В этом разделе описываются соображения и различия между сайтами в развертывании нескольких сайтов. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Несколько сайтов с общедоступными переключениями телефонной сети (PSTN)

Ниже показан пример конфигурации для развертывания Skype для бизнеса Cloud Connector Edition сайтов PSTN. Убедитесь, что параметры конфигурации правильны перед началом развертывания.
  
PSTN Site 1
  
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

PSTN Site 2
  
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

Для каждого сайта PSTN, который необходимо добавить, выполните действия в Развертывании одного сайта [в облачном соединителю.](deploy-a-single-site-in-cloud-connector.md)
  
> [!IMPORTANT]
> Общая папка для подготовки высокой доступности (HA) находится на сайте PSTN. Общая папка должна **быть** разной между сайтами PSTN. Не используйте ту же общую папку для нескольких сайтов.> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Единый сайт с высокой доступностью (HA) по сравнению с развертыванием на нескольких узлах
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

В следующей таблице перечислены различия между одним сайтом с поддержкой HA и нескольким развертыванием сайта.
  
|**Категория**|**Элемент**|**Одно-сайт с ha**|**Multi-Site**|
|:-----|:-----|:-----|:-----|
|Configure (Настроить)  <br/> |Имя хозяина устройства <br/> |**Разные** устройства <br/> |**Разные** для сайтов PSTN <br/> |
|Установка  <br/> |Общая папка  <br/> |Требуется та **же общая** папка для устройств <br/> |Требуется **разная общая** папка для устройств <br/> |
|Configure (Настроить)  <br/> |VirtualMachineDomain  <br/> |Требуется один **и тот же** домен для устройств <br/> |Требуется один **и тот же** домен на сайтах PSTN <br/> |
|Configure (Настроить)  <br/> |SIPDomains  <br/> |Доменные имена и порядок должны быть **одинаковыми** для всех устройств <br/> |Доменные имена и порядок должны быть **одинаковыми** на сайтах PSTN <br/> |
|Configure (Настроить)  <br/> |имя сайта.  <br/> |**То же самое** Имя сайта в устройствах <br/> |**Разные** Имя сайта на сайтах PSTN <br/> |
|Configure (Настроить)  <br/> |Имена серверов  <br/> |**Разные** устройства <br/> |**Разные** для сайтов PSTN <br/> |
|Configure (Настроить)  <br/> |Внутренние FQDNs пула  <br/> |**То же** самое в устройствах <br/> |**То же** самое на сайтах PSTN <br/> |
|Configure (Настроить)  <br/> |Внутренние IPs  <br/> |**Разные** устройства <br/> |**Разные** для сайтов PSTN <br/> |
|Configure (Настроить)  <br/> |Внешний FQDN  <br/> |**То же** самое в устройствах <br/> |**Разные** для сайтов PSTN <br/> |
|Configure (Настроить)  <br/> |Внешние IPs  <br/> |**Разные** устройства <br/> |**Разные** для сайтов PSTN <br/> |
|Configure (Настроить)  <br/> |Параметры GW PSTN  <br/> |**То же** самое в устройствах <br/> |**Разные** для сайтов PSTN <br/> |
|Configure (Настроить)  <br/> |Запись DNS  <br/> |Добавление записей с **одинаковыми** FQDNs внешнего доступа и **различными** IP-адресами <br/> |Добавление записей с **различными** FQDNs внешнего доступа и **различными** IP-адресами <br/> |
|Установка  <br/> |Гибридный клиент  <br/> |Настройка hybridPSTNSite  <br/> Установите peerDestination для отката  <br/> |Настройка hybridPSTNSite  <br/> Установите peerDestination для отката  <br/> |
|Установка  <br/> |Шлюз  <br/> |Сопоставление MS GW **M:N** на этом сайте <br/> |Шлюз PSTN на каждом сайте PSTN должен подключаться только к серверу-посреднику (s) на одном сайте.  <br/> |
|Установка  <br/> |Пользователь  <br/> |Настройка userPSTNSettings  <br/> |Настройка userPSTNSettings  <br/> |
