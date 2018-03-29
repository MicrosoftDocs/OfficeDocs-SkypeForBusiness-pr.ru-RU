---
title: Создание политик местоположения в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Прочтите сведения о настройке политик расположения экстренных служб (E9-1-1) в Скайп enhanced Business Server корпоративной голосовой связи.
ms.openlocfilehash: 7635199810e21f33bdbe30d5bf6f229987fa8c77
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="create-location-policies-in-skype-for-business-server-2015"></a>Создание политик местоположения в Skype для бизнеса Server 2015
 
Прочтите сведения о настройке политик расположения экстренных служб (E9-1-1) в Скайп enhanced Business Server корпоративной голосовой связи. 
  
Скайп для Business Server использует политику расположения для включения Скайп пользователей для E9-1-1 во время регистрации клиента. Политика расположения содержит параметры, которые определяют порядок реализации E911. Дополнительные сведения содержатся в разделе [планирование политики расположения для Скайп для Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).
  
Вы задаете политики расположения с помощью Скайп для панели управления бизнеса или с помощью командлета [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .
  
> [!NOTE]
> Скайп для Business Server теперь поддерживает конфигурации нескольких аварийного номера для клиента. Если вы хотите настроить несколько аварийного номера, необходимо выполнить сведения в [Планирование нескольких аварийного номера в Скайп для Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) и [настроить несколько аварийного номера в Скайп для бизнеса 2015](configure-multiple-emergency-numbers.md). 
  
Глобальную политику расположения можно редактировать, кроме того, можно создавать новые именованные политики расположения. Клиент получает глобальную политику, если он расположен не в подсети, для которой имеется связанная локальная политика, или если локальная политика не назначена ему напрямую. Именованные политики назначаются подсетям или пользователям.   
  
Чтобы создать политику расположения, следует использовать учетную запись, являющуюся членом группы RTCUniversalServerAdmins или административной роли CsVoiceAdministrator или обладает эквивалентными правами и разрешениями администратора.
  
Дополнительные сведения содержатся в разделе [планирование политики расположения для Скайп для Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md). Командлеты в этой процедуре используют заданную политику расположения и приведенные ниже значения. Полное описание командлета параметры и значения в разделе [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).
  
|**Элемент**|**Значение**|
|:-----|:-----|
|EnhancedEmergencyServicesEnabled  <br/> |**True** <br/> |
|LocationRequired  <br/> |**Заявление об отказе** <br/> |
|EnhancedEmergencyServiceDisclaimer  <br/> |Политика вашей компании требует задать расположение. В противном случае в экстренной ситуации соответствующие службы не смогут определить ваше расположение. Задайте расположение.  <br/> |
|UseLocationForE911Only  <br/> |**False** <br/> |
|Параметра PstnUsage  <br/> |**EmergencyUsage** <br/> |
|EmergencyDialString  <br/> |**911** <br/> |
|EmergencyDialMask  <br/> |**112** <br/> |
|NotificationUri  <br/> |**SIP:Security@litwareinc.com** <br/> |
|URI конференции  <br/> |**SIP:+14255550123@litwareinc.com** <br/> |
|ConferenceMode  <br/> |**twoway** <br/> |
|LocationRefreshInterval  <br/> |**2** <br/> |
   
### <a name="to-create-location-policies"></a>Создание политик расположения

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
    > [!NOTE]
    > Командлет CsLocationPolicy завершится с ошибкой, если значение для параметра **PstnUsage** не будет содержаться в глобальном списке параметров PstnUsage.
  
2. Чтобы изменить глобальную политику расположения, можно дополнительно выполнить следующий командлет:
    
   ```
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

   ```

3. Выполните следующие действия, чтобы создать именованную политику расположения.
    
   ```
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

   ```

4. Выполните следующий командлет, чтобы применить именованную политику расположения, созданную в шаге 3, к политике пользователя.
    
   ```
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```


