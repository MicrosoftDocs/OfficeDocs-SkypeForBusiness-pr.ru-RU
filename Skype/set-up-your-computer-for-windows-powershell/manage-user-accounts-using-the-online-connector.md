---
title: "Управление учетными записями пользователей с помощью Скайп для бизнеса Online соединителя"
ms.author: tonysmit
author: tonysmit
ms.date: 5/23/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
description: "Use the Get-CsOnlineUser cmdlet in Windows PowerShell to get information about your organization's Skype for Business Online users."
---

# Управление учетными записями пользователей с помощью Скайп для бизнеса Online соединителя

> [!IMPORTANT]
> Данная статья переведена с помощью машинного перевода, см. Отказ от ответственности.  
  
## Управление учетными записями пользователей

Эта статья содержит следующие разделы:
  
- [Возврат сведений обо всех пользователях Skype для бизнеса Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnInfoAboutAllUsers)
    
- [Возврат сведений о конкретном пользователе в Skype для бизнеса Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnInfoSpecificUser)
    
- [Возврат определенных сведений о конкретных пользователях в Skype для бизнеса Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturninfoSpecificUsers)
    
- [Возврат отфильтрованного списка пользователей в Skype для бизнеса Online ](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnFilteredListofUsers)
    
> [!NOTE]
> Командлет **Set-CsUser** также включен в набор командлетов, доступных администраторам Skype для бизнеса online. Но **Set-CsUser** сейчас невозможно использовать для управления Skype для бизнеса online, кроме задания параметра _AudioVideoDisabled_. Если вы попытаетесь запустить командлет с любым другим параметром, произойдет сбой с сообщением об ошибке, аналогичным следующему: Не удалось задать "SipAddress". Этот параметр запрещен в удаленной среде PowerShell клиента. 
  
### Возврат сведений обо всех пользователях Skype для бизнеса Online
<a name="BKMK_ReturnInfoAboutAllUsers"> </a>

Чтобы вернуть сведения обо всех пользователях, у которых разрешен Skype для бизнеса online, вызовите командлет [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) без дополнительных параметров.
  
```
Get-CsOnlineUser
```

Чтобы вернуть сведения для одного случайно выбранного пользователя (например, для использования этой учетной записи в целях тестирования), вызовите командлет **Get-CsOnlineUser** и задайте для параметра _ResultSize_ значение 1.
  
```
Get-CsOnlineUser -ResultSize 1
```

Командлет **Get-CsOnlineUser** вернет сведения только для одного пользователя независимо от того, сколько пользователей в организации. Чтобы вернуть сведения для пяти пользователей, задайте для параметра _ResultSize_ значение 5.
  
```
Get-CsOnlineUser -ResultSize 5
```

### Возврат сведений о конкретном пользователе в Skype для бизнеса Online
<a name="BKMK_ReturnInfoSpecificUser"> </a>

Существует несколько способов ссылки на учетную запись конкретного пользователя при вызове командлета [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603). Вы можете использовать отображаемое имя пользователя Доменные службы Active Directory (AD DS).
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

Вы можете использовать SIP-адрес пользователя.
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Вы можете использовать имя участника-пользователя.
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### Возврат определенных сведений о конкретных пользователях в Skype для бизнеса Online
<a name="BKMK_ReturninfoSpecificUsers"> </a>

По умолчанию командлет [Get-CsOnlineUser](https://support.office.com/article/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) возвращает большое количество сведений для каждой учетной записи пользователя Skype для бизнеса online. Если вас интересует только подмножество этих сведений, передайте возвращенные данные в командлет **Select-Object**. Например, эта команда возвращает все данные для пользователя Ken Myer, а затем использует командлет **Select-Object**, чтобы ограничить сведения, показанные на экране, только его отображаемым именем и абонентской группой AD DS.
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

Следующая команда возвращает отображаемое имя и абонентскую группу для всех пользователей.
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Чтобы найти свойства учетной записи пользователя Skype для бизнеса online, используйте следующую команду.
  
```
Get-CsOnlineUser | Get-Member
```

### Возврат отфильтрованного списка пользователей в Skype для бизнеса Online
<a name="BKMK_ReturnFilteredListofUsers"> </a>

Используя командлет [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) и параметры _LdapFilter_ или _Filter_, вы можете легко вернуть сведения о целевом множестве пользователей. Например, эта команда возвращает всех пользователей, которые работают в финансовом отделе.
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Отказ от ответственности относительно машинного перевода**. Данная статья была переведена с помощью компьютерной системы без участия человека. Microsoft предлагает эти машинные переводы, чтобы помочь пользователям, которые не знают английского языка, ознакомиться с материалами о продуктах, услугах и технологиях Microsoft. Поскольку статья была переведена с использованием машинного перевода, она может содержать лексические,синтаксические и грамматические ошибки. 
  

