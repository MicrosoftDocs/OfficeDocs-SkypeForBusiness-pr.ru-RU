---
title: Управление учетными записями пользователей
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Командлет Get-CsOnlineUser в Windows PowerShell для получения сведений о Скайп вашей организации для бизнеса активные пользователи.
ms.openlocfilehash: 6c0ea2383e26b7b54eceab3a9adf71477fdc6e9a
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244390"
---
# <a name="manage-user-accounts"></a>Управление учетными записями пользователей

## <a name="manage-user-accounts"></a>Управление учетными записями пользователей

В этой статье содержатся следующие разделы.

- [Получение сведений обо всех пользователях Lync Online](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [Получить сведения для определенного пользователя в Скайп для бизнеса в Интернет](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [Возвращает сведения, относящиеся к определенным пользователям в Скайп для бизнеса в Интернет](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [Возвращает фильтрованного списка пользователей в Скайп для бизнеса в Интернет](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> Командлет **Set-CsUser** также входит в набор командлетов, доступных для Скайп для бизнеса в Интернет "Администраторы". Тем не менее **Set-CsUser** в настоящее время не может использоваться для управления Скайп для бизнеса в Интернет, за исключением параметра _AudioVideoDisabled_ . Если попытаться запустить командлет с другими параметрами, она завершится с ошибкой с сообщением об ошибке, похожие на следующие: не удается задать «SipAddress». Этот параметр есть только в пределах удаленного сеанса PowerShell клиента.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Получение сведений обо всех пользователях Lync Online
<a name="BKMKReturnInfoAboutAllUsers"> </a>

Для получения информации обо всех пользователей, которым был разрешен доступ к Скайп для бизнеса в Интернет, вызовите командлет [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) без дополнительных параметров.

```
Get-CsOnlineUser
```

Чтобы получить сведения для одного, случайно выбранного пользователя (например, чтобы использовать эту учетную запись для тестирования) вызова командлета **Get-CsOnlineUser** и установите параметр _ResultSize_ 1.

```
Get-CsOnlineUser -ResultSize 1
```

Который вызывает командлет **Get-CsOnlineUser** возвращает сведения для одного пользователя, независимо от того, сколько пользователей в вашей организации есть. Для возвращения сведений о пяти пользователей, задайте значение параметра _ResultSize_ до 5.

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Получить сведения для определенного пользователя в Скайп для бизнеса в Интернет
<a name="BKMKReturnInfoSpecificUser"> </a>

Существует несколько способов обращения к учетной записи пользователя при вызове командлета [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) . Можно использовать отображаемое имя пользователя доменных служб Active Directory (AD DS).

```
Get-CsOnlineUser -Identity "Ken Myer"
```

Можно использовать адрес SIP пользователя.

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Можно использовать его имя участника-пользователя (UPN).

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Возвращает сведения, относящиеся к определенным пользователям в Скайп для бизнеса в Интернет
<a name="BKMKReturninfoSpecificUsers"> </a>

По умолчанию командлет [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) возвращает большой объем сведений для каждого Скайп для бизнеса в Интернет учетной записи пользователя. Если вы заинтересованы в подмножество эти сведения, передайте возвращаемые данные в командлет **Select-Object** . Например эта команда возвращает все данные для пользователя Кен Майер, а затем использует командлет **Select-Object** , чтобы ограничить сведения, отображаемые на экране чтобы Кена Доменные службы Active Directory отображаемое имя и абонентской группы.

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

Следующие команды Возвращает отображаемое имя и абонентская группа планирования для всех пользователей.

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Чтобы найти свойства Скайп для бизнеса в Интернет учетной записи пользователя, используйте следующую команду.

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Возвращает фильтрованного списка пользователей в Скайп для бизнеса в Интернет
<a name="BKMKReturnFilteredListofUsers"> </a>

С помощью командлета [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) и параметры _LdapFilter_ или _Фильтр_ , можно легко возвращать сведения о целевой группы пользователей. Например эта команда возвращает все пользователи, работающие в финансовом подразделении.

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Связанные разделы
[Настройка компьютера для Скайп online управления бизнес-процессов с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)


