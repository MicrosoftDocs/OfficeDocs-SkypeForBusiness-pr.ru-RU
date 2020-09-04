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
description: Сведения о развертывании нескольких сайтов PSTN в Cloud Connector Edition.
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358925"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Развертывание нескольких сайтов в Cloud Connector

> [!Important] 
> Cloud Connector Edition выйдет 31 июля 2021 вместе со Skype для бизнеса Online. После обновления вашей организации до Teams Узнайте, как подключить локальную телефонную сеть к Teams с помощью [прямой маршрутизации](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Сведения о развертывании нескольких сайтов PSTN в Cloud Connector Edition.
  
В этом разделе описывается развертывание нескольких сайтов телефонной сети общего пользования (PSTN). Сайты развертываются по одному, используя те же действия, что и развертывание одного сайта. В этом разделе описываются вопросы и различия между сайтами в развертывании с несколькими сайтами. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Несколько сайтов телефонной сети общего пользования (PSTN)

Ниже показан пример конфигурации для развертывания Skype для бизнеса Cloud Connector Edition для разных сайтов PSTN. Прежде чем приступать к развертыванию, убедитесь, что параметры конфигурации верны.
  
PSTN-сайт 1
  
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

PSTN-сайт 2
  
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

Для каждого добавляемого сайта PSTN выполните действия, описанные в разделе [развертывание одного сайта в Cloud Connector](deploy-a-single-site-in-cloud-connector.md).
  
> [!IMPORTANT]
> Общая папка для подготовки высокой доступности (HA) — на сайте PSTN. Общая папка **должна** быть разной между сайтами PSTN. Не используйте одну и ту же общую папку для нескольких сайтов. > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Один сайт с высокой доступностью (HA) по сравнению с развертыванием с несколькими сайтами
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

В следующей таблице перечислены различия между отдельными сайтами с поддержкой высокой доступности и развертыванием нескольких сайтов.
  
|**Категория**|**Элемент**|**Один сайт с высокой доступностью**|**Несколько сайтов**|
|:-----|:-----|:-----|:-----|
|Настройка  <br/> |Имя узла устройства <br/> |**Разные для разных** устройств <br/> |**Разный** для сайтов PSTN <br/> |
|Настройка  <br/> |Общая папка  <br/> |Требуется **одна и та же** общая папка для всех устройств <br/> |Требуется **другая** общая папка для разных устройств <br/> |
|Настройка  <br/> |виртуалмачинедомаин  <br/> |Требуется **один и тот же** домен для устройств <br/> |Требуется **один** домен для сайтов PSTN <br/> |
|Настройка  <br/> |сипдомаинс  <br/> |Имена и порядок доменов должны быть **одинаковыми** для всех устройств <br/> |Имена и порядок доменов должны быть **одинаковы** для сайтов PSTN <br/> |
|Настройка  <br/> |имя сайта.  <br/> |**То же самое** Имя сайта для разных устройств <br/> |**Разные** Имя сайта на сайтах PSTN <br/> |
|Настройка  <br/> |Имена серверов  <br/> |**Разные для разных** устройств <br/> |**Разный** для сайтов PSTN <br/> |
|Настройка  <br/> |Полные доменные имена внутреннего пула  <br/> |**Одинаково** для разных устройств <br/> |**Одинаково** на сайтах PSTN <br/> |
|Настройка  <br/> |Внутренние IP-адреса  <br/> |**Разные для разных** устройств <br/> |**Разный** для сайтов PSTN <br/> |
|Настройка  <br/> |Внешнее полное доменное имя  <br/> |**Одинаково** для разных устройств <br/> |**Разный** для сайтов PSTN <br/> |
|Настройка  <br/> |Внешние IP-адреса  <br/> |**Разные для разных** устройств <br/> |**Разный** для сайтов PSTN <br/> |
|Настройка  <br/> |Параметры PSTN GW  <br/> |**Одинаково** для разных устройств <br/> |**Разный** для сайтов PSTN <br/> |
|Настройка  <br/> |Запись DNS  <br/> |Добавление записей с **одинаковыми** полными доменными именами внешнего доступа и **разными** IP-адресами <br/> |Добавление записей с **различными** полными доменными именами внешнего доступа и **разными** IP-адресами <br/> |
|Настройка  <br/> |Гибридный клиент  <br/> |Set задайте hybridpstnsite  <br/> Set параметр peerdestination для резервного  <br/> |Set задайте hybridpstnsite  <br/> Set параметр peerdestination для резервного  <br/> |
|Настройка  <br/> |Шлюз  <br/> |Сопоставление **M:N** MS GW на этом сайте <br/> |Шлюзы PSTN на каждом сайте PSTN должны подключаться только к серверам-посредникам на том же сайте.  <br/> |
|Настройка  <br/> |Пользователь  <br/> |Set Усерпстнсеттингс  <br/> |Set Усерпстнсеттингс  <br/> |
   

