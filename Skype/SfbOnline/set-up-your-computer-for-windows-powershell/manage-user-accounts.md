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
description: Используйте Get-CsOnlineUser в Windows PowerShell, чтобы получить сведения о пользователях Skype для бизнеса Online.
ms.openlocfilehash: aec79f589f6b1fb0c9d38fd4bc70421b30f66a56
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238725"
---
# <a name="manage-user-accounts"></a><span data-ttu-id="5c39d-103">Управление учетными записями пользователей</span><span class="sxs-lookup"><span data-stu-id="5c39d-103">Manage user accounts</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="manage-user-accounts"></a><span data-ttu-id="5c39d-104">Управление учетными записями пользователей</span><span class="sxs-lookup"><span data-stu-id="5c39d-104">Manage user accounts</span></span>

<span data-ttu-id="5c39d-105">В этой статье содержатся следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="5c39d-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="5c39d-106">Получение сведений обо всех пользователях Lync Online</span><span class="sxs-lookup"><span data-stu-id="5c39d-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [<span data-ttu-id="5c39d-107">Возврат сведений для определенного пользователя в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5c39d-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [<span data-ttu-id="5c39d-108">Возврат определенных сведений для определенных пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5c39d-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [<span data-ttu-id="5c39d-109">Возврат отфильтрованного списка пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5c39d-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> <span data-ttu-id="5c39d-110">Кроме **того, в** наборе доступных для администраторов Skype для бизнеса Online используется Skype для бизнеса-CsUser.</span><span class="sxs-lookup"><span data-stu-id="5c39d-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="5c39d-111">Однако **в настоящее время Set-CsUser** нельзя использовать для управления Skype для бизнеса Online, за исключением настройки параметра _AudioVideoDisabled._</span><span class="sxs-lookup"><span data-stu-id="5c39d-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="5c39d-112">Если вы попытались выполнить этот проект с любым другим параметром, при попытке выполнить его сбой с сообщением об ошибке, аналогичным такому: Не удается установить "SipAddress".</span><span class="sxs-lookup"><span data-stu-id="5c39d-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="5c39d-113">Этот параметр ограничен в удаленной клиентской powerShell.</span><span class="sxs-lookup"><span data-stu-id="5c39d-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="5c39d-114">Получение сведений обо всех пользователях Lync Online</span><span class="sxs-lookup"><span data-stu-id="5c39d-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="5c39d-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="5c39d-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span></span>

<span data-ttu-id="5c39d-116">Чтобы получить сведения обо всех пользователях, у которых включена Skype для бизнеса Online, позвоните в [get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) без дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="5c39d-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet without any additional parameters.</span></span>

```PowerShell
Get-CsOnlineUser
```

<span data-ttu-id="5c39d-117">Чтобы получить сведения об одном пользователе, выбранном случайным образом (например, для использования этой учетной записи в целях тестирования), позвоните в **cmdlet Get-CsOnlineUser** и задате для параметра _ResultSize_ (Размер результатов) 1.</span><span class="sxs-lookup"><span data-stu-id="5c39d-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="5c39d-118">Это приводит **к** возврату сведений только для одного пользователя с учетом того, сколько пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5c39d-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="5c39d-119">Чтобы получить сведения для пяти пользователей, за установите для _параметра ResultSize_ значение 5.</span><span class="sxs-lookup"><span data-stu-id="5c39d-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="5c39d-120">Возврат сведений для определенного пользователя в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5c39d-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="5c39d-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="5c39d-121"><a name="BKMKReturnInfoSpecificUser"> </a></span></span>

<span data-ttu-id="5c39d-122">Существует несколько способов ссылки на определенную учетную запись пользователя при вызове [cmdlet Get-CsOnlineUser.](/powershell/module/skype/Get-CsOnlineUser)</span><span class="sxs-lookup"><span data-stu-id="5c39d-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet.</span></span> <span data-ttu-id="5c39d-123">Вы можете использовать отображаемую имя доменных служб Active Directory (AD DS) пользователя.</span><span class="sxs-lookup"><span data-stu-id="5c39d-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="5c39d-124">Вы можете использовать SIP-адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="5c39d-124">You can use the user's SIP address.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="5c39d-125">Вы можете использовать имя имени пользователя-пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="5c39d-125">You can use the user's user principal name (UPN).</span></span>

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="5c39d-126">Возврат определенных сведений для определенных пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5c39d-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="5c39d-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="5c39d-127"><a name="BKMKReturninfoSpecificUsers"> </a></span></span>

<span data-ttu-id="5c39d-128">По умолчанию для [каждой учетной](/powershell/module/skype/Get-CsOnlineUser) записи пользователя Skype для бизнеса Online возвращается большой объем сведений.</span><span class="sxs-lookup"><span data-stu-id="5c39d-128">By default, the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="5c39d-129">Если вас интересует только подмножество этих сведений, перенагружите возвращенные данные в проектлет **Select-Object.**</span><span class="sxs-lookup"><span data-stu-id="5c39d-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="5c39d-130">Например, эта команда возвращает все данные пользователя Сергея Мойера, а затем использует командлет **Select-Object,** чтобы ограничить отображаемую на экране информацию отображаемой и телефонной планом AD DS Артема.</span><span class="sxs-lookup"><span data-stu-id="5c39d-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="5c39d-131">Следующая команда возвращает отображаемую и телефонную план для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="5c39d-131">The following command returns the display name and dial plan for all your users.</span></span>

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="5c39d-132">Чтобы найти свойства учетной записи Skype для бизнеса Online, воспользуйтесь следующей командой:</span><span class="sxs-lookup"><span data-stu-id="5c39d-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="5c39d-133">Возврат отфильтрованного списка пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5c39d-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="5c39d-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="5c39d-134"><a name="BKMKReturnFilteredListofUsers"> </a></span></span>

<span data-ttu-id="5c39d-135">С помощью [параметров Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) и _LdapFilter_ или _Filter_ можно легко возвращать сведения о целевом наборе пользователей.</span><span class="sxs-lookup"><span data-stu-id="5c39d-135">By using the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="5c39d-136">Например, эта команда возвращает всех пользователей, которые работают в финансовом отделе.</span><span class="sxs-lookup"><span data-stu-id="5c39d-136">For example, this command returns all the users who work in the Finance department.</span></span>

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="5c39d-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5c39d-137">Related topics</span></span>
[<span data-ttu-id="5c39d-138">Настройка компьютера для управления Skype для бизнеса online с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c39d-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
