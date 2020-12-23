---
title: Включить для пользователей прямую маршрутику
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Узнайте, как включить прямую маршрутику по системе Microsoft Phone System.
ms.openlocfilehash: 5739797649c639e3259c6972da665ae0ced4b4bf
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655486"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Включить для пользователей прямую маршрутику, голосовую и голосовую почту

В этой статье описано, как включить для пользователей прямую маршрутику телефонной системы.  Это шаг 2 из следующих действий по настройке прямой маршрутинга:

- Шаг 1. [Подключение SBC к телефонной системе Майкрософт и проверка подключения](direct-routing-connect-the-sbc.md) 
- **Шаг 2. Включить для пользователей прямую маршрутику, голосовую и голосовую почту**   (в этой статье)
- Шаг 3. [Настройка голосовой маршрутии](direct-routing-voice-routing.md)
- Шаг 4. [Перевод чисел в альтернативный формат](direct-routing-translate-numbers.md) 


Сведения о всех шагах, необходимых для настройки прямой маршрутинга, см. в этой [ссылке.](direct-routing-configure.md)

Когда вы будете готовы включить прямую маршрутику для пользователей, выполните следующие действия: 

1. Создайте пользователя в Microsoft 365 или Office 365 и назначьте лицензию на телефонную систему. 
2. Убедитесь, что пользователь находится в Skype для бизнеса Online. 
3. Настройте номер телефона и в включить корпоративную голосовую и голосовую почту. 
4. Назначьте режим "Только Teams" пользователям.

## <a name="create-a-user-and-assign-the-license"></a>Создание пользователя и назначение лицензии 

Существует два варианта создания пользователя в Microsoft 365 или Office 365. Однако корпорация Майкрософт рекомендует использовать один из вариантов, чтобы избежать проблем с маршрутией: 

- Создайте пользователя в локальной службе Active Directory и синхронизируйте его с облаком. Узнайте, [как интегрировать свои локальное каталоги с Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- Создайте пользователя непосредственно в Центре администрирования Microsoft 365. См. ["Добавление пользователей по отдельности или массово в Microsoft 365 или Office 365 — справка для администраторов".](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec) 

Если ваши системы развертывания Skype для бизнеса Online сосуществят со Skype для бизнеса 2015 или локальной службой Lync 2010 или 2013, поддерживается только создание пользователя в локальной службе Active Directory и его синхронизация с облаком (вариант 1). 

Сведения о лицензионных требованиях см. в [лицензиях](direct-routing-plan.md#licensing-and-other-requirements) и других требованиях плана [прямой маршрутинга.](direct-routing-plan.md)

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>Убедитесь, что пользователь находится в сети и телефонные номера не синхронизируются из локальной сети (применимо к skype для бизнеса Server Корпоративная голосовая связь пользователей, переносимых в прямую маршрутинг Teams)

Прямая маршрутная маршрутия требует, чтобы пользователь был в интернете. Чтобы проверить это, обратитесь к параметру RegistrarPool, который должен иметь значение в infra.lync.com домене. Для параметра OnPremLineUriManuallySet также должно быть задано true. Для этого нужно настроить номер телефона и включить корпоративную голосовую и голосовую почту с помощью Skype для бизнеса Online PowerShell.

1. Подключите сеанс PowerShell в Skype для бизнеса Online.

2. Выдача команды: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    Если для onPremLineUriManuallySet задано число False и LineUri заполнен номером <E.164>, очистите параметры с помощью локальной оболочки управления Skype для бизнеса, прежде чем настраивать номер телефона с помощью Skype для бизнеса Online PowerShell. 

1. В командной оболочке Skype для бизнеса выдают команду: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   После синхронизации изменений с Office 365 ожидается `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` выход:

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Настройка номера телефона и включить корпоративную голосовую и голосовую почту 

После создания пользователя и назначенной лицензии необходимо настроить его номер телефона и голосовую почту. 

Чтобы добавить номер телефона и включить голосовую почту:
 
1. Подключите сеанс PowerShell в Skype для бизнеса Online. 

2. Выдача команды: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    Например, чтобы добавить номер телефона пользователя "Низкий", введите следующее: 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    Если у пользователей "Низкий" и "Стейки Квинн" одно и то же базовое число с уникальными расширениями, введите следующее:
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    Рекомендуется, но не обязательно, чтобы используемый номер телефона был настроен как полный номер телефона E.164 с кодом страны. Можно настроить номера телефонов с расширениями, которые будут использоваться для искомого пользователя, когда при подстройке для базового номера будет возвращено несколько результатов. Это позволяет компаниям настраивать номера телефонов с одинаковыми базовыми номерами и уникальными расширениями. Для успешного подстройки в приглашение должно быть включено полное число с расширением:
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > Если номер телефона пользователя управляется локально, настройте его с помощью локальной панели управления Skype для бизнеса или панели управления. 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>Настройка отправки звонков непосредственно на голосовую почту

Прямая маршрутия позволяет прекратить звонок пользователю и отправить его непосредственно в голосовую почту пользователя. Если вы хотите перенаправлять звонок напрямую в голосовую почту, вложите непрозрак=app:voicemail в закавляю URI запроса. Например: "sip:user@yourdomain.com;opaque=app:voicemail". В этом случае пользователь Teams не получит уведомление о вызове, звонок будет напрямую подключен к голосовой почте пользователя.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Назначение пользователям режима "Только teams", чтобы обеспечить доступ к звонкам в Microsoft Teams

Прямая маршрутка требует, чтобы пользователи были в режиме "Только Teams", чтобы входящие звонки направлялись в клиент Teams. Чтобы перейти в режим только Teams, назначьте им экземпляр UpgradeToTeams teamsUpgradePolicy. Дополнительные сведения см. в [руководстве по обновлению для ИТ-администраторов.](upgrade-to-teams-on-prem-overview.md) Если в вашей организации используется Skype для бизнеса Server или Skype для бизнеса Online, см. сведения о взаимодействиях между Skype и Teams в следующей статье: перенос и взаимодействия со Skype для [бизнеса.](migration-interop-guidance-for-teams-with-skype.md)

## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)

[Настройка прямой маршрутизации](direct-routing-configure.md)
