---
title: Управление учетной записью пользователя с помощью Соединитела Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Используйте Get-CsOnlineUser в Windows PowerShell, чтобы получить сведения о пользователях Skype для бизнеса Online вашей организации.
ms.openlocfilehash: 370150de08493507d7b401d7907c90f343802d88
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692654"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>Управление учетной записью пользователя с помощью Соединитела Online

## <a name="manage-user-accounts"></a>Управление учетными записями пользователей

В этой статье содержатся следующие разделы.

- [Получение сведений обо всех пользователях Lync Online](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [Возврат сведений о конкретном пользователе в Skype для бизнеса Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [Возврат определенных сведений для определенных пользователей в Skype для бизнеса Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [Возврат отфильтрованного списка пользователей в Skype для бизнеса Online](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> Для администраторов Skype для бизнеса Online также доступен набор **cmdlets Set-CsUser.** Однако **в настоящее время Set-CsUser** нельзя использовать для управления Skype для бизнеса Online, за исключением настройки _параметра AudioVideoDisabled._ Если вы попытались запустить этот cmdlet с любым другим параметром, он не будет сбой с сообщением об ошибке, аналогичным такому: Не удается настроить "SipAddress". Этот параметр ограничен в удаленной клиентской powerShell.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Получение сведений обо всех пользователях Lync Online
<a name="BKAllUsers"> </a>

Чтобы получить сведения обо всех пользователях, у которых есть доступ к Skype для бизнеса Online, вызовите cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) без дополнительных параметров.

```PowerShell
Get-CsOnlineUser
```

Чтобы вернуть сведения для одного случайно выбранного пользователя (например, для использования этой учетной записи в целях тестирования), вызовите cmdlet **Get-CsOnlineUser** и задате для параметра _ResultSize_ 1.

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

В результате **с** его учетом можно получить сведения только для одного пользователя независимо от того, сколько пользователей в вашей организации. Чтобы вернуть сведения для пяти пользователей, установите для параметра _ResultSize_ значение 5.

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Возврат сведений о конкретном пользователе в Skype для бизнеса Online
<a name="BKSpecificUser"> </a>

Существует несколько способов ссылки на конкретную учетную запись пользователя при вызове cmdlet [Get-CsOnlineUser.](https://go.microsoft.com/fwlink/p/?linkid=849603) Вы можете использовать отображаемом имени доменных служб Active Directory (AD DS) пользователя.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

Вы можете использовать SIP-адрес пользователя.

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Вы можете использовать имя директора-пользователя (UPN).

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Возврат определенных сведений для определенных пользователей в Skype для бизнеса Online
<a name="BKSpecificUsers"> </a>

По умолчанию для каждой учетной записи пользователя Skype для бизнеса Online возвращается большой объем информации с помощью cmdlet [Get-CsOnlineUser.](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) Если вам нужно только подмножество этих сведений, перенагружите полученные данные в cmdlet **Select-Object.** Например, эта команда возвращает все данные пользователя "Сергей Мойер", а затем использует командлет **Select-Object,** чтобы ограничить отображаемую на экране информацию отображаемой именем пользователя AD DS и телефонной командой.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

Следующая команда возвращает отображаемую имя и набор для всех пользователей.

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Чтобы найти свойства учетной записи пользователя Skype для бизнеса Online, воспользуйтесь следующей командой:

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Возврат отфильтрованного списка пользователей в Skype для бизнеса Online
<a name="BKListofUsers"> </a>

С помощью параметров [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) и _LdapFilter_ или _Filter_ можно легко возвращать сведения о целевом наборе пользователей. Например, эта команда возвращает всех пользователей, которые работают в финансовом отделе.

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Статьи по теме
[Настройка компьютера для управления skype для бизнеса с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)


