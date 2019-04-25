---
title: Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Узнайте, как включить маршрутизации на основе расположения для прямой маршрутизации.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: e68b239d00e67d942f80a259facb87c80ddf2a55
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245256"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Прежде чем выполнять действия, описанные в этой статье, убедитесь, что вы чтение [Plan Location-Based маршрутизации для прямого](location-based-routing-plan.md) и выполнить действия, описанные в [настроить параметры сети для маршрутизации на основе местоположения](location-based-routing-configure-network-settings.md).

В этой статье описывается, как включить маршрутизации на основе расположения для прямой маршрутизации. После развертывания прямой маршрутизации телефонной системы и настройка области сети, сайтов и подсетей, вы готовы для включения маршрутизации на основе местоположения. Чтобы выполнить действия, описанные в этой статье, вам потребуются некоторые навыки работы с помощью командлетов PowerShell. Для получения дополнительных сведений см [Команды PowerShell](teams-powershell-overview.md).

 Вам необходимо включить зависимостью от расположения маршрутизации для следующих:
- Пользователи
- Сетевые узлы
- Шлюзов
- Вызов политик

## <a name="enable-location-based-routing-for-users"></a>Включение маршрутизации на основе расположения для пользователей

1. Командлет [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) случаев использования PSTN. Для нескольких вариантов использования разделяются запятыми каждого использования.

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Например:
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Командлет [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) используется для создания политики маршрутизации голосовой связи, чтобы связать пользователя с соответствующих случаев использования PSTN.

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    При назначении политики маршрутизации голосовых данных случаев использования PSTN, убедитесь, что вы выполните одно из следующих:
    - Используйте случаев использования PSTN, связанный со маршрутов голосовых вызовов, которые используют локального шлюза ТСОП для сайта
    - С помощью использования ТСОП, связанный со маршрутов голосовых вызовов, использующих шлюз ТСОП, расположенной в области, где ограничений на основе местоположения маршрутизации не требуется.

    В этом примере мы создайте две новые политики маршрутизации голосовых данных и назначать им случаев использования PSTN. 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    В следующей таблице показаны политики маршрутизации голосовой связи, определенных в этом примере. 
    
    ||Политики маршрутизации 1 голосовой связи|Политики маршрутизации 2 голосовой связи|
    |---------|---------|---------|
    |Идентификатор политики голосовой связи через Интернет   |Delhi политики маршрутизации голосовой связи через Интернет   |Hyderabad политики маршрутизации голосовой связи через Интернет    |
    |Online использования ТСОП  |Междугородный  |Междугородный, локальные, внутренний  |

3. Командлет [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) связывание маршрутизации политики сети голосовой связи для пользователей, которым требуется маршрутизации ограничения вступили в силу.
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>Включение маршрутизации на основе расположения для сетевых узлов
1.  Командлет [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) для включения маршрутизации на основе расположения и связать политики маршрутизации голосовых данных на сайтах сети, которые необходимо применить ограничения по маршрутизации.
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    В этом примере мы Включение маршрутизации на основе расположения для узла Delhi и Hyderabad сайта. 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    Ниже указаны сайты, включены для маршрутизации на основе расположения в следующем примере.

    ||Узел 1 (Delhi)  |Узел 2 (Hyderabad)  |
    |---------|---------|---------|
|Имя сайта    |Узел 1 (Delhi)    |Узел 2 (Hyderabad)   
    |EnableLocationBasedRouting    |True    |True    |
    |Подсети     |Подсеть 1 (Delhi)     |Подсеть 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-gateways"></a>Включение маршрутизации на основе расположения для шлюзов
1. Командлет [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) используется для создания конфигурации шлюза для каждого шлюза или сетевого узла. 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    Если несколько шлюзов, связанные с системой (например, шлюзом или УАТС), измените каждый шлюз для включения ограничений на основе местоположения маршрутизации. 

    В этом примере мы создадим одной конфигурации шлюза для каждого шлюза. 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    Дополнительные сведения можно [Настроить прямой маршрутизации](direct-routing-configure.md).
    
2. Командлет [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) используется для включения маршрутизации на основе расположения для вашей шлюзов, которые необходимо применить ограничения по маршрутизации. 

    Включение маршрутизации на основе расположения для шлюзов, которые маршрутизации вызовов для шлюзов PSTN, маршрутизировать вызовы в ТСОП и сопоставить сетевого узла, где находится шлюз.

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    В этом примере мы Включение маршрутизации на основе расположения для каждого шлюза, сопоставленные для шлюзов ТСОП на веб-сайтах Delhi и Hyderabad. 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    Не Включение маршрутизации на основе расположения для шлюзов, которые не маршрутизировать вызовы в ТСОП. Тем не менее необходимо связать шлюза для сетевого узла, где расположена система. Это из-за ограничений на основе местоположения маршрутизации должны применяться для вызовов ТСОП достигает конечные точки, подключенные через этот шлюз. В этом примере зависимостью от расположения маршрутизации не включен для каждого шлюза, содержащего АТС на веб-сайтах Delhi и Hyderabad.

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    Конечные точки, подключенные к системам, которые не маршрутизировать вызовы в ТСОП (например, УАТС) будут иметь аналогичные ограничения как конечных точек пользователям группы с поддержкой маршрутизации на основе местоположения. Это означает, что эти пользователи могут выполнять и принимать вызовы, связанные с группами пользователей независимо от расположения пользователя. Пользователь может звонить и принимать звонки, чтобы и других систем, которые не маршрутизировать вызовы Телефонной сети общего пользования (например, конечную точку, подключенный к УАТС различных) независимо от сетевого узла, с которым связана системы. Все входящие вызовы, исходящие вызовы, перевод звонков и переадресацию звонков, связанных с конечными точками PSTN будет использоваться принудительным ограничением маршрутизации на основе местоположения. Эти вызовы необходимо использовать только шлюзы ТСОП, определенные как локальный для таких систем. 

    В следующей таблице показаны настройки шлюза четыре шлюзов в двух различных сетевых сайтов: два, подключенных к шлюзы ТСОП и по два подключенных к УАТС. 

    ||GatewaySiteLbrEnabled   |NetworkSiteID  |
    |---------|---------|---------|
    |DEL PstnGateway:Gateway 1-Себестоимости    |    True     |   Узел 1 (Delhi)      |
    |PstnGateway:Gateway 2 HYD-Себестоимости     |   True      |      Узел 2 (Hyderabad)   |
    |DEL PstnGateway:Gateway 3-УАТС    |    False     |     Узел 1 (Delhi)    |
    |HYD PstnGateway:Gateway 4-УАТС    |    False     |    Узел 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-calling-policies"></a>Включение маршрутизации на основе расположения для вызова политик

Для применения параметров маршрутизации на основе расположения для отдельных пользователей, настройте политику голосовой связи пользователей, чтобы запретить международную PTSN обхода. 

Командлет [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) используется для включения маршрутизации на основе местоположения, устраняя PSTN международную сервера-посредника.

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
В этом примере мы запретить PSTN международную сервера-посредника для пользователя User1 вызов политик. 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a>Статьи по теме
- [Планирование маршрутизации на основе расположения для прямой маршрутизации](location-based-routing-plan.md)
- [Настройка параметров сети для маршрутизации на основе расположения](location-based-routing-configure-network-settings.md)
- [Терминология маршрутизации на основе расположения](location-based-routing-terminology.md)
