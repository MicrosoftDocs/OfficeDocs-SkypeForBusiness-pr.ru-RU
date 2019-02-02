---
title: Настройка параметров сети для маршрутизации на основе расположения
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Узнайте, как создать и настроить областей сети, сайты и подсети для маршрутизации на основе расположения для прямой маршрутизации.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: adb84f58c48292c13bd4af6f355f5e4da22458c9
ms.sourcegitcommit: 9f767b48e5f0eaf43869cba9c42ba3ba3225bcf6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2019
ms.locfileid: "29715479"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Настройка параметров сети для маршрутизации на основе расположения 

Если вы еще не сделано, чтение, чтобы просмотреть другие действия по [Plan Location-Based маршрутизации для непосредственного](location-based-routing-plan.md) необходимо выполнить перед развертыванием параметров сети для маршрутизации на основе местоположения.

В этой статье описывается настройка параметров сети для маршрутизации на основе местоположения. После развертывания прямой маршрутизации телефонной системы в вашей организации, следующие действия, чтобы создать и настроить областей сети, сетевых сайтов и подсетей. Чтобы выполнить действия, описанные в этой статье, вам потребуются некоторые навыки работы с помощью командлетов PowerShell. Для получения дополнительных сведений см [Команды PowerShell](teams-powershell-overview.md).

## <a name="define-network-regions"></a>Определение областей сети
 Область сети соединения различные части сети через несколько географических областей. Использование ``New-CsTenantNetworkRegion`` командлета PowerShell для определения области сети. Обратите внимание, что ``RegionID`` параметр — это логическое имя, которое представляет географический регион и не имеет зависимости или ограничения и ``CentralSite <site ID>`` это необязательный параметр. 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

В этом примере мы Создание области сети с именем Индия. 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>Определение сетевых узлов

Использование ``New-CsTenantNetworkSitePowerShell`` командлета PowerShell определение сетевых узлов. 

```
New-CsTenantNetworkSite -NetworkRegionID <region ID>  
```
В этом примере мы создадим два новых сетевых узлов, Delhi и Hyderabad в области Индия. 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
В следующей таблице показаны сетевых узлов, определенных в этом примере. 

||Узел 1 |Узел 2 |
|---------|---------|---------|
|Идентификатор сайта    |    Узел 1 (Delhi)     |  Узел 2 (Hyderabad)       |
|КОД региона  |     Область 1 (Индия)    |   Область 1 (Индия)      |

## <a name="define-network-subnets"></a>Определение подсетей

Использование ``New-Cs-TenantNetworkSubnet`` командлет, чтобы определить подсетей и связать их сетевых узлов. Каждый внутренней подсети может быть связано только с одного сайта. 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
В этом примере мы создадим связь между подсетью 192.168.0.0 и сетевым узлом Delhi и подсети 192.168.1.0 и Hyderabad сетевого узла.
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
В следующей таблице показаны подсетей, определенных в этом примере. 

||Узел 1 |Узел 2 |
|---------|---------|---------|
|Идентификатор подсети   |    192.168.0.0     |  192.168.1.0     |
|Маска  |     24    |   24      |
|Идентификатор сайта  | Сайт (Delhi) | Узел 2 (Hyderabad) |

Для нескольких подсетей можно импортировать в CSV-файл, используя следующий сценарий.
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
В этом примере CSV-файл выглядит примерно следующим образом:
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>Определить внешние подсети
Использование ``New-Cs-TenantTrustedIPAddress`` командлет, чтобы определить внешние подсети и назначить их к клиенту. Можно определить неограниченное число подсети для клиента. 
```
New-CsTenantTrustedIPAddress -IPAddress <Subnet IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
Например:
```
New-CsTenantTrustedIPAddress -IPAddress 192.168.0.1 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>Дальнейшие действия
Перейдите на [Включение зависимостью от расположения маршрутизации для непосредственного](location-based-routing-enable.md).

### <a name="related-topics"></a>Связанные разделы
- [Планирование зависимостью от расположения маршрутизации для непосредственного](location-based-routing-plan.md)
- [Терминология маршрутизации на основе расположения](location-based-routing-terminology.md)