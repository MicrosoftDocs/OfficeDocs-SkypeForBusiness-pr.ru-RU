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
description: 'Сводка: в этой статье рассказывается, как использовать PowerShell для получения функциональных возможностей SEFAUtil в Skype для бизнеса Server 2019 после установки накопительного пакета обновления 1.'
ms.openlocfilehash: 1a18a954e40ba7a0c72e4d87b4b3c943e827f2a1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049141"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Использование функций SEFAUtil с помощью PowerShell в Skype для бизнеса Server 2019

SEFAUtil (дополнительный добавочный номер функции расширения) позволяет администраторам и агентам службы поддержки пользователей Skype для бизнеса Server настраивать параметры ответа на звонки, переадресацию звонка и групповые звонки от имени пользователя Skype для бизнеса Server. Это средство также позволяет администраторам запрашивать параметры маршрутизации вызовов, опубликованные для определенного пользователя. После установки накопительного пакета обновления для Skype для бизнеса Server 2019 Июль в настоящее время можно управлять следующими функциями, которые в настоящее время управляются только с помощью SEFAUtil, с помощью PowerShell:

- [Параметры переадресации звонков](#call-forwarding-settings)
- [Параметры делегирования](#delegation-settings)
- [Участники группы и связанные с ней параметры](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Параметры переадресации звонков

Администраторы могут изменять параметры переадресации звонков с помощью следующего командлета в PowerShell:

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

Этот командлет возвращает параметры переадресации вызовов указанного пользователя в виде объекта и отображает то же самое на экране.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Этот командлет изменяет параметры переадресации звонков указанного пользователя. Этот командлет возвращает параметры переадресации вызовов указанного пользователя в виде объекта и отображается на экране в случае успеха. В случае сбоя отображается соответствующее сообщение об ошибке.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Этот командлет отключает параметры переадресации звонков пользователя (здесь показаны два различных примера параметров).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Этот командлет изменяет параметры переадресации звонков пользователя.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Этот командлет изменяет параметры выполнение (опять с двумя примерами параметров, один из которых не отвечает на голосовую почту, а второй не отвечает другим).

## <a name="delegation-settings"></a>Параметры делегирования

Администраторы могут изменить параметры делегирования с помощью следующего командлета в PowerShell:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Этот командлет возвращает объект List делегата и отображает список делегатов указанного пользователя в случае успеха. В случае сбоя отображается соответствующее сообщение об ошибке.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Этот командлет изменяет параметры делегирования указанного пользователя, возвращает объект List of delegates и отображает список делегатов в случае успеха. В случае сбоя отображается соответствующее сообщение об ошибке. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Этот командлет добавляет или удаляет делегата.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Этот командлет задает список делегатов для определенных делегатов.

## <a name="team-members-and-related-settings"></a>Участники группы и связанные с ней параметры

Администраторы могут изменять участников группы и связанные с ней параметры с помощью следующего командлета в PowerShell:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Этот командлет возвращает объект, содержащий список участников группы, и отображает объект на экране в случае успеха. В случае сбоя отображается соответствующее сообщение об ошибке.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Этот командлет изменяет список участников группы указанного пользователя, возвращает объект, который содержит список участников группы, и отображает объект на экране в случае успеха. В случае сбоя отображается соответствующее сообщение об ошибке.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Этот командлет добавляет или удаляет участников группы.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Этот командлет задает список определенных членов группы.

## <a name="more-information"></a>Дополнительные сведения

Для локальных развертываний командлеты, представленные в этой функции, могут запускаться только членами следующих групп на уровне доступа, указанным ниже:

- CsAdministrator — Get и Set для всех командлетов
- CsVoiceAdministrator — Get и Set для всех командлетов
- CsHelpDesk — Get для всех командлетов

Более подробную информацию об этих ролях администратора можно узнать в статье [Создание администраторов панели управления Skype для бизнеса Server](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). Администратор может получить доступ к этим командлетам непосредственно или с удаленного компьютера для входа на сервер.
Для гибридного развертывания администраторы Skype для бизнеса должны иметь возможность вызывать Get и Set для всех командлетов. Для получения дополнительных сведений о полном списке ролей, ознакомьтесь со статьями [About Office 365 Admin Roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)

> [!NOTE]
> Автоматическое обнаружение сервера должно быть включено. Для использования командлетов не будут использоваться дополнительные требования к лицензированию.
