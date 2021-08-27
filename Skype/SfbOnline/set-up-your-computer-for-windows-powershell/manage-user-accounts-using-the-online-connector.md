---
title: Управление учетной записью пользователя с помощью Online Connector
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Используйте Get-CsOnlineUser в Windows PowerShell, чтобы получить сведения о пользователях Skype для бизнеса Online.
ms.openlocfilehash: 6f5caf9df905364c078226501d880db5271db92f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590603"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>Управление учетной записью пользователя с помощью Online Connector

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="manage-user-accounts"></a>Управление учетными записями пользователей

В этой статье содержатся следующие разделы.

- [Получение сведений обо всех пользователях Lync Online](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [Возврат сведений для определенного пользователя в Skype для бизнеса Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [Возврат определенных сведений для определенных пользователей в Skype для бизнеса Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [Возврат отфильтрованного списка пользователей в Skype для бизнеса Online](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> Кроме **того, в** наборе доступных для администраторов Skype для бизнеса Online используется Skype для бизнеса Set-CsUser. Однако **в настоящее время Set-CsUser** нельзя использовать для управления Skype для бизнеса Online, за исключением настройки параметра _AudioVideoDisabled._ Если вы попытались выполнить этот проект с любым другим параметром, при попытке выполнить его сбой с сообщением об ошибке, аналогичным такому: Не удается установить "SipAddress". Этот параметр ограничен в удаленной клиентской powerShell.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Получение сведений обо всех пользователях Lync Online
<a name="BKAllUsers"> </a>

Чтобы получить сведения обо всех пользователях, у которых включена Skype для бизнеса Online, позвоните в [get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) без дополнительных параметров.

```PowerShell
Get-CsOnlineUser
```

Чтобы получить сведения для отдельного пользователя, выбранного случайным образом (например, для использования этой учетной записи в целях тестирования), позвоните в **get-CsOnlineUser** и задате для параметра _ResultSize_ (Размер результатов) 1.

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

**Из-за** этого с его учетной записи будет возвращена информация только для одного пользователя, независимо от того, сколько пользователей в вашей организации. Чтобы получить сведения для пяти пользователей, за установите для _параметра ResultSize_ значение 5.

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Возврат сведений для определенного пользователя в Skype для бизнеса Online
<a name="BKSpecificUser"> </a>

Существует несколько способов ссылки на определенную учетную запись пользователя при вызове [cmdlet Get-CsOnlineUser.](/powershell/module/skype/Get-CsOnlineUser) Вы можете использовать отображаемую имя доменных служб Active Directory (AD DS) пользователя.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

Вы можете использовать SIP-адрес пользователя.

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Вы можете использовать имя имени пользователя-пользователя (UPN).

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Возврат определенных сведений для определенных пользователей в Skype для бизнеса Online
<a name="BKSpecificUsers"> </a>

По умолчанию для [каждой учетной](/powershell/module/skype/Get-CsOnlineUser) записи пользователя Skype для бизнеса Online возвращается большой объем сведений. Если вас интересует только подмножество этих сведений, перенагружите возвращенные данные в проектлет **Select-Object.** Например, эта команда возвращает все данные пользователя Сергея Мойера, а затем использует командлет **Select-Object,** чтобы ограничить отображаемую на экране информацию отображаемой и телефонной планом AD DS Артема.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

Следующая команда возвращает отображаемую и телефонную план для всех пользователей.

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Чтобы найти свойства учетной записи Skype для бизнеса Online, воспользуйтесь следующей командой:

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Возврат отфильтрованного списка пользователей в Skype для бизнеса Online
<a name="BKListofUsers"> </a>

С помощью [параметров Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) и _LdapFilter_ или _Filter_ можно легко возвращать сведения о целевом наборе пользователей. Например, эта команда возвращает всех пользователей, которые работают в финансовом отделе.

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Статьи по теме
[Настройка компьютера для управления Skype для бизнеса в Интернете с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
