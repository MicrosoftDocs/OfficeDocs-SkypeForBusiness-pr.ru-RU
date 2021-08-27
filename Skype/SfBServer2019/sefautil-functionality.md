---
title: Поддержка использования функций SEFAUtil в PowerShell в Skype для бизнеса Server 2019 г.
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: Сводка. Узнайте, как использовать PowerShell для получения функций SEFAUtil в Skype для бизнеса Server 2019 г. после установки накопительного обновления 1.
ms.openlocfilehash: 88e62543f41d9a497b9b0ca28c55322fbe5f5be7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578183"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Использование функций SEFAUtil через PowerShell в Skype для бизнеса Server 2019 г.

SEFAUtil (Активация дополнительных функций расширения) позволяет администраторам Skype для бизнеса Server и агентам helpdesk настраивать параметры делегирования, переададации вызовов и группового вызова от имени Skype для бизнеса Server пользователя. Этот инструмент также позволяет администраторам запрашивать параметры маршрутивки вызовов, опубликованные для конкретного пользователя. После установки накопительного обновления Skype для бизнеса Server июля 2019 г. следующие функции, которые в настоящее время можно управлять только с помощью SEFAUtil, также будут управляться с помощью PowerShell:

- [Параметры переададки вызовов](#call-forwarding-settings)
- [Параметры делегирования](#delegation-settings)
- [Члены группы и связанные с ними параметры](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Параметры переададки вызовов

Администраторы могут изменять параметры переадправления вызовов, используя следующий cmdlet в PowerShell:

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

Этот комдлет возвращает указанные параметры переададки вызовов пользователя в качестве объекта и отображает то же самое на экране.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Этот cmdlet изменяет параметры переададции вызовов указанного пользователя. Этот комдлет возвращает указанные параметры переададки зовов пользователя в качестве объекта и отображает то же самое на экране в случае успеха. В случае сбоя будет показано соответствующее сообщение об ошибке.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Этот кодлет отключает параметры переададки вызовов пользователя (здесь мы покажем два разных примера параметров).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Этот кодлет изменяет параметры переададции вызовов пользователя.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Этот cmdlet изменяет параметры одновременных параметров кольца (опять же, с двумя примерами параметров, один для голосовой почты без ответа, а второй без ответа на другие).

## <a name="delegation-settings"></a>Параметры делегирования

Администраторы могут изменять параметры делегирования, используя следующий cmdlet в PowerShell:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Этот комлет возвращает объект списка делегатов и отображает указанный список делегатов пользователя в случае успеха. В случае сбоя будет показано соответствующее сообщение об ошибке.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Этот кодлет изменяет параметры делегирования указанного пользователя, возвращает объект списка делегатов и отображает список делегатов в случае успеха. В случае сбоя будет показано соответствующее сообщение об ошибке. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Этот кодлет добавляет или удаляет делегата.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Этот список задает список делегатов определенным делегатам.

## <a name="team-members-and-related-settings"></a>Члены группы и связанные с ними параметры

Администраторы могут изменять членов группы и связанные с ними параметры, используя следующий командлет в PowerShell:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Этот командлет возвращает объект, содержащий список членов группы, и отображает объект на экране в случае успеха. В случае сбоя будет показано соответствующее сообщение об ошибке.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Этот командлет изменяет список членов команды указанного пользователя, возвращает объект, содержащий список членов группы, и отображает объект на экране в случае успеха. В случае сбоя будет показано соответствующее сообщение об ошибке.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Этот командлет добавляет или удаляет членов группы.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Этот командлет задает список команд определенным участникам.

## <a name="more-information"></a>Дополнительные сведения

Для локального развертывания команды, введенные в эту функцию, могут запускаться только членами следующих групп на уровне доступа, указанном ниже:

- CsAdministrator — get and Set for all cmdlets
- CsVoiceAdministrator — get and Set for all cmdlets
- CsHelpDesk — get for all cmdlets

Дополнительные сведения об этих ролях администратора см. в [Skype для бизнеса Server Администраторы панели управления.](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md) Администратор может получить доступ к этим комлетам, непосредственно или удаленно войдя на серверный компьютер.
Для гибридного развертывания Skype для бизнеса администраторы должны иметь возможность вызывать get and Set для всех cmdlets. Дополнительные сведения о полном списке ролей см. в дополнительных [сведениях о ролях администратора.](/microsoft-365/admin/add-users/about-admin-roles)

> [!NOTE]
> Необходимо включить автоматическое обнаружение сервера. Дополнительные требования к лицензированию для использования этих кодлетов не будут введены.
