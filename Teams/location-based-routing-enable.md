---
title: Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Узнайте, как Location-Based маршрутизов для прямой маршрутации, в том числе для пользователей, сетевых сайтов, конфигураций шлюза и политик звонков.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dda26fafd48c56c11e2d6e085a1932a00307c64e96996bc30f22faaa80ed5639
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306391"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации

Прежде чем выполнять действия, которые вы выполните в этой статье, прочитайте статью [Планирование](location-based-routing-plan.md) маршрутов Location-Based для прямой маршрутии и выполните действия, которые можно сделать в статье Настройка сетевых параметров Location-Based [маршрутии.](location-based-routing-configure-network-settings.md)

В этой статье описано, как включить Location-Based для прямой маршрутии. После развертывания телефонная система прямой маршрутизации и настроив сетевые регионы, сайты и подсети, вы можете включить Location-Based маршрутизации. Для выполнения действий, которые вы найдете в этой статье, вам потребуется ознакомиться с помощью cmdlets PowerShell. Дополнительные сведения см. [в Teams PowerShell.](teams-powershell-overview.md)

 Для этого необходимо Location-Based маршрутику:
- Пользователи
- Сетевые сайты
- Конфигурации шлюза
- Политики звонков

Вы можете использовать [Центр администрирования Microsoft Team](#using-the-microsoft-teams-admin-center) или [PowerShel](#using-powershell)l, чтобы Location-Based маршрутику.

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

### <a name="enable-location-based-routing-for-users"></a>Включить Location-Based маршрутии для пользователей

1. Создайте политику маршрутинга голосовой почты и назначьте политике использование услуг STN. При назначении политикам использования ННР необходимо сделать одно из следующих:

    - Использование услуг STN, связанных с голосовой маршрутией, в которую используется локальный шлюз STN на сайте.
    - Использование услуг ННП, связанных с голосовой маршрутикой, в которой используется шлюз ННР, расположенный в регионе, где Location-Based маршруты не нужны.
2. Назначьте политику маршрутинга голосовой почты пользователям, для которых требуются ограничения маршрутики.

Дополнительные информацию о создании политик голосовой маршрутики и их назначении пользователям см. в [Microsoft Teams.](manage-voice-routing-policies.md)

### <a name="enable-location-based-routing-for-network-sites"></a>Включить Location-Based маршрутику для сетевых сайтов

В Location-Based включить маршрутную маршрутику для сайтов, для выполнения ограничений на маршрутивную маршрутику. Для этого в левой области навигации Центра администрирования Microsoft Teams перейдите в топологию сети расположений , выберите сетевой сайт, нажмите кнопку Изменить и включите маршрутику по  >   **расположению.**   

Дополнительные узнать см. в [управлении топологией сети.](manage-your-network-topology.md)

### <a name="enable-location-based-routing-for-gateways"></a>Включить Location-Based маршрутику для шлюзов

В Location-Based маршрутизов можно включить маршрутизовы шлюзов, которые перенаустанавлиют вызовы на шлюзы ПСС, которые перенанаустанавлиют вызовы на STN, и связать сетевой сайт, на котором находится шлюз. 

1. В левой области навигации перейдите в **voice**  >  **Direct Routing** и щелкните **вкладку SBCs.**
2. Выберите SBC и нажмите кнопку **Изменить**. 
3. В **области Маршрутизация на основе расположения и оптимизация мультимедиа** включите включить маршрутизация на основе **расположения**.
4. Укажите ИД сайта шлюза, а затем установите режим обхода.
5. Нажмите кнопку **Сохранить**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Включить Location-Based маршрутизов для политик звонков

Чтобы принудительно Location-Based маршрутизов для определенных пользователей, установите для них политику звонков, чтобы запретить обход платных звонков по ОКП. Для этого включите параметр Запретить платный **обход** в политике звонков.

Дополнительные информации см. в [Teams.](teams-calling-policy.md)

## <a name="using-powershell"></a>С помощью PowerShell

### <a name="enable-location-based-routing-for-users"></a>Включить Location-Based маршрутии для пользователей

1. Для этого используйте для этого [cmdlet Set-CsOnlinePstnUsage.](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) Для нескольких использования разделять каждое использование запятой.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Например:
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. С помощью [нового-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) создайте политику маршрутизации голосовой связи, чтобы связать пользователя с соответствующими использованием ОКП.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    При назначении использования услуг ННР политике голосовой маршрутии убедитесь, что вы делаете одно из следующих:
    - Использование службы STN, связанных с голосовой маршрутией, в сети с локальным шлюзом STN на сайте
    - Использование услуг ННП, связанных с голосовой маршрутикой, в которой используется шлюз ННР, расположенный в регионе, где Location-Based маршруты не нужны.

    В этом примере мы создадим две новые политики маршрутинга голосовой связи и назначим им использование услуг STN. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    В таблице ниже показаны политики маршрутии голосовой связи, определенные в данном примере. 
    
    ||Политика маршрутинга голосовой почты 1|Политика маршрутинга голосовой почты 2|
    |---------|---------|---------|
    |ИД голосовой политики в Интернете   |Политика маршрутистики голосовой почты в Интернете   |Политика маршрутистики голосовой почты в Интернете    |
    |Использование сетевых услуг STN  |Длинное расстояние  |Длинное расстояние, Локальное, Внутреннее  |

3. С помощью [cmdlet Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) можно связать политики маршрутизации голосовой сети с пользователями, для которых требуются ограничения маршрутизации.
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>Включить Location-Based маршрутику для сетевых сайтов

1.  С помощью [командлета Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) можно включить Location-Based маршрутизации и связать политики маршрутизации голосовой связи с сетевыми сайтами, которые должны применять ограничения маршрутизации.
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    В этом примере мы Location-Based маршрутику для сайта "Сова" и сайта "Омеровая система". 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    В следующей таблице показаны сайты, Location-Based маршруты в этом примере.

    ||Сайт 1 (вЕтвях)  |Сайт 2 (Кузьмина)  |
    |---------|---------|---------|
|Имя сайта    |Сайт 1 (вЕтвях)    |Сайт 2 (Кузьмина)   
    |EnableLocationBasedRouting    |Верно    |Верно    |
    |Подсети     |Подсеть 1 (Висяче)     |Подсеть 2 (Кузнецов)     |

### <a name="enable-location-based-routing-for-gateways"></a>Включить Location-Based маршрутику для шлюзов

1. Создайте конфигурацию шлюза для каждого шлюза или сайта сети с помощью [нового-CsOnlinePSTNGateway.](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    Если с системой связано несколько шлюзов (например, Шлюз или УАКС), измените каждый шлюз, чтобы включить Location-Based маршрутии. 

    В этом примере для каждого шлюза создается одна конфигурация. 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Дополнительные сведения см. [в этой ссылке.](direct-routing-configure.md)
    
2. Чтобы включить маршрутиз Location-Based шлюзов, которые должны применять ограничения маршрутизации, используйте Location-Based [Set-CSOnlinePSTNGateway.](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) 

    В Location-Based маршрутизов можно включить маршрутизовы шлюзов, которые перенаустанавлиют вызовы на шлюзы ПСС, которые перенанаустанавлиют вызовы на STN, и связать сетевой сайт, на котором находится шлюз.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    В этом примере мы Location-Based маршрутику для каждого шлюза, связанного со шлюзами ННП, на сайтах "Висяк" и "Омерверхи". 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    Не в Location-Based маршрутизов для шлюзов, которые не перенаустанавлиют вызовы в ОКП. Однако вам все равно придется связать шлюз с сетевым сайтом, на котором находится система. Это связано с темLocation-Based что для звонков по ДНР, которые находятся в конечных точках, подключенных с помощью этого шлюза, необходимо применять Location-Based маршрутизов. В этом примере Location-Based для каждого шлюза, связанного с системами УАКС, на сайтах "Висячая" и "Омеровая маршрутия".

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

Используйте для [этого](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) Location-Based маршрутизации, предотвращая обход платных номеров ОКП.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
В этом примере мы не мешаем обходу платных номеров ЗВОНКОВ через пользовательские политики звонков. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Статьи по теме

- [Параметры сети для облачных функций голосовой связи в Teams](cloud-voice-network-settings.md)