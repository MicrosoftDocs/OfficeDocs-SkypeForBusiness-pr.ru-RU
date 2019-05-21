---
title: Управление учетными записями пользователей с помощью онлайнового соединителя
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
f1keywords: None
ms.custom:
- PowerShell
description: С помощью командлета Get-CsOnlineUser в Windows PowerShell можно получить сведения о пользователях Skype для бизнеса Online в вашей организации.
ms.openlocfilehash: 5be51ac39f4a5bd07788a3341114d72a8556cc1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284683"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>Управление учетными записями пользователей с помощью онлайнового соединителя

## <a name="manage-user-accounts"></a>Управление учетными записями пользователей

В этой статье содержатся следующие разделы.

- [Получение сведений обо всех пользователях Lync Online](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [Возврат сведений о конкретном пользователе в Skype для бизнеса Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [Возврат определенных сведений о конкретных пользователях в Skype для бизнеса Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [Возврат отфильтрованного списка пользователей в Skype для бизнеса Online](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> Командлет **Set-CsUser** также включается в набор командлетов, доступных для администраторов Skype для бизнеса Online. Однако **Set-CsUser** в настоящее время не может использоваться для управления Skype для бизнеса Online, за исключением задания параметра _аудиовидеодисаблед_ . При попытке выполнить командлет с другим параметром произойдет сбой с сообщением об ошибке, похожее на следующее: не удается установить значение "Сипаддресс". Этот параметр ограничен в среде удаленного клиента PowerShell.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Получение сведений обо всех пользователях Lync Online
<a name="BKAllUsers"> </a>

Чтобы получить сведения обо всех пользователях, которым разрешено использовать Skype для бизнеса Online, вызовите командлет [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) без дополнительных параметров.

```
Get-CsOnlineUser
```

Чтобы вернуть сведения для одного случайно выбранного пользователя (например, чтобы использовать эту учетную запись для целей тестирования), вызовите командлет **Get-CsOnlineUser** и установите для параметра _ресултсизе_ значение 1.

```
Get-CsOnlineUser -ResultSize 1
```

Это приводит к тому, что командлет **Get-CsOnlineUser** возвращает сведения только для одного пользователя, независимо от количества пользователей в Организации. Чтобы вернуть сведения для пяти пользователей, установите для параметра _ресултсизе_ значение 5.

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Возврат сведений о конкретном пользователе в Skype для бизнеса Online
<a name="BKSpecificUser"> </a>

Существует несколько способов ссылки на определенную учетную запись пользователя при вызове командлета [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) . Вы можете использовать отображаемое имя пользователя доменных служб Active Directory (AD DS).

```
Get-CsOnlineUser -Identity "Ken Myer"
```

Вы можете использовать SIP-адрес пользователя.

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Вы можете использовать имя участника-пользователя (UPN).

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Возврат определенных сведений о конкретных пользователях в Skype для бизнеса Online
<a name="BKSpecificUsers"> </a>

По умолчанию командлет [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) возвращает огромный объем данных для каждой учетной записи пользователя Skype для бизнеса Online. Если вы заинтересованы только в подмножестве этих данных, перебери возвращенные данные в командлет **Select-Object** . Например, эта команда возвращает все данные для пользователя Кен мер, а затем использует командлет **Select-Object** для ограничения отображаемых на экране сведений отображаемым именем и абонентским ИНТЕРФЕЙСОМ AD DS.

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

Следующая команда возвращает отображаемое имя и абонентскую группу для всех пользователей.

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Чтобы найти свойства учетной записи пользователя Skype для бизнеса Online, выполните следующую команду:

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Возврат отфильтрованного списка пользователей в Skype для бизнеса Online
<a name="BKListofUsers"> </a>

С помощью командлета [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) и параметров _лдапфилтер_ или _Filter_ вы можете легко вернуть сведения о целевом наборе пользователей. Например, эта команда возвращает всех пользователей, работающих в финансовом отделе.

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Статьи по теме
[Настройка компьютера для управления Skype для бизнеса Online с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)


