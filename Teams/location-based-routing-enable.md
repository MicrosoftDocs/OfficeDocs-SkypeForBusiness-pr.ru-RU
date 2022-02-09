---
title: Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Узнайте, как Location-Based маршрутизов для прямой маршрутации, в том числе для пользователей, сетевых сайтов, конфигураций шлюза и политик звонков.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b2a3d74220b685be8a856dc2398b45d0002129ed
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457199"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации

В этой статье описано, как включить Location-Based для прямой маршрутии. Прежде чем выполнять действия, которые вы выполните в этой статье, прочитайте [](location-based-routing-plan.md) статью Location-Based Маршруты для прямой маршрутии и выполните действия, которые необходимо предпринять в статье Настройка параметров сети для Location-Based [маршрутии](location-based-routing-configure-network-settings.md).

 После развертывания прямой маршрутизации и настроив сетевые регионы, сайты и подсети, вы можете включить Location-Based маршрутизации. Для выполнения действий, которые вы выполните в этой статье, необходимо ознакомиться с помощью cmdlets PowerShell. Дополнительные сведения см. в [Teams PowerShell.](teams-powershell-overview.md)

 Для этого необходимо Location-Based маршрутику.

- Пользователи
- Сетевые сайты
- Конфигурации шлюза
- Политики звонков

