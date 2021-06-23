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
description: Узнайте, как включить для Телефон (Майкрософт) прямой маршрутии Системы.
ms.openlocfilehash: 7d2b7c4b5d6268d1498a47537e0edbbf892198aa
ms.sourcegitcommit: cae94cd5761baafde51aea1137e6d164722eead9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53075372"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Включить для пользователей прямую маршрутику, голосовую и голосовую почту

В этой статье описано, как включить для телефонная система прямую маршрутику.  Это шаг 2 из следующих действий по настройке прямой маршрутии:

- Шаг 1. [Подключение SBC с Телефон (Майкрософт) и проверьте подключение](direct-routing-connect-the-sbc.md) 
- **Шаг 2. Включить для пользователей прямую маршрутику, голосовую и голосовую почту**   (эта статья)
- Шаг 3. [Настройка голосовой маршрутии](direct-routing-voice-routing.md)
- Шаг 4. [Перевод чисел в альтернативный формат](direct-routing-translate-numbers.md) 


Сведения о всех действиях, необходимых для настройки прямой маршрутистики, см. в этой [ссылке.](direct-routing-configure.md)

Когда вы будете готовы включить прямую маршрутику для пользователей, выполните следующие действия: 

1. Создайте пользователя в Microsoft 365 или Office 365 и назначьте телефонная система лицензию. 
2. Убедитесь, что пользователь находится в Skype для бизнеса Online. 
3. Настройте номер телефона и в включить корпоративную голосовую и голосовую почту. 
4. Назначьте Teams режим только пользователям.

## <a name="create-a-user-and-assign-the-license"></a>Создание пользователя и назначение лицензии 

Существует два варианта создания нового пользователя в Microsoft 365 или Office 365. Однако корпорация Майкрософт рекомендует вашей организации выбрать один из вариантов, чтобы избежать проблем с маршрутией: 

- Создайте пользователя в локальной службе Active Directory и синхронизируйте его с облаком. См. [интеграцию локального каталога с Azure Active Directory.](/azure/active-directory/connect/active-directory-aadconnect)
- Создайте пользователя непосредственно в Центр администрирования Microsoft 365. См. добавление пользователей по отдельности или массово [в Microsoft 365 или Office 365 — справка для администраторов.](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec) 

Если развертывание Skype для бизнеса Online сосуществовает с локальной Skype для бизнеса 2015 или Lync 2010 или 2013, единственным вариантом является создание пользователя в локальной службе Active Directory и синхронизация пользователя с облаком (вариант 1). 

Сведения о требованиях к лицензиям см. [в лицензировании](direct-routing-plan.md#licensing-and-other-requirements) и других требованиях в [области Планирование прямой маршрутии.](direct-routing-plan.md)

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>Убедитесь, что пользователь находится в Сети и телефонные номера не синхронизируются из локальной сети (применимо для пользователей Skype для бизнеса Server Корпоративная голосовая связь с поддержкой переноса в Teams Direct Routing)

Прямая маршрутная маршрутия требует, чтобы пользователь был домашним в Интернете. Чтобы проверить это, обратитесь к параметру RegistrarPool, который должен иметь значение в infra.lync.com домене. Для параметра OnPremLineUriManuallySet также должно быть задано true. Для этого нужно настроить номер телефона и включить корпоративную голосовую и голосовую почту с Skype для бизнеса PowerShell.

1. Подключение сеанс Skype для бизнеса Online PowerShell.

2. Выдай команду: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    Если для параметра OnPremLineUriManuallySet задано число False, а для параметра LineUri используется номер <E.164>, очистите параметры с помощью локальной оболочки Skype для бизнеса Management Shell, прежде чем настраивать номер телефона с помощью Skype для бизнеса Online PowerShell. 

1. Команда Skype для бизнеса командной оболочки: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   После синхронизации изменений с Office 365 ожидаемым `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` выходом будет:

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Настройка номера телефона и включить корпоративную голосовую и голосовую почту 

После создания пользователя и назначенной лицензии необходимо настроить его номер телефона и голосовую почту. 

Чтобы добавить номер телефона и включить голосовую почту:
 
1. Подключение сеанс Skype для бизнеса Online PowerShell. 

2. Выдай команду: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    Например, чтобы добавить номер телефона пользователя "Низкий уровень", введите следующую запись: 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    Если у пользователей "Низкий уровень" и "Стейси Квинн" одинаковые базовые номера с уникальными расширениями, введите следующее:
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1001" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1002" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    Рекомендуется, но не обязательно, чтобы используемый номер телефона был настроен как полный номер телефона E.164 с кодом страны. Поддерживается настройка номеров телефонов с расширениями, которые будут использоваться для искомых пользователей, если при подступе к базовому номеру возвращается несколько результатов. Это позволяет компаниям настраивать номера телефонов с одинаковым базовым номером и уникальными расширениями. Для успешного подстроки в приглашении должно быть включено полное число с расширением:
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > Если номер телефона пользователя управляется локально, настройте его с помощью локальной Skype для бизнеса или панели управления. 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>Настройка отправки звонков непосредственно на голосовую почту

Прямая маршрутия позволяет прекратить звонок и отправить его непосредственно в голосовую почту пользователя. Если вы хотите отправить звонок непосредственно в голосовую почту, вложите непрозрачной=app:voicemail в заглавный URI запроса. Например, "sip:user@yourdomain.com;opaque=app:voicemail". В этом случае Teams не получит уведомление о вызове, звонок будет напрямую подключен к голосовой почте пользователя.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Назначьте Teams режим только пользователям, чтобы обеспечить доступ к звонкам Microsoft Teams

Прямая маршрутия требует, чтобы Teams режиме только для входящих звонков в клиенте Teams маршрутизов. Чтобы перейти в Teams, назначьте им экземпляр UpgradeToTeams TeamsUpgradePolicy. Дополнительные сведения см. в [стратегии обновления для ИТ-администраторов.](upgrade-to-teams-on-prem-implement.md) Если в вашей организации используется Skype для бизнеса Server или Skype для бизнеса Online, см. статью о взаимосвязи между Skype и [Teams:](migration-interop-guidance-for-teams-with-skype.md)миграция и взаимодействия с Skype для бизнеса.

## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)

[Настройка прямой маршрутизации](direct-routing-configure.md)
