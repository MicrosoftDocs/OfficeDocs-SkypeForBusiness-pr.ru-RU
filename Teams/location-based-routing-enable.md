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
description: Узнайте, как включить Location-Based для прямой маршрутации, в том числе включить ее для пользователей, сетевых сайтов, конфигураций шлюза и политик звонков.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d43d650384dd538ff481ac9625c15b9a9f420d95
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120580"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации

Прежде чем выполнять действия, которые следуют из этой статьи, прочитайте план Location-Based [Маршруты](location-based-routing-plan.md) для прямой маршрутинга и выполните действия, которые необходимо предпринять в статье "Настройка параметров сети для Location-Based [маршрутов".](location-based-routing-configure-network-settings.md)

В этой статье описано, как включить Location-Based для прямой маршрутинга. После развертывания прямой маршрутизации телефонной системы и настроив сетевые регионы, сайты и подсети, вы можете включить Location-Based маршрутизации. Для выполнения действий, которые вы найдете в этой статье, необходимо ознакомиться с cmdlets PowerShell. Дополнительные сведения см. в [обзоре Teams PowerShell.](teams-powershell-overview.md)

 Необходимо включить Location-Based для следующих экономий:
- Пользователи
- Сетевые сайты
- Конфигурации шлюза
- Политики звонков

Для этого можно [использовать Центр](#using-the-microsoft-teams-admin-center) администрирования Microsoft Team или [PowerShel](#using-powershell)l, чтобы Location-Based маршрутику.

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

### <a name="enable-location-based-routing-for-users"></a>Включить Location-Based маршрутии для пользователей

1. Создайте политику маршрутинга голосовой почты и назначьте политике использование услуг ННР. При назначении политик использования ННР убедитесь, что вы делаете одно из следующего:

    - Использование ННР, связанных с голосовой маршрутией, при использовании локального шлюза ННП на сайте.
    - Использование ННР, связанных с голосовой маршрутией, в которой используется шлюз ННР, расположенный в регионе, где Location-Based маршруты не нужны.
2. Назначьте политику маршрутики голосовой почты пользователям, которым требуются ограничения маршрутики.

Дополнительные информацию о создании политик голосовой маршрутии и их назначении пользователям см. в подмнося "Управление политиками маршрутинга голосовой [маршрутии в Microsoft Teams".](manage-voice-routing-policies.md)

### <a name="enable-location-based-routing-for-network-sites"></a>Включить Location-Based маршрутов для сетевых сайтов

В Location-Based включить маршрутную маршрутику для сайтов, для которые необходимо навести ограничения. Для этого в левой области навигации Центра администрирования Microsoft Teams перейдите в топологию сети расположений, выберите сетевой сайт, нажмите кнопку "Изменить" и включайте маршрутику на основе  >   **расположения.**   

Дополнительные узнать см. в [топологии "Управление сетью".](manage-your-network-topology.md)

### <a name="enable-location-based-routing-for-gateways"></a>Включить Location-Based маршрутов для шлюзов

В Location-Based перенастройку маршрутов шлюзам, которые перена маршрутируют вызовы на шлюзы STN, которые перена могут перенапорять вызовы на ПС, и связать сетевой сайт, на котором находится шлюз. 

1. В области навигации слева перейдите к маршруту **Voice** Direct Routing и выберите вкладку  >   **"SBCs".**
2. Выберите SBC и нажмите кнопку **"Изменить".** 
3. В **области "Маршрутизация на основе расположения" и "Оптимизация мультимедиа"** включите ее. 
4. Укажите ИД сайта шлюза, а затем укажите режим обхода.
5. Нажмите кнопку **Сохранить**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Включить Location-Based маршрутов для политик звонков

Чтобы принудительно Location-Based маршрутизов для определенных пользователей, установите для них политику звонков, чтобы запретить обход платных звонков по ДНР. Для этого включите параметр "Запретить платный **обход"** в политике звонков.

Подробнее см. в [политиках звонков в Teams.](teams-calling-policy.md)

## <a name="using-powershell"></a>С помощью PowerShell

### <a name="enable-location-based-routing-for-users"></a>Включить Location-Based маршрутии для пользователей