Вы можете включить [Teams или](#using-the-microsoft-teams-admin-center) [PowerShell](#using-powershell), чтобы Location-Based маршрутику.

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

### <a name="enable-location-based-routing-for-users"></a>Включить Location-Based маршрутии для пользователей

1. Создайте политику маршрутинга голосовой почты и назначьте политике использование услуг STN. При назначении политик использования услуг ННР необходимо сделать одно из следующих:

    - Использование услуг STN, связанных с голосовой маршрутией, которые используют локальный шлюз STN на сайте.

    - Использование услуг ННП, связанных с голосовой маршрутикой, в которой используется шлюз ННР, расположенный в регионе, где Location-Based маршруты не нужны.

2. Назначьте политику маршрутинга голосовой почты пользователям, для которых требуются ограничения маршрутики.

Дополнительные информацию о создании политик голосовой маршрутии и их назначении пользователям см. в [Microsoft Teams.](manage-voice-routing-policies.md)

### <a name="enable-location-based-routing-for-network-sites"></a>Включить Location-Based маршрутику для сетевых сайтов

В Location-Based перенаустоять маршруты для сайтов, для которые необходимо навести ограничения на маршрутику. Для этого в левой области навигации Центра администрирования Microsoft Teams перейдите в топологию **LocationsNetwork** > , выберите сетевой сайт, нажмите кнопку Изменить и включите маршрутику по **расположению**.  

Дополнительные узнать см. в [этой теме](manage-your-network-topology.md).

### <a name="enable-location-based-routing-for-gateways"></a>Включить Location-Based маршрутов для шлюзов

В Location-Based маршрутизов можно включить маршрутизовы шлюзов, которые перенаустанавлиют вызовы на шлюзы ПСС, которые перенанаустанавлиют вызовы на STN, и связать сетевой сайт, на котором находится шлюз. 

1. В области навигации слева перейдите в **voiceDirect** >  Routing и щелкните **вкладку SBCs**.

2. Выберите SBC и нажмите кнопку **Изменить**. 

3. В **области Маршрутизация на основе расположения и оптимизация мультимедиа** включите включить маршрутизация **на основе расположения**.

4. Укажите ИД сайта шлюза, а затем установите режим обхода.

5. Нажмите кнопку **Сохранить**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Включить Location-Based маршрутизов для политик звонков

Чтобы принудительно Location-Based маршрутизов для определенных пользователей, установите для них политику звонков, чтобы запретить обход платных звонков по ОКП. Для этого включите параметр Запретить платный **обход** в политике звонков.

Дополнительные информации см. в [Teams](teams-calling-policy.md).

## <a name="using-powershell"></a>С помощью PowerShell

### <a name="enable-location-based-routing-for-users"></a>Включить Location-Based маршрутии для пользователей

1. Чтобы настроить использование ПСОП, используйте для этого cmdlet [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) . Для нескольких вариантов использования разделять каждое использование запятой.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```

    Например:

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```

2. Чтобы создать политику маршрутизации голосовой связи, чтобы связать пользователя с соответствующим использованием ОКП, воспользуйтесь помощью cmdlet [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) .

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    При назначении использования услуг ННР политике голосовой маршрутии убедитесь в том, что вы делаете одно из следующих:

    - Использование услуг STN, связанных с голосовой маршрутией, которые используют локальный шлюз STN на сайте.

    - Использование услуг ННП, связанных с голосовой маршрутикой, в которой используется шлюз ННР, расположенный в регионе, где Location-Based маршруты не нужны.

    В следующем примере создаются две новые политики маршрутинга голосовой почты и назначаются использование услуг ННП. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ``` 

    В таблице ниже показаны политики маршрутии голосовой связи, определенные в данном примере. 
    
    |&nbsp;|Политика маршрутинга голосовой почты 1|Политика маршрутинга голосовой почты 2|
    |---------|---------|---------|
    |ИД голосовой политики в Интернете   |Политика маршрутистики голосовой почты в Интернете   |Политика маршрутинга голосовой почты в Интернете    |
    |Использование сетевых услуг STN  |Длинное расстояние  |Длинное расстояние, Локальное, Внутреннее  |

3. Чтобы связать политики маршрутизации голосовой почты в Интернете с пользователями, для которых требуются ограничения маршрутизации, используйте для этого cmdlet [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) .

    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```

### <a name="enable-location-based-routing-for-network-sites"></a>Включить Location-Based маршрутику для сетевых сайтов

1. Чтобы включить Location-Based маршрутизации и связать политики голосовой маршрутизации с сетевыми сайтами, на которые необходимо навести ограничения, используйте командлет [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) .

    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    В этом примере Location-Based маршрутику для сайта "Совхода" и сайта "Обмер". 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    В следующей таблице показаны сайты, Location-Based маршруты в этом примере.

    |&nbsp;|Сайт 1 (вЕтвях)  |Сайт 2 (Кузьмина)  |
    |---------|---------|---------|
    |Имя сайта    |Сайт 1 (вЕтвях)    |Сайт 2 (Кузьмина)|
    |EnableLocationBasedRouting    |Верно    |Верно    |
    |Подсети     |Подсеть 1 (Висяче)     |Подсеть 2 (Кузнецов)     |


### <a name="enable-location-based-routing-for-gateways"></a>Включить Location-Based маршрутов для шлюзов

1. Чтобы создать конфигурацию шлюза для каждого шлюза или сетевого сайта, используйте для этого [cmdlet New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) . 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```

    Если с системой связано несколько шлюзов (например, Шлюз или УАКС), измените каждый шлюз, чтобы включить Location-Based маршрутии. 

    В следующем примере создается одна конфигурация шлюза для каждого шлюза. 

    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Дополнительные сведения см. [в этой ссылке](direct-routing-configure.md).
    
2. Чтобы включить Location-Based маршрутику для шлюзов, для выполнения ограничений на маршрутику используйте [cmdlet Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) . 

    В Location-Based маршрутизов можно включить маршрутизовы шлюзов, которые перенаустанавлиют вызовы на шлюзы ПСС, которые перенанаустанавлиют вызовы на STN, и связать сетевой сайт, на котором находится шлюз.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

   В следующем примере Location-Based маршрутику для каждого шлюза, связанного со шлюзами STN, на сайтах "Висяк" и "Подмалинник". 

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```

    Не в Location-Based маршрутизов для шлюзов, которые не перенана могут перенанапорять звонки на ДНР. Однако вам все равно придется связать шлюз с сетевым сайтом, на котором расположена система. Это связано с темLocation-Based что для звонков по ДНР, которые проходят через конечные точки, подключенные через этот шлюз, необходимо ввести ограничения на маршрутику. В этом примере Location-Based не включена для каждого шлюза, связанного с системами УАКС, на сайтах "Висячая" и "Подсистема".

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Включить Location-Based маршрутизов для политик звонков

Чтобы принудительно Location-Based маршрутику для определенных пользователей, установите для них голосовую политику, чтобы запретить обход платных номеров ТССК. 

Чтобы Location-Based маршрутизации, предотвращая обход платных номеров ОКП, используйте для этого cmdlet [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) .


```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```

В этом примере мы не мешаем обходу платных номеров ЗВОНКОВ через пользовательские политики звонков. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Статьи по теме

- [Параметры сети для облачных голосовых функций в Teams](cloud-voice-network-settings.md)