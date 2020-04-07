---
title: Разрешить пользователям прямую маршрутизацию
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
description: Сведения о том, как включить прямую маршрутизацию для пользователей Microsoft Phone System.
ms.openlocfilehash: 10c62d14f283d565765a47e4c07504bc9bffa720
ms.sourcegitcommit: 0fdc60840f45ff5b0a39a8ec4a21138f6cab49c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2020
ms.locfileid: "43160063"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Предоставление пользователям прямой маршрутизации, голоса и голосовой почты

В этой статье описано, как разрешить пользователям использовать прямую маршрутизацию телефонной системы.  Это шаг 2 описанных ниже действий для настройки прямой маршрутизации.

- Шаг 1. [Соединение SBC с телефонной системой Microsoft и проверка соединения](direct-routing-connect-the-sbc.md) 
- **Шаг 2. Предоставление пользователям прямой маршрутизации, голоса и голосовой почты** (в этой статье)
- Шаг 3. [Настройка голосовой маршрутизации](direct-routing-voice-routing.md)
- Шаг 4. [Перевод чисел в альтернативный формат](direct-routing-translate-numbers.md) 


Сведения о всех шагах, необходимых для настройки прямой маршрутизации, приведены в статье [Настройка прямого маршрута](direct-routing-configure.md).

Когда вы будете готовы предоставить пользователям прямую маршрутизацию, выполните указанные ниже действия. 

1. Создание пользователя в Office 365 и назначение лицензии на телефонную систему. 
2. Убедитесь в том, что пользователь размещен в Skype для бизнеса Online. 
3. Настройте номер телефона и включите поддержку корпоративной голосовой и голосовой почты. 
4. Назначение пользователю режима "только для Teams".

## <a name="create-a-user-in-office-365-and-assign-the-license"></a>Создание пользователя в Office 365 и назначение лицензии 

Существует два способа создания нового пользователя в Office 365. Тем не менее Корпорация Майкрософт рекомендует выбирать один из вариантов для устранения проблем с маршрутизацией. 

- Создайте пользователя в локальной службе каталогов Active Directory и синхронизируйте пользователя с облаком. Откройте раздел [интеграция локальных каталогов с Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
- Создайте пользователя прямо на портале администратора Office 365. В разделе [Добавление пользователей по отдельности или массово в Office 365 — Справка для администраторов](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Если развертывание Skype для бизнеса Online осуществляется с помощью Skype для бизнеса 2015 или Lync 2010 или 2013 локально, единственным поддерживаемым вариантом будет создание пользователя в локальной службе каталогов Active Directory и синхронизация пользователя с облаком (вариант 1). 

Сведения о требованиях к лицензиям можно найти в разделе [Лицензирование и другие требования](direct-routing-plan.md#licensing-and-other-requirements) в [прямом маршруте планирование](direct-routing-plan.md).

## <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>Убедитесь в том, что пользователь размещен в Skype для бизнеса Online 

Для прямой маршрутизации требуется, чтобы пользователь был подключен в Skype для бизнеса Online. Вы можете проверить, просматривая параметр RegistrarPool, который должен иметь значение в домене infra.lync.com.

1. Подключитесь к удаленной оболочке PowerShell.
2. Выдайте команду: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Настройка номера телефона и включение корпоративной голосовой и голосовой почты 

После создания пользователя и назначения лицензии следует настроить номер телефона пользователя и голосовую почту. 

Чтобы добавить номер телефона и включить голосовую почту, выполните указанные ниже действия.
 
1. Подключитесь к удаленному сеансу PowerShell. 
2. Введите команду: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

    Например, чтобы добавить номер телефона пользователя "Spencer Low", введите следующее: 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    Номер телефона должен быть настроен как полный E. 164 номер телефона с кодом страны. 

      > [!NOTE]
      > Если в качестве номера телефона пользователя используется локальный, используйте локальную среду управления и панель управления Skype для бизнеса, чтобы настроить номер телефона пользователя. 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>Настройка отправки звонков непосредственно в голосовую почту

Прямая маршрутизация позволяет прекратить звонок пользователю и отправить его прямо на голосовую почту пользователя. Если вы хотите отправить звонок прямо на голосовую почту, прикрепите непрозрачный = App: голосовой почте к заголовку URI запроса. Например, "SIP: user@yourdomain. com; непрозрачный = App: голосовой почты". В этом случае пользователь Teams не получит уведомление о звонке, Звонок будет подключен непосредственно к голосовой почте пользователя.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Назначение режима "только для Teams" для пользователей, которые должны обеспечивать звонки в Microsoft Teams

Для прямой маршрутизации необходимо, чтобы пользователи были в режиме "только Teams", чтобы обеспечить поступление входящих звонков в клиенте Teams. Чтобы перевести пользователей в режиме "только Teams", назначьте им экземпляр "UpgradeToTeams" для TeamsUpgradePolicy. Дополнительные сведения можно найти в [статье Руководство по обновлению для ИТ – администраторов](upgrade-to-teams-on-prem-overview.md). Если в вашей организации используется Skype для бизнеса Server или Skype для бизнеса Online, ознакомьтесь со статьей сведения о взаимодействии между Skype и Teams, а также о том, как [Переход и взаимодействие осуществляется в Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md).

## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)

[Настройка прямой маршрутизации](direct-routing-configure.md)
