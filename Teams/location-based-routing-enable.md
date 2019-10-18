---
title: Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Сведения о том, как включить маршрутизацию на основе местоположения для прямой маршрутизации.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4acd03dfff78d5aae329492014b24e55b2f92ec9
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572026"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Перед выполнением действий, описанных в этой статье, убедитесь в том, что вы прочитали [маршрут на основе местоположения для прямой маршрутизации](location-based-routing-plan.md) и завершили этапы в разделе [Настройка сетевых параметров для маршрутизации на основе местоположения](location-based-routing-configure-network-settings.md).

В этой статье описано, как включить маршрутизацию на основе местоположения для прямой маршрутизации. После развертывания прямой маршрутизации на телефонную систему и настройки регионов сети, сайтов и подсетей вы можете включить маршрутизацию на основе местоположения. Для выполнения действий, описанных в этой статье, вам потребуется ознакомиться с командлетами PowerShell. Дополнительные сведения можно найти в разделе [Общие сведения о Teams PowerShell](teams-powershell-overview.md).

 Вы должны включить маршрутизацию на основе местоположения для указанных ниже вариантов.
- Пользователи
- Сетевые сайты
- Конфигурации шлюзов
- Политики звонков

## <a name="enable-location-based-routing-for-users"></a>Включение маршрутизации на основе местоположения для пользователей

1. Используйте командлет [Set-ксонлинепстнусаже](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) , чтобы настроить использование КТСОП. Для нескольких использований Разделяйте каждое использование запятыми.

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Например:
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. С помощью командлета [New-ксонлиневоицераутингполици](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) можно создать политику маршрутизации голосовой связи, связывающую пользователя с использованием соответствующих ресурсов PSTN.

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    При назначении политики голосовой маршрутизации параметров использования PSTN убедитесь, что вы выполняете одно из указанных ниже действий.
    - Использование PSTN, связанных с голосовыми маршрутами, которые используют локальный шлюз PSTN для сайта
    - Используйте PSTN, связанные с голосовыми маршрутами, которые используют шлюз PSTN, находящийся в регионе, где не требуются ограничения на маршрутизацию на основе местоположения.

    В этом примере мы создадим две новые политики голосовой маршрутизации и назначаем им использование PSTN. 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    В следующей таблице показаны политики маршрутизации голосовой связи, определенные в этом примере. 
    
    ||Политика маршрутизации голосовой связи 1|Политика маршрутизации голосовой связи 2|
    |---------|---------|---------|
    |КОД политики голосовой связи через Интернет   |Политика маршрутизации голосовой связи Делхи Online   |Политика маршрутизации голосовой связи Хидерабад Online    |
    |Использование сети PSTN  |Междугородные звонки  |Междугородный, локальный, внутренний  |

3. С помощью командлета [Grant-ксонлиневоицераутингполици](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) можно связать политики голосовой маршрутизации через Интернет с пользователями, которым требуются ограничения маршрутизации.
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>Включение маршрутизации на основе местоположения для сетевых сайтов
1.  Используйте командлет [Set-кстенантнетворксите](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) , чтобы включить маршрутизацию на основе местоположения и связать политики голосовой маршрутизации с сетевыми сайтами, которые должны применять ограничения маршрутизации.
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    В этом примере включается маршрутизация на основе местоположения для сайта Делхи и сайта Хидерабад. 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    В приведенной ниже таблице показаны сайты, для которых включена маршрутизация на основе местоположения в этом примере.

    ||Сайт 1 (Делхи)  |Сайт 2 (Хидерабад)  |
    |---------|---------|---------|
|Имя сайта    |Сайт 1 (Делхи)    |Сайт 2 (Хидерабад)   
    |енаблелокатионбаседраутинг    |Верно    |Верно    |
    |Подсети     |Подсеть 1 (Делхи)     |Подсеть 2 (Хидерабад)     |

