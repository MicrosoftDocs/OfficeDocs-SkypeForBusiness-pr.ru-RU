---
title: Настройка параметров сети для маршрутизации на основе расположения
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Сведения о том, как создавать и настраивать регионы сети, сайты и подсети для маршрутизации на основе местоположения для прямой маршрутизации.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240bbce48452edf505a61830891d0fcd6a6d199d
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570703"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Настройка параметров сети для маршрутизации на основе расположения

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

Если вы еще не сделали этого, прочтите [маршрут на основе местоположения для прямой маршрутизации](location-based-routing-plan.md) , чтобы просмотреть другие действия, которые необходимо выполнить перед настройкой сетевых параметров для маршрутизации на основе местоположения.

В этой статье описано, как настроить параметры сети для маршрутизации на основе местоположения. После развертывания прямой маршрутизации для телефонной системы в Организации следует создать и настроить регионы сети, сетевые сайты и сетевые подсети. Для выполнения действий, описанных в этой статье, вам потребуется ознакомиться с командлетами PowerShell. Дополнительные сведения можно найти в разделе [Общие сведения о Teams PowerShell](teams-powershell-overview.md).

## <a name="define-network-regions"></a>Определение регионов сети
 Сетевой регион соединяет различные части сети в нескольких географических регионах. Используйте командлет [New-кстенантнетворкрегион](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) , чтобы определить регионы сети. Обратите внимание, что параметр Регионид является логическим именем, которое представляет собой географию области и не имеет зависимостей или ограничений и &lt;не является&gt; обязательным параметром идентификатора сайта централсите. 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

В этом примере мы создаем сетевой регион с именем Индии. 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>Определение сетевых сайтов

С помощью командлета [New-кстенантнетворксите](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) можно определять сетевые сайты. 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
В этом примере мы создаем в регионе Индии две новые сетевые сайты, Делхи и Хидерабад. 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
В следующей таблице показаны сетевые сайты, определенные в этом примере. 

||Сайт 1 |Сайт 2 |
|---------|---------|---------|
|Идентификатор сайта    |    Сайт 1 (Делхи)     |  Сайт 2 (Хидерабад)       |
|КОД региона  |     Регион 1 (Индия)    |   Регион 1 (Индия)      |

## <a name="define-network-subnets"></a>Определение подсетей сети

С помощью командлета [New-кстенантнетворксубнет](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) можно определять сетевые подсети и связывать их с сетевыми сайтами. Каждая внутренняя подсеть может быть связана только с одним сайтом. 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
В этом примере мы создаем связь между подсетью 192.168.0.0 и сетевым сайтом Делхи и между подсетью 2001:4898: E8:25:844E: 926f: 85ad: dd8e и на сайте Хидерабад Network.
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
В приведенной ниже таблице указаны подсети, определенные в этом примере. 

||Сайт 1 |Сайт 2 |
|---------|---------|---------|
|КОД подсети   |    172.16.0.0     |  2001:4898: E8:25:844E: 926f: 85ad: dd8e     |
|Маски  |     24    |   120      |
|Идентификатор сайта  | Сайт (Делхи) | Сайт 2 (Хидерабад) |

Если вы используете несколько подсетей, вы можете импортировать CSV-файл с помощью такого сценария, как описано ниже.
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
В этом примере CSV-файл выглядит примерно так:
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>Определение внешних подсетей
С помощью командлета [New-кстенанттрустедипаддресс](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) можно определять внешние подсети и назначать их клиентам. Вы можете определить неограниченное количество подсетей для клиента. 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
Например:
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>Дальнейшие действия
Перейдите к разделу [Включение маршрутизации на основе местоположения для прямой маршрутизации](location-based-routing-enable.md).

### <a name="related-topics"></a>Статьи по теме
- [Планирование маршрутизации на основе расположения для прямой маршрутизации](location-based-routing-plan.md)
- [Терминология маршрутизации на основе расположения](location-based-routing-terminology.md)
