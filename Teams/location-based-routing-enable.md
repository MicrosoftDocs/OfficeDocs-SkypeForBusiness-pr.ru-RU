---
title: Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Узнайте, как включить Location-Based для прямой маршрутизации, включая ее для пользователей, сетевых сайтов, конфигураций шлюза и политик звонков.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4039105fe27df6fa8acb3f14c0db076e56910403
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999324"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации

В этой статье описывается, как включить Location-Based для прямой маршрутизации. Прежде чем выполнять действия, описанные в этой статье, убедитесь, что вы ознакомились с планом [Location-Based](location-based-routing-plan.md) для прямой маршрутизации и выполнили действия, описанные в разделе " [Настройка](location-based-routing-configure-network-settings.md) параметров сети для Location-Based маршрутизации".

 После развертывания прямой маршрутизации и настройки сетевых регионов, сайтов и подсетей вы можете включить Location-Based маршрутизации. Для выполнения действий, описанных в этой статье, необходимо ознакомиться с командлетами PowerShell. Дополнительные сведения см. в [обзоре Teams PowerShell](teams-powershell-overview.md)

 Необходимо включить Location-Based маршрутизации для следующих действий:

- Пользователи
- Сетевые сайты
- Конфигурации шлюза
- Политики звонков

Вы можете использовать [Центр администрирования Teams](#using-the-microsoft-teams-admin-center) или [PowerShell](#using-powershell) , чтобы включить Location-Based маршрутизации.

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

### <a name="enable-location-based-routing-for-users"></a>Включение Location-Based маршрутизации для пользователей

1. Создайте политику маршрутизации голосовой связи и назначьте политике использование ТСОП. При назначении политик использования ТСОП убедитесь, что вы выполните одно из следующих действий:

    - Использование ТСОП, связанных с голосовым маршрутом, использующим локальный шлюз ТСОП на сайте.

    - Используйте параметры ТСОП, связанные с маршрутами голосовой связи, которые используют шлюз ТСОП, расположенный в регионе, Location-Based маршрутизации не требуются.

2. Назначьте политику маршрутизации голосовой связи пользователям, которым требуется принудительное применение ограничений маршрутизации.

Дополнительные сведения о том, как создавать политики маршрутизации голосовой связи и назначать их пользователям, см. в статье "Управление политиками маршрутизации голосовой связи [" в Microsoft Teams](manage-voice-routing-policies.md).

### <a name="enable-location-based-routing-for-network-sites"></a>Включение Location-Based маршрутизации для сетевых сайтов

Включите Location-Based маршрутизации для сайтов, которые должны применять ограничения маршрутизации. Для этого в левой области навигации Центра администрирования Microsoft Teams  >  перейдите к топологии сети расположений **, выберите** сетевой сайт, нажмите кнопку "Изменить **", а** затем включите маршрутизацию на основе **расположения.**  

Дополнительные сведения см. в [статье "Управление топологией сети"](manage-your-network-topology.md).

### <a name="enable-location-based-routing-for-gateways"></a>Включение Location-Based маршрутизации для шлюзов

Включите Location-Based к шлюзам, которые направляют вызовы к шлюзам ТСОП, которые направляют вызовы в ТСОП, и свяжите сетевой сайт, на котором расположен шлюз. 

1. В области навигации слева перейдите к **маршрутизации Voice** > **Direct** и перейдите на **вкладку SBCs** .

2. Выберите SBC и нажмите кнопку "Изменить **"**. 

3. В **разделе "Маршрутизация на основе расположения" и "Оптимизация мультимедиа**" включите включение **маршрутизации на основе расположения**.

4. Укажите идентификатор сайта шлюза, а затем задайте режим обхода.

5. Нажмите кнопку **Сохранить**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Включение Location-Based маршрутизации для политик вызовов

Чтобы обеспечить Location-Based маршрутизации для определенных пользователей, настройте политику звонков пользователя, чтобы предотвратить обход платных звонков по ТСОП. Для этого включите параметр "Запретить обход платных **звонков"** в политике вызова.

Дополнительные сведения см [. в разделе "Политики звонков" в Teams](teams-calling-policy.md).

## <a name="using-powershell"></a>С помощью PowerShell

### <a name="enable-location-based-routing-for-users"></a>Включение Location-Based маршрутизации для пользователей

