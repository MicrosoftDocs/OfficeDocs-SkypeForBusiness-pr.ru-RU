---
title: Поддержка использования функций SEFAUtil в Skype PowerShell в Skype для бизнеса Server 2019 г.
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
description: Сводка. Узнайте, как использовать PowerShell для получения функциональных возможностей SEFAUtil в Skype для бизнеса Server 2019 после установки накопительного пакета обновления 1.
ms.openlocfilehash: 07d05ef1687fa9ca14f7e90108ae8b5c0e7e3bb9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676541"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Использование функций SEFAUtil с помощью PowerShell в Skype для бизнеса Server 2019 г.

SEFAUtil (активация дополнительных функций расширения) позволяет администраторам Skype для бизнеса Server и агентам службы технической поддержки настраивать параметры делегирования, переадресации  вызовов и группового вызова от имени Skype для бизнеса Server пользователей. SEFAUtil также позволяет администраторам запрашивать параметры маршрутизации вызовов для определенного пользователя.

После установки накопительного Skype для бизнеса Server за июль 2019 г. следующие функции, доступные только через SEFAUtil, также будут доступны в Skype PowerShell:

- [Параметры переадресации  вызовов](#call-forwarding-settings)
- [Параметры делегирования](#delegation-settings)
- [Участники команды и связанные параметры](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Параметры переадресации  вызовов

Администраторы могут изменить параметры переадресации  вызовов с помощью следующих команд в PowerShell:

```powershell
Get-CsUserCallForwardingSettings -Identity <UserIdParameter>
```

Эта команда возвращает параметры переадресации вызовов указанного пользователя в качестве объекта и отображает то же самое на экране.

```powershell
Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]...
```

Эта команда изменяет параметры переадресации вызовов указанного пользователя. Эта команда возвращает параметры переадресации вызовов указанного пользователя в качестве объекта и отображает то же самое на экране. Если команда не выполнена успешно, отобразится соответствующее сообщение об ошибке.

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

Эта команда отключает параметры переадресации  вызовов пользователя (здесь показаны два разных примера параметров).

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

Эта команда изменяет параметры переадресации  вызовов пользователя.

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]
```

Эта команда изменяет параметры одновременного звонка (опять же, с двумя примерами параметров: один для голосовой почты, а второй — для другого).

## <a name="delegation-settings"></a>Параметры делегирования

Администраторы могут изменять параметры делегирования с помощью следующей команды в PowerShell:

```powershell
Get-CsuserDelegates -Identity <UserIdParameter>
```

Эта команда возвращает объект списка делегатов и отображает список делегатов указанного пользователя. Если команда не выполнена успешно, отобразится соответствующее сообщение об ошибке.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]
```

Эта команда изменяет параметры делегирования указанного пользователя, возвращает объект списка делегатов и отображает список делегатов. Если команда не выполнена успешно, отобразится соответствующее сообщение об ошибке.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]
```

Эта команда добавляет или удаляет делегат.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]
```

Эта команда задает список делегатов для определенных делегатов.

## <a name="team-members-and-related-settings"></a>Участники команды и связанные параметры

Администраторы могут изменять членов команды и связанные параметры с помощью следующей команды в PowerShell:

```powershell
Get-CsUserTeamMembers -Identity <UserIdParameter>
```

Эта команда возвращает объект, содержащий список участников команды, и отображает объект на экране. Если команда не выполнена успешно, отобразится соответствующее сообщение об ошибке.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]
```

Эта команда изменяет список участников команды указанного пользователя, возвращает объект, содержащий список участников группы, и отображает объект на экране. Если команда не выполнена успешно, отобразится соответствующее сообщение об ошибке.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]
```

Эта команда добавляет или удаляет участников команды.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]
```

Эта команда задает список команд для определенных участников.

## <a name="more-information"></a>Дополнительная информация

Для локальных развертываний командлеты, представленные в этой функции, могут выполняться только членами следующих групп в соответствии с уровнем доступа, указанным ниже:

- CsAdministrator — получение и установка для всех командлетов
- CsVoiceAdministrator — получение и установка для всех командлетов
- CsHelpDesk — получение для всех командлетов

Дополнительные сведения об этих ролях администраторов см. в [разделе "Создание Skype для бизнеса Server панель управления администраторов"](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). Администратор может получить доступ к этим командлетам, напрямую или удаленно войдите на серверный компьютер.
Для гибридного развертывания Skype для бизнеса администраторы должны иметь возможность вызывать Get и Set для всех командлетов. Дополнительные сведения о полном списке ролей см. в разделе ["О ролях администратора"](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> Необходимо включить автоматическое обнаружение сервера. Дополнительные требования к лицензированию для использования командлетов не будут применяться.
