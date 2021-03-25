---
title: Управление учетными записями пользователей
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
ms.openlocfilehash: a4675bdb438dd81f9c72aa743134f9a444f0d1f9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113155"
---
# <a name="manage-user-accounts"></a><span data-ttu-id="16018-103">Управление учетными записями пользователей</span><span class="sxs-lookup"><span data-stu-id="16018-103">Manage user accounts</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="16018-104">Управление учетными записями пользователей</span><span class="sxs-lookup"><span data-stu-id="16018-104">Manage user accounts</span></span>

<span data-ttu-id="16018-105">В этой статье содержатся следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="16018-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="16018-106">Получение сведений обо всех пользователях Lync Online</span><span class="sxs-lookup"><span data-stu-id="16018-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [<span data-ttu-id="16018-107">Возврат сведений о конкретном пользователе в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="16018-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [<span data-ttu-id="16018-108">Возврат определенных сведений о конкретных пользователях в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="16018-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [<span data-ttu-id="16018-109">Возврат отфильтрованного списка пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="16018-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> <span data-ttu-id="16018-110">**Cmdlet Set-CsUser** также включается в набор cmdlets, доступный администраторам Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="16018-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="16018-111">Однако **в настоящее время Set-CsUser** нельзя использовать для управления Skype для бизнеса Online, за исключением настройки _параметра AudioVideoDisabled._</span><span class="sxs-lookup"><span data-stu-id="16018-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="16018-112">Если вы попытались запустить этот cmdlet с любым другим параметром, он не будет сбой с сообщением об ошибке примерно так: Не удается установить "SipAddress".</span><span class="sxs-lookup"><span data-stu-id="16018-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="16018-113">Этот параметр ограничен в удаленной клиентской powerShell.</span><span class="sxs-lookup"><span data-stu-id="16018-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="16018-114">Получение сведений обо всех пользователях Lync Online</span><span class="sxs-lookup"><span data-stu-id="16018-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="16018-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="16018-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span></span>

<span data-ttu-id="16018-116">Чтобы получить сведения обо всех пользователях, у которых есть доступ к Skype для бизнеса Online, вызовите cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) без дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="16018-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet without any additional parameters.</span></span>

```PowerShell
Get-CsOnlineUser
```

<span data-ttu-id="16018-117">Чтобы вернуть сведения для одного случайно выбранного пользователя (например, для использования этой учетной записи в целях тестирования), вызовите cmdlet **Get-CsOnlineUser** и задате для параметра _ResultSize_ 1.</span><span class="sxs-lookup"><span data-stu-id="16018-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="16018-118">В результате **с** его учетом можно получить сведения только для одного пользователя независимо от того, сколько пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="16018-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="16018-119">Чтобы вернуть сведения для пяти пользователей, установите для параметра _ResultSize_ значение 5.</span><span class="sxs-lookup"><span data-stu-id="16018-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="16018-120">Возврат сведений о конкретном пользователе в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="16018-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="16018-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="16018-121"><a name="BKMKReturnInfoSpecificUser"> </a></span></span>

<span data-ttu-id="16018-122">Существует несколько способов ссылки на конкретную учетную запись пользователя при вызове cmdlet [Get-CsOnlineUser.](/powershell/module/skype/Get-CsOnlineUser)</span><span class="sxs-lookup"><span data-stu-id="16018-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet.</span></span> <span data-ttu-id="16018-123">Вы можете использовать отображаемом имени доменных служб Active Directory (AD DS) пользователя.</span><span class="sxs-lookup"><span data-stu-id="16018-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="16018-124">Вы можете использовать SIP-адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="16018-124">You can use the user's SIP address.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="16018-125">Вы можете использовать имя директора-пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="16018-125">You can use the user's user principal name (UPN).</span></span>

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="16018-126">Возврат определенных сведений для определенных пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="16018-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="16018-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="16018-127"><a name="BKMKReturninfoSpecificUsers"> </a></span></span>

<span data-ttu-id="16018-128">По умолчанию для каждой учетной записи пользователя Skype для бизнеса Online возвращается большой объем информации с помощью cmdlet [Get-CsOnlineUser.](/powershell/module/skype/Get-CsOnlineUser)</span><span class="sxs-lookup"><span data-stu-id="16018-128">By default, the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="16018-129">Если вам нужно только подмножество этих данных, перенагружите полученные данные в проектлет **Select-Object.**</span><span class="sxs-lookup"><span data-stu-id="16018-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="16018-130">Например, эта команда возвращает все данные пользователя "Сергей Мойер", а затем использует командлет **Select-Object,** чтобы ограничить отображаемую на экране информацию отображаемой именем пользователя AD DS и телефонной командой.</span><span class="sxs-lookup"><span data-stu-id="16018-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="16018-131">Следующая команда возвращает отображаемую и набираемую команду для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="16018-131">The following command returns the display name and dial plan for all your users.</span></span>

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="16018-132">Чтобы найти свойства учетной записи пользователя Skype для бизнеса Online, воспользуйтесь следующей командой:</span><span class="sxs-lookup"><span data-stu-id="16018-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="16018-133">Возврат отфильтрованного списка пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="16018-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="16018-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="16018-134"><a name="BKMKReturnFilteredListofUsers"> </a></span></span>

<span data-ttu-id="16018-135">С помощью параметров [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) и _LdapFilter_ или _Filter_ можно легко возвращать сведения о целевом наборе пользователей.</span><span class="sxs-lookup"><span data-stu-id="16018-135">By using the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="16018-136">Например, эта команда возвращает всех пользователей, которые работают в финансовом отделе.</span><span class="sxs-lookup"><span data-stu-id="16018-136">For example, this command returns all the users who work in the Finance department.</span></span>

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="16018-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="16018-137">Related topics</span></span>
[<span data-ttu-id="16018-138">Настройка компьютера для управления интернет-приложением Skype для бизнеса с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="16018-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)