1. Чтобы задать использование ТСОП, используйте [командлет Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) . Для нескольких вариантов использования разделите каждое использование запятой.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```

    Например:

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```

2. Чтобы создать политику маршрутизации голосовой связи, чтобы связать пользователя с соответствующим использованием ТСОП, используйте командлет [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) .

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    При назначении использования ТСОП политике маршрутизации голосовой связи убедитесь, что вы выполните одно из следующих действий:

    - Использование ТСОП, связанных с голосовым маршрутом, использующим локальный шлюз ТСОП на сайте.

    - Используйте параметры ТСОП, связанные с маршрутами голосовой связи, которые используют шлюз ТСОП, расположенный в регионе, Location-Based маршрутизации не требуются.

    В следующем примере создаются две новые политики маршрутизации голосовой связи и назначается использование ТСОП. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ``` 

    В следующей таблице показаны политики маршрутизации голосовой связи, определенные в этом примере. 
    
    |&nbsp;|Политика маршрутизации голосовой связи 1|Политика маршрутизации голосовой связи 2|
    |---------|---------|---------|
    |Идентификатор политики голосовой связи в Сети   |Политика сетевой маршрутизации голосовой связи   |Политика маршрутизации голосовой связи в Сети    |
    |Использование ТСОП в сети  |Длинное расстояние  |Long Distance, Local, Internal  |

3. Чтобы связать политики сетевой маршрутизации голосовой связи с пользователями, которым требуется принудительное применение ограничений маршрутизации, используйте командлет [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) .

    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```

### <a name="enable-location-based-routing-for-network-sites"></a>Включение Location-Based маршрутизации для сетевых сайтов

1. Чтобы включить Location-Based маршрутизации и связать политики маршрутизации голосовой связи с сетевыми сайтами, которые должны применять ограничения маршрутизации, используйте командлет [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) .

    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    В этом примере Location-Based маршрутизации для сайта "Саули" и сайта "Окремент". 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    В следующей таблице показаны сайты, для которых Location-Based маршрутизации в этом примере.

    |&nbsp;|Сайт 1 (Индия)  |Сайт 2 (Сша)  |
    |---------|---------|---------|
    |Имя сайта    |Сайт 1 (Индия)    |Сайт 2 (Сша)|
    |EnableLocationBasedRouting    |Верно    |Верно    |
    |Подсети     |Подсеть 1 (Индия)     |Подсеть 2 (Кузнечик)     |


### <a name="enable-location-based-routing-for-gateways"></a>Включение Location-Based маршрутизации для шлюзов

1. Чтобы создать конфигурацию шлюза для каждого шлюза или сетевого сайта, используйте командлет [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) . 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```

    Если с системой связано несколько шлюзов (например, шлюз или УАТС), измените каждый шлюз, чтобы включить Location-Based маршрутизации. 

    В следующем примере создается одна конфигурация шлюза для каждого шлюза. 

    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Дополнительные сведения см. в [разделе "Настройка прямой маршрутизации"](direct-routing-configure.md).
    
2. Чтобы включить Location-Based для шлюзов, которые должны применять ограничения маршрутизации, используйте командлет [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) . 

    Включите Location-Based к шлюзам, которые направляют вызовы к шлюзам ТСОП, которые направляют вызовы в ТСОП, и свяжите сетевой сайт, на котором расположен шлюз.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

   В следующем примере Location-Based маршрутизации для каждого шлюза, связанного со шлюзами ТСОП, на сайтах "Приостановка". 

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```

    Не включите Location-Based для шлюзов, которые не направляют вызовы в ТСОП. Однако вам по-прежнему придется связать шлюз с сетевым сайтом, на котором находится система. Это связано с Location-Based маршрутизации для вызовов ТСОП, которые достигают конечных точек, подключенных через этот шлюз. В этом примере Location-Based маршрутизация не включена для каждого шлюза, связанного с системами УАТС на сайтах Порезов и Премента.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Включение Location-Based маршрутизации для политик вызовов

Чтобы обеспечить Location-Based маршрутизации для определенных пользователей, настройте политику голосовой связи пользователей, чтобы запретить обход платных ТСОП. 

Чтобы включить Location-Based маршрутизации, предотвращая обход платных ТСОП, используйте командлет [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) .


```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```

В этом примере мы запрещаем обход платных ТСОП политикам звонков User1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>См. также

- [Параметры сети для функций облачной голосовой связи в Teams](cloud-voice-network-settings.md)