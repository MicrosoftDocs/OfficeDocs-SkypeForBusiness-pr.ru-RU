---
title: Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Сведения о том, как включить маршрутизацию на основе местоположения для прямой маршрутизации, в том числе включать ее для пользователей, сетевые сайты, конфигурации шлюза и политики звонков.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4daf270dcd67dc732bba5e5fe134d5a0994dcd75
ms.sourcegitcommit: 2295a668a6f118b95f010e81150351741572b076
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412646"
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

Вы можете использовать [центр администрирования Microsoft Teams](#using-the-microsoft-teams-admin-center) или [PowerShel](#using-powershell)l для включения маршрутизации на основе местоположения.

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

### <a name="enable-location-based-routing-for-users"></a>Включение маршрутизации на основе местоположения для пользователей

1. Создайте политику маршрутизации голосовой связи и назначьте ей использование PSTN. После назначения политике использования PSTN убедитесь в том, что вы выполняете одно из указанных ниже действий.

    - Использование PSTN, связанных с голосовыми маршрутами, которые используют локальный шлюз PSTN для сайта.
    - Используйте PSTN, связанные с голосовыми маршрутами, которые используют шлюз PSTN, находящийся в регионе, где не требуются ограничения на маршрутизацию на основе местоположения.
2. Назначьте политику маршрутизации голосовых сообщений пользователям, которым требуется применить ограничения маршрутизации.

Чтобы узнать больше о том, как создавать политики голосовой маршрутизации и назначать их пользователям, ознакомьтесь со статьей [Управление политиками голосовой маршрутизации в Microsoft Teams](manage-voice-routing-policies.md).

### <a name="enable-location-based-routing-for-network-sites"></a>Включение маршрутизации на основе местоположения для сетевых сайтов

Включите маршрутизацию на основе местоположения для сайтов, для которых необходимо применить ограничения маршрутизации. Для этого на левой панели навигации в центре администрирования Microsoft Teams перейдите в раздел **Расположение**  >  **топологии сети**, выберите сайт сети, нажмите кнопку **изменить**, а затем включите **маршрутизацию на основе расположения**.  

Дополнительные сведения можно найти в разделе [Управление топологией сети](manage-your-network-topology.md).

### <a name="enable-location-based-routing-for-gateways"></a>Включение маршрутизации на основе местоположения для шлюзов

Включите возможность маршрутизации на основе местоположения для шлюзов, которые направляют звонки на шлюзы PSTN, которые направляют звонки в КТСОП и связывают сетевой сайт, на котором расположен шлюз. 

1. На панели навигации слева перейдите к **Voice**  >  **перенаправлению**голосовой почты, а затем откройте вкладку **SBCs** .
2. Выделите SBC и нажмите кнопку **изменить**. 
3. В разделе **Оптимизация маршрутизации и мультимедиа с учетом расположения**включите **параметр включить маршрутизацию на основе местоположения**.
4. Укажите идентификатор сайта шлюза, а затем настройте режим пропуска.
5. Нажмите кнопку **Сохранить**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Включение маршрутизации на основе местоположения для политик звонков

Чтобы обеспечить возможность маршрутизации на основе местоположения для конкретных пользователей, настройте политику звонков пользователя, чтобы отключить платный звонок. Для этого включите параметр **запретить платный звонок** в политике звонков.

Дополнительные сведения можно найти [в разделе политики вызова в Teams](teams-calling-policy.md).

## <a name="using-powershell"></a>Использование PowerShell

### <a name="enable-location-based-routing-for-users"></a>Включение маршрутизации на основе местоположения для пользователей

1. Используйте командлет [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) , чтобы настроить использование КТСОП. Для нескольких использований Разделяйте каждое использование запятыми.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Например:
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. С помощью командлета [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) можно создать политику маршрутизации голосовой связи, связывающую пользователя с использованием соответствующих ресурсов PSTN.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    При назначении политики голосовой маршрутизации параметров использования PSTN убедитесь, что вы выполняете одно из указанных ниже действий.
    - Использование PSTN, связанных с голосовыми маршрутами, которые используют локальный шлюз PSTN для сайта
    - Используйте PSTN, связанные с голосовыми маршрутами, которые используют шлюз PSTN, находящийся в регионе, где не требуются ограничения на маршрутизацию на основе местоположения.

    В этом примере мы создадим две новые политики голосовой маршрутизации и назначаем им использование PSTN. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    В следующей таблице показаны политики маршрутизации голосовой связи, определенные в этом примере. 
    
    ||Политика маршрутизации голосовой связи 1|Политика маршрутизации голосовой связи 2|
    |---------|---------|---------|
    |КОД политики голосовой связи через Интернет   |Политика маршрутизации голосовой связи Delhi Online   |Политика маршрутизации голосовой связи Hyderabad Online    |
    |Использование сети PSTN  |Междугородные звонки  |Междугородный, локальный, внутренний  |

3. С помощью командлета [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) можно связать политики голосовой маршрутизации через Интернет с пользователями, которым требуются ограничения маршрутизации.
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>Включение маршрутизации на основе местоположения для сетевых сайтов

1.  Используйте командлет [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) , чтобы включить маршрутизацию на основе местоположения и связать политики голосовой маршрутизации с сетевыми сайтами, которые должны применять ограничения маршрутизации.
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    В этом примере включается маршрутизация на основе местоположения для сайта Delhi и сайта Hyderabad. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    В приведенной ниже таблице показаны сайты, для которых включена маршрутизация на основе местоположения в этом примере.

    ||Сайт 1 (Delhi)  |Сайт 2 (Hyderabad)  |
    |---------|---------|---------|
|Имя сайта    |Сайт 1 (Delhi)    |Сайт 2 (Hyderabad)   
    |EnableLocationBasedRouting    |Верно    |Верно    |
    |Подсети     |Подсеть 1 (Delhi)     |Подсеть 2 (Hyderabad)     |

### <a name="enable-location-based-routing-for-gateways"></a>Включение маршрутизации на основе местоположения для шлюзов

1. Используйте командлет [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) для создания конфигурации шлюза для каждого шлюза или сайта сети. 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    Если несколько шлюзов связаны с системой (например, Gateway или УАТС), измените каждый из них, чтобы включить ограничения маршрутизации на основе местоположения. 

    В этом примере мы создадим одну конфигурацию шлюза для каждого шлюза. 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Дополнительные сведения можно найти в разделе [Настройка прямого маршрута](direct-routing-configure.md).
    
2. Используйте командлет [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) , чтобы включить маршрутизацию на основе местоположения для шлюзов, которые должны применять ограничения маршрутизации. 

    Включите возможность маршрутизации на основе местоположения для шлюзов, которые направляют звонки на шлюзы PSTN, которые направляют звонки в КТСОП и связывают сетевой сайт, на котором расположен шлюз.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    В этом примере включена маршрутизация на основе местоположения для каждого шлюза, связанного с шлюзами PSTN на сайтах Delhi и Hyderabad. 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    Не включайте маршрутизацию на основе местоположения для шлюзов, не направлять звонки в КТСОП. Однако вы по-прежнему должны ассоциировать шлюз с сетевым сайтом, на котором находится система. Это связано с тем, что для звонков по протоколу PSTN должны применяться ограничения на маршрутизацию на основе местоположения, связанные с конечными точками, которые подключены через этот шлюз. В этом примере маршрутизация на основе местоположения не включена для каждого шлюза, связанного с системами УАТС на сайтах Delhi и Hyderabad.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Включение маршрутизации на основе местоположения для политик звонков

Чтобы обеспечить возможность маршрутизации на основе местоположения для конкретных пользователей, настройте политику голосовой связи пользователей, чтобы предотвратить ОКТС платный звонок. 

Используйте командлет [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) , чтобы включить маршрутизацию на основе местоположения, запретив бесплатный звонок без поддержки КТСОП.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
В этом примере мы постараемся отключить платный звонок в политики User1's звонков. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Статьи по теме

- [Параметры сети для функций голосовой связи в облаке в Teams](cloud-voice-network-settings.md)
