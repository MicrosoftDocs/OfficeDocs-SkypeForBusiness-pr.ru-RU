---
title: Создание политик расположения в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: В этом разделе вы узнаете, как настроить расширенные политики расположения для экстренной службы (E9-1-1) в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 4230d6ac1a820cb9612d58b21a2e5b6ae36d8f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822549"
---
# <a name="create-location-policies-in-skype-for-business-server"></a>Создание политик расположения в Skype для бизнеса Server

В этом разделе вы узнаете, как настроить расширенные политики расположения для экстренной службы (E9-1-1) в Skype для бизнеса Server Корпоративная голосовая связь. 

Skype для бизнеса Server использует политику расположения, чтобы включить для клиентов Skype для бизнеса E9-1-1 во время регистрации клиента. Политика расположения содержит параметры, которые определяют порядок внедрения E9-1-1.. Дополнительные сведения [см.](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)в сведениях о планировании политик расположения для Skype для бизнеса Server.

Политики расположения определяются с помощью панели управления Skype для бизнеса или с помощью [cmdlet New-CsLocationPolicy.](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)

> [!NOTE]
> Skype для бизнеса Server теперь поддерживает конфигурацию нескольких номеров экстренных служб для клиента. If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](configure-multiple-emergency-numbers.md). 

Глобальную политику расположения можно редактировать, кроме того, можно создавать новые именованные политики расположения. Клиент получает глобальную политику, если он расположен не в подсети, для которой имеется связанная локальная политика, или если локальная политика не назначена ему напрямую. Именованные политики назначаются подсетям или пользователям. 

Чтобы создать политику расположения, следует использовать учетную запись, являющуюся членом группы RTCUniversalServerAdmins или административной роли CsVoiceAdministrator или обладает эквивалентными правами и разрешениями администратора.

Дополнительные сведения см. в сведениях [о планировании политик расположения для Skype для бизнеса Server.](../../plan-your-deployment/enterprise-voice-solution/location-policies.md) В этой процедуре используются политики расположения, определенные с помощью следующих значений. Полное описание параметров и значений cmdlet см. в описании [New-CsLocationPolicy.](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)


| **Элемент**                               | **Значение**                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EnhancedEmergencyServicesEnabled  <br/>   | **True** <br/>                                                                                                                                                                     |
| LocationRequired  <br/>                   | **Заявление об отказе от ответственности** <br/>                                                                                                                                                               |
| EnhancedEmergencyServiceDisclaimer  <br/> | Политика вашей компании требует задать расположение. В противном случае в экстренной ситуации соответствующие службы не смогут определить ваше расположение. Задайте расположение.  <br/> |
| UseLocationForE911Only  <br/>             | **False** <br/>                                                                                                                                                                    |
| PstnUsage  <br/>                          | **EmergencyUsage** <br/>                                                                                                                                                           |
| EmergencyDialString  <br/>                | **911** <br/>                                                                                                                                                                      |
| EmergencyDialMask  <br/>                  | **112** <br/>                                                                                                                                                                      |
| NotificationUri  <br/>                    | <strong>sip:security@litwareinc.com</strong> <br/>                                                                                                                                 |
| ConferenceUri  <br/>                      | <strong>sip:+14255550123@litwareinc.com</strong> <br/>                                                                                                                             |
| ConferenceMode  <br/>                     | **twoway** <br/>                                                                                                                                                                   |
| LocationRefreshInterval  <br/>            | **2** <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a>Создание политик расположения

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**

    > [!NOTE]
    > Командлет CsLocationPolicy завершится с ошибкой, если значение для параметра **PstnUsage** не будет содержаться в глобальном списке параметров PstnUsage.

2. Чтобы изменить глобальную политику расположения, можно дополнительно выполнить следующий командлет:

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. Выполните следующие действия, чтобы создать именованную политику расположения.

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. Выполните следующий командлет, чтобы применить именованную политику расположения, созданную в шаге 3, к политике пользователя.

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