1. Для этого [используйте cmdlet Set-CsOnlinePstnUsage.](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) Для нескольких вариантов использования разделять каждое использование запятой.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Например:
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Используйте cmdlet [New-CsOnlineVoiceRoutingPolicy,](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) чтобы создать политику маршрутизации голоса, чтобы связать пользователя с соответствующими использованием ННР.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    При назначении использования ПС НН для политики голосовой маршрутки убедитесь, что вы делаете одно из следующих:
    - Использование ННР, связанных с голосовой маршрутией, при использовании локального шлюза STN на сайте
    - Использование ННР, связанных с голосовой маршрутией, в которой используется шлюз ННР, расположенный в регионе, где Location-Based маршруты не нужны.

    В этом примере мы создадим две новые политики маршрутинга голосовой связи и назначим им использование услуг ННР. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    В таблице ниже показаны политики маршрутинга голосовой связи, определенные в данном примере. 
    
    ||Политика маршрутинга голосовой почты 1|Политика маршрутинга голосовой почты 2|
    |---------|---------|---------|
    |Online voice policy ID   |Зауминая политика маршрутинга голосовой почты в Интернете   |Политика сетевой маршрутии голосовой почты    |
    |Использование сетевых услуг ННР  |Длинное расстояние  |Междугородние, локальные, внутренние  |

3. Используйте [cmdlet Grant-CsOnlineVoiceRoutingPolicy,](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) чтобы связать сетевые политики маршрутизации с пользователями, которым требуется навести ограничения маршрутизации.
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>Включить Location-Based маршрутов для сетевых сайтов

1.  Используйте командлет [Set-CsTenantNetworkSite,](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) чтобы включить Location-Based маршрутизации и связать политики голосовой маршрутизации с сетевыми сайтами, которые должны применять ограничения маршрутизации.
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    В этом примере мы Location-Based маршрутику для сайтов "Висяк" и "Приодерев". 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    В таблице ниже показаны сайты, для Location-Based маршрутов в этом примере.

    ||Сайт 1 (Висяк)  |Сайт 2 (Приокрет)  |
    |---------|---------|---------|
|Имя сайта    |Сайт 1 (Висяк)    |Сайт 2 (Приокрет)   
    |EnableLocationBasedRouting    |Верно    |Верно    |
    |Подсети     |Подсеть 1 (Ви2)     |Подсеть 2 (Приокрет)     |

### <a name="enable-location-based-routing-for-gateways"></a>Включить Location-Based маршрутов для шлюзов

1. С помощью [cmdlet new-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) можно создать конфигурацию шлюза для каждого шлюза или сайта сети. 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    Если с системой связано несколько шлюзов (например, шлюз или УАКС), измените каждый шлюз, чтобы включить Location-Based маршрутов. 

    В этом примере для каждого шлюза создается одна конфигурация. 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Дополнительные сведения см. [в сведениях о настройке прямой маршрутинга.](direct-routing-configure.md)
    
2. Используйте для этого Location-Based маршрутов шлюзов с помощью Location-Based [CSOnlinePSTNGateway.](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) 

    В Location-Based перенастройку маршрутов шлюзам, которые перена маршрутируют вызовы на шлюзы STN, которые перена могут перенапорять вызовы на ПС, и связать сетевой сайт, на котором находится шлюз.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    В этом примере мы Location-Based маршрутику для каждого шлюза, связанного со шлюзами ННР, на сайтах "Висяк" и "Висяк". 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    Не в Location-Based перенастройки шлюзов, которые не перена могут перенаупорять вызовы через ПСО. Однако вам все равно придется связать шлюз с сетевым сайтом, на котором расположена система. Это связано с темLocation-Based что для звонков по ПС, которые подключаются к конечным точкам, подключенным через этот шлюз, необходимо навести ограничения маршрутинга. В этом примере Location-Based для каждого шлюза, связанного с системами УАПС, на сайтах "Висячай" и "Подсистема" не включена маршрутка.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Включить Location-Based маршрутов для политик звонков

Чтобы принудительно Location-Based маршрутику для определенных пользователей, установите для них голосовую политику, чтобы запретить обход платных номеров ТСО. 

Используйте [cmdlet Grant-CsTeamsCallingPolicy,](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) чтобы Location-Based маршрутизации, предотвращая обход платных номеров ДНР.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
В этом примере мы предотвращаем обход платных номеров ННР в политиках звонков пользователя 1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Статьи по теме

- [Параметры сети для функций облачного голосового связи в Teams](cloud-voice-network-settings.md)