## <a name="enable-location-based-routing-for-gateways"></a>Включение маршрутизации на основе местоположения для шлюзов
1. Используйте командлет [New-ксонлинепстнгатевай](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) для создания конфигурации шлюза для каждого шлюза или сайта сети. 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    Если несколько шлюзов связаны с системой (например, Gateway или УАТС), измените каждый из них, чтобы включить ограничения маршрутизации на основе местоположения. 

    В этом примере мы создадим одну конфигурацию шлюза для каждого шлюза. 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    Дополнительные сведения можно найти в разделе [Настройка прямого маршрута](direct-routing-configure.md).
    
2. Используйте командлет [Set-ксонлинепстнгатевай](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) , чтобы включить маршрутизацию на основе местоположения для шлюзов, которые должны применять ограничения маршрутизации. 

    Включите возможность маршрутизации на основе местоположения для шлюзов, которые направляют звонки на шлюзы PSTN, которые направляют звонки в КТСОП и связывают сетевой сайт, на котором расположен шлюз.

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    В этом примере включена маршрутизация на основе местоположения для каждого шлюза, связанного с шлюзами PSTN на сайтах Делхи и Хидерабад. 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    Не включайте маршрутизацию на основе местоположения для шлюзов, не направлять звонки в КТСОП. Однако вы по-прежнему должны ассоциировать шлюз с сетевым сайтом, на котором находится система. Это связано с тем, что для звонков по протоколу PSTN должны применяться ограничения на маршрутизацию на основе местоположения, связанные с конечными точками, которые подключены через этот шлюз. В этом примере маршрутизация на основе местоположения не включена для каждого шлюза, связанного с системами УАТС на сайтах Делхи и Хидерабад.

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    Конечные точки, подключенные к системам, не накладываемые на протокол PSTN (например, УАТС), имеют аналогичные ограничения в качестве конечных точек пользователей Teams, поддерживающих маршрутизацию на основе местоположения. Это означает, что эти пользователи могут выполнять и принимать звонки от пользователей Teams, независимо от местонахождения пользователя. Они также могут размещать и принимать звонки в другие системы, не находящиеся в сети PSTN (например, конечную точку, подключенную к другой УАТС) независимо от того, с какой сетевой страницей связана система. Для всех входящих звонков, исходящих звонков, передачи звонков и переадресации звонков, использующих конечные точки PSTN, будет применяться маршрутизация на основе местоположения. Эти звонки должны использовать только шлюзы PSTN, определенные как локальные для таких систем. 

    В приведенной ниже таблице показана настройка шлюза для четырех шлюзов на двух разных сетевых сайтах: два соединения с шлюзами PSTN и двумя подключенными к системам АТС. 

    ||гатевайсителбренаблед   |нетворкситеид  |
    |---------|---------|---------|
    |Пстнгатевай: шлюз 1 DEL-GW    |    Верно     |   Сайт 1 (Делхи)      |
    |Пстнгатевай: шлюз 2 ХИД-GW     |   Верно      |      Сайт 2 (Хидерабад)   |
    |Пстнгатевай: Gateway 3 Delete-УАТС    |    False     |     Сайт 1 (Делхи)    |
    |Пстнгатевай: шлюз 4 ХИД-УАТС    |    False     |    Сайт 2 (Хидерабад)     |

## <a name="enable-location-based-routing-for-calling-policies"></a>Включение маршрутизации на основе местоположения для политик звонков

Чтобы обеспечить возможность маршрутизации на основе местоположения для конкретных пользователей, настройте политику голосовой связи пользователей, чтобы предотвратить ОКТС платный звонок. 

Используйте командлет [Grant-кстеамскаллингполици](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) , чтобы включить маршрутизацию на основе местоположения, запретив бесплатный звонок без поддержки КТСОП.

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
В этом примере мы постараемся отключить платный звонок в политики User1's звонков. 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a>Статьи по теме
- [Планирование маршрутизации на основе расположения для прямой маршрутизации](location-based-routing-plan.md)
- [Настройка параметров сети для маршрутизации на основе расположения](location-based-routing-configure-network-settings.md)
- [Терминология маршрутизации на основе расположения](location-based-routing-terminology.md)
