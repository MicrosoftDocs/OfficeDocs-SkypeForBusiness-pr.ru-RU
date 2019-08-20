---
title: Поддержка использования функций Сефаутил в PowerShell в Skype для бизнеса Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Сводка: сведения о том, как использовать PowerShell для получения функций Сефаутил в Skype для бизнеса Server 2019 после установки накопительного обновления 1.'
ms.openlocfilehash: 6e0f7fc8e4bbb25564faa8107dec81ae3887b360
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464556"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Использование функций Сефаутил через PowerShell в Skype для бизнеса Server 2019

Сефаутил (активация дополнительного расширения) позволяет администраторам и агентам службы поддержки пользователей Skype для бизнеса Server настраивать параметры приема-передачи, переадресации звонков и группового звонка от имени пользователя Skype для бизнеса Server. Оно также позволяет администраторам запрашивать параметры маршрутизации звонков, опубликованные для определенного пользователя. После установки накопительного обновления для Skype для бизнеса Server 2019 за Июль вы можете управлять следующими функциями, которые в настоящее время управляются только через Сефаутил, с помощью PowerShell.

- [Параметры переадресации звонков](#call-forwarding-settings)
- [Параметры делегирования](#delegation-settings)
- [Участники групп и связанные параметры](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Параметры переадресации звонков

Администраторы могут изменить параметры переадресации звонков с помощью следующего командлета в PowerShell:

- `Get-CsUserForwardingSettings -Identity <UserIdParameter>`

Этот командлет возвращает указанные пользователем параметры переадресации звонков в виде объекта и отображает его на экране.

- `Set-CsUserForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Этот командлет изменяет параметры переадресации звонков указанного пользователя. Этот командлет возвращает указанные пользователем параметры переадресации звонков в качестве объекта и отображает его на экране в случае успеха. В случае сбоя будет отображено соответствующее сообщение об ошибке.

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Этот командлет отключает параметры переадресации звонков пользователя (здесь мы рассмотрим два различных примера параметров).

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Этот командлет изменяет параметры переадресации звонков пользователя.

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Этот командлет изменяет параметры Симулринг (опять же, с двумя примерами параметров, один из которых не отвечает на голосовую почту, а второй — неотвеченный другой).

## <a name="delegation-settings"></a>Параметры делегирования

Администраторы могут изменить параметры делегирования с помощью следующего командлета в PowerShell:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Этот командлет возвращает объект списка делегатов и отображает список делегатов указанного пользователя в случае успеха. В случае сбоя будет отображено соответствующее сообщение об ошибке.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Этот командлет изменяет параметры делегирования указанного пользователя, возвращает объект списка делегатов и отображает список делегатов в случае успеха. В случае сбоя будет отображено соответствующее сообщение об ошибке. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Этот командлет добавляет или удаляет делегата.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Этот командлет задает для списка делегатов определенные делегаты.

## <a name="team-members-and-related-settings"></a>Участники групп и связанные параметры

Администраторы могут изменять участников группы и связанные с ними параметры с помощью следующего командлета в PowerShell:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Этот командлет возвращает объект, который содержит список участников группы, и отображает объект на экране в случае успеха. В случае сбоя будет отображено соответствующее сообщение об ошибке.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Этот командлет изменяет список участников группы определенного пользователя, возвращает объект, который содержит список участников группы, и отображает объект на экране в случае успеха. В случае сбоя будет отображено соответствующее сообщение об ошибке.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Этот командлет добавляет или удаляет участников группы.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Этот командлет задает список участников группы для определенного пользователя.

## <a name="more-information"></a>Дополнительные сведения

Для локальных развертываний командлеты, представленные в этой функции, могут быть выполнены только членами следующих групп на уровне доступа, указанным ниже.

- Ксадминистратор — получение и настройка для всех командлетов
- Ксвоицеадминистратор-Get и Set для всех командлетов
- Кшелпдеск-Get для всех командлетов

Дополнительные сведения об этих ролях администратора можно найти в разделе [Создание администраторов панели управления в Skype для бизнеса Server](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). Администратор может получить доступ к этим командлетам, напрямую или удаленно войдя на компьютер сервера.
Для гибридного развертывания администраторы Skype для бизнеса должны вызвать get и Set для всех командлетов. Дополнительные сведения о ролях [администратора Office 365](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles) см.

> [!NOTE]
> Автоматическое обнаружение сервера должно быть включено. Для использования командлетов никакие дополнительные требования к лицензированию не будут добавлены.
