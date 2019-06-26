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
f1keywords: None
ms.custom:
- PowerShell
description: С помощью командлета Get-CsOnlineUser в Windows PowerShell можно получить сведения о пользователях Skype для бизнеса Online в вашей организации.
ms.openlocfilehash: 973529682224231e997e3900664fb5163156dfc3
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221766"
---
# <a name="manage-user-accounts"></a><span data-ttu-id="b62e4-103">Управление учетными записями пользователей</span><span class="sxs-lookup"><span data-stu-id="b62e4-103">Manage user accounts</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="b62e4-104">Управление учетными записями пользователей</span><span class="sxs-lookup"><span data-stu-id="b62e4-104">Manage user accounts</span></span>

<span data-ttu-id="b62e4-105">В этой статье содержатся следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="b62e4-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="b62e4-106">Получение сведений обо всех пользователях Lync Online</span><span class="sxs-lookup"><span data-stu-id="b62e4-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [<span data-ttu-id="b62e4-107">Возврат сведений о конкретном пользователе в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b62e4-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [<span data-ttu-id="b62e4-108">Возврат определенных сведений о конкретных пользователях в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b62e4-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [<span data-ttu-id="b62e4-109">Возврат отфильтрованного списка пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b62e4-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> <span data-ttu-id="b62e4-110">Командлет **Set-CsUser** также включается в набор командлетов, доступных для администраторов Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="b62e4-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="b62e4-111">Однако **Set-CsUser** в настоящее время не может использоваться для управления Skype для бизнеса Online, за исключением задания параметра _аудиовидеодисаблед_ .</span><span class="sxs-lookup"><span data-stu-id="b62e4-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="b62e4-112">При попытке выполнить командлет с другим параметром произойдет сбой с сообщением об ошибке, похожее на следующее: не удается установить значение "Сипаддресс".</span><span class="sxs-lookup"><span data-stu-id="b62e4-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="b62e4-113">Этот параметр ограничен в среде удаленного клиента PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b62e4-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="b62e4-114">Получение сведений обо всех пользователях Lync Online</span><span class="sxs-lookup"><span data-stu-id="b62e4-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="b62e4-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="b62e4-115"></span></span>

<span data-ttu-id="b62e4-116">Чтобы получить сведения обо всех пользователях, которым разрешено использовать Skype для бизнеса Online, вызовите командлет [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) без дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="b62e4-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>

```
Get-CsOnlineUser
```

<span data-ttu-id="b62e4-117">Чтобы вернуть сведения для одного случайно выбранного пользователя (например, чтобы использовать эту учетную запись для целей тестирования), вызовите командлет **Get-CsOnlineUser** и установите для параметра _ресултсизе_ значение 1.</span><span class="sxs-lookup"><span data-stu-id="b62e4-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="b62e4-118">Это приводит к тому, что командлет **Get-CsOnlineUser** возвращает сведения только для одного пользователя, независимо от количества пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="b62e4-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="b62e4-119">Чтобы вернуть сведения для пяти пользователей, установите для параметра _ресултсизе_ значение 5.</span><span class="sxs-lookup"><span data-stu-id="b62e4-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="b62e4-120">Возврат сведений о конкретном пользователе в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b62e4-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="b62e4-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="b62e4-121"></span></span>

<span data-ttu-id="b62e4-122">Существует несколько способов ссылки на определенную учетную запись пользователя при вызове командлета [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) .</span><span class="sxs-lookup"><span data-stu-id="b62e4-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="b62e4-123">Вы можете использовать отображаемое имя пользователя доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="b62e4-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="b62e4-124">Вы можете использовать SIP-адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="b62e4-124">You can use the user's SIP address.</span></span>

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="b62e4-125">Вы можете использовать имя участника-пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="b62e4-125">You can use the user's user principal name (UPN).</span></span>

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="b62e4-126">Возврат определенных сведений о конкретных пользователях в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b62e4-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="b62e4-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="b62e4-127"></span></span>

<span data-ttu-id="b62e4-128">По умолчанию командлет [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) возвращает огромный объем данных для каждой учетной записи пользователя Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="b62e4-128">By default, the [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="b62e4-129">Если вы заинтересованы только в подмножестве этих данных, перебери возвращенные данные в командлет **Select-Object** .</span><span class="sxs-lookup"><span data-stu-id="b62e4-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="b62e4-130">Например, эта команда возвращает все данные для пользователя Кен мер, а затем использует командлет **Select-Object** для ограничения отображаемых на экране сведений отображаемым именем и абонентским ИНТЕРФЕЙСОМ AD DS.</span><span class="sxs-lookup"><span data-stu-id="b62e4-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="b62e4-131">Следующая команда возвращает отображаемое имя и абонентскую группу для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="b62e4-131">The following command returns the display name and dial plan for all your users.</span></span>

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="b62e4-132">Чтобы найти свойства учетной записи пользователя Skype для бизнеса Online, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b62e4-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="b62e4-133">Возврат отфильтрованного списка пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b62e4-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="b62e4-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="b62e4-134"></span></span>

<span data-ttu-id="b62e4-135">С помощью командлета [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) и параметров _лдапфилтер_ или _Filter_ вы можете легко вернуть сведения о целевом наборе пользователей.</span><span class="sxs-lookup"><span data-stu-id="b62e4-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="b62e4-136">Например, эта команда возвращает всех пользователей, работающих в финансовом отделе.</span><span class="sxs-lookup"><span data-stu-id="b62e4-136">For example, this command returns all the users who work in the Finance department.</span></span>

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="b62e4-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b62e4-137">Related topics</span></span>
[<span data-ttu-id="b62e4-138">Настройка компьютера для управления Skype для бизнеса Online с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b62e4-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)


