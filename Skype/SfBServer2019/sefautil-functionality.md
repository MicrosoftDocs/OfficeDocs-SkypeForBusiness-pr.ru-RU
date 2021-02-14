---
title: Поддержка использования функций SEFAUtil в PowerShell в Skype для бизнеса Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Сводка. Узнайте, как использовать PowerShell для получения функциональных возможностей SEFAUtil в Skype для бизнеса Server 2019 после установки накопительного обновления 1.
ms.openlocfilehash: 19c3ba1124bbc1f32f301096036404f8bd101fe9
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868556"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Использование функций SEFAUtil с помощью PowerShell в Skype для бизнеса Server 2019

SEFAUtil (активация дополнительных функций расширения) позволяет администраторам Skype для бизнеса Server и агентам службы поддержки настраивать параметры делегирования звонков, переададации звонков и группового вызова от имени пользователя Skype для бизнеса Server. Это средство также позволяет администраторам запрашивать параметры маршрутки вызовов, опубликованные для определенного пользователя. После установки накопительного обновления Skype для бизнеса Server 2019 за июль следующие функции, которыми в настоящее время можно управлять только с помощью SEFAUtil, также будут управляться с помощью PowerShell:

- [Параметры переад вызовов](#call-forwarding-settings)
- [Параметры делегирования](#delegation-settings)
- [Участники команды и соответствующие параметры](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Параметры переад вызовов

Администраторы могут изменять параметры переадминизовки параметров с помощью следующего cmdlet в PowerShell:

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

Этот cmdlet возвращает параметры переад вызовов указанного пользователя в качестве объекта и отображает то же самое на экране.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Этот cmdlet изменяет параметры переададции вызовов указанного пользователя. Этот cmdlet возвращает параметры переад вызовов указанного пользователя в качестве объекта и отображает их на экране в случае успеха. В случае сбоя отображается соответствующее сообщение об ошибке.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Этот cmdlet отключает параметры переад вызовов пользователя (здесь мы покажем два разных примера параметров).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Этот cmdlet изменяет параметры переад вызовов пользователя.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Этот cmdlet изменяет параметры SimulRing (опять же, с двумя примерами параметров: один для голосовой почты, а второй — для других).

## <a name="delegation-settings"></a>Параметры делегирования

Администраторы могут изменять параметры делегирования с помощью следующего cmdlet в PowerShell:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Этот cmdlet возвращает объект списка делегатов и отображает список делегатов указанного пользователя в случае успеха. В случае сбоя отображается соответствующее сообщение об ошибке.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Этот cmdlet изменяет параметры делегирования указанного пользователя, возвращает объект списка делегатов и отображает список делегатов в случае успеха. В случае сбоя отображается соответствующее сообщение об ошибке. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Этот cmdlet добавляет или удаляет делегата.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Этот cmdlet задает список делегатов для определенных делегатов.

## <a name="team-members-and-related-settings"></a>Участники команды и соответствующие параметры

Администраторы могут изменять участников команды и связанные с ними параметры с помощью следующего командлета в PowerShell:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Этот командлет возвращает объект, содержащий список участников группы, и отображает его на экране в случае успеха. В случае сбоя отображается соответствующее сообщение об ошибке.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Этот командлет изменяет список участников группы указанного пользователя, возвращает объект, содержащий список участников группы, и отображает его на экране в случае успеха. В случае сбоя отображается соответствующее сообщение об ошибке.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Этот командлет добавляет или удаляет участников команды.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Этот командлет задает список команд для определенных участников.

## <a name="more-information"></a>Дополнительные сведения

Для локального развертывания в соответствии с указанным ниже уровнем доступа запускать в этой функции могут только члены следующих групп:

- CsAdministrator — get and Set for all cmdlets
- CsVoiceAdministrator — get and Set для всех cmdlets
- CsHelpDesk — get для всех cmdlets

Дополнительные сведения об этих ролях администратора см. в записи "Создание администраторов панели управления Skype для бизнеса [Server".](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md) Администратор может получить доступ к этим cmdlets путем прямого или удаленного входа на серверный компьютер.
Для гибридного развертывания администраторы Skype для бизнеса должны иметь возможность вызывать get and Set для всех cmdlets. Дополнительные сведения о полном списке ролей см. в [сведениях о ролях администраторов.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

> [!NOTE]
> Необходимо включить автоматическое обнаружение сервера. Дополнительные требования к лицензированию для использования этих cmdlets не будут применяться.
