---
title: "Управление учетными записями пользователей"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
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
description: "Командлет Get-CsOnlineUser в Windows PowerShell для получения сведений о Скайп вашей организации для бизнеса активные пользователи."
ms.openlocfilehash: f51f2c1f723a26bfa3a815bfe7641b68c5d23b26
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
# <a name="manage-user-accounts"></a><span data-ttu-id="52f0a-103">Управление учетными записями пользователей</span><span class="sxs-lookup"><span data-stu-id="52f0a-103">Manage user accounts</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="52f0a-104">Управление учетными записями пользователей</span><span class="sxs-lookup"><span data-stu-id="52f0a-104">Manage user accounts</span></span>

<span data-ttu-id="52f0a-105">В этой статье содержатся следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="52f0a-105">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="52f0a-106">Возвращает сведения о всех Скайп для бизнеса в Интернет пользователей</span><span class="sxs-lookup"><span data-stu-id="52f0a-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)
    
- [<span data-ttu-id="52f0a-107">Получить сведения для определенного пользователя в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="52f0a-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)
    
- [<span data-ttu-id="52f0a-108">Возвращает сведения, относящиеся к определенным пользователям в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="52f0a-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)
    
- [<span data-ttu-id="52f0a-109">Возвращает фильтрованного списка пользователей в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="52f0a-109">Return a filtered list of users in Skype for Business Online </span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)
    
> [!NOTE]
> <span data-ttu-id="52f0a-110">Командлет **Set-CsUser** также входит в набор командлетов, доступных для Скайп для бизнеса в Интернет "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="52f0a-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="52f0a-111">Тем не менее **Set-CsUser** в настоящее время не может использоваться для управления Скайп для бизнеса в Интернет, за исключением параметра _AudioVideoDisabled_ .</span><span class="sxs-lookup"><span data-stu-id="52f0a-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="52f0a-112">Если попытаться запустить командлет с другими параметрами, она завершится с ошибкой с сообщением об ошибке, похожие на следующие: не удается задать «SipAddress».</span><span class="sxs-lookup"><span data-stu-id="52f0a-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="52f0a-113">Этот параметр есть только в пределах удаленного сеанса PowerShell клиента.</span><span class="sxs-lookup"><span data-stu-id="52f0a-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>
  
### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="52f0a-114">Получение сведений обо всех пользователях Lync Online</span><span class="sxs-lookup"><span data-stu-id="52f0a-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="52f0a-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="52f0a-115"></span></span>

<span data-ttu-id="52f0a-116">Для получения информации обо всех пользователей, которым был разрешен доступ к Скайп для бизнеса в Интернет, вызовите командлет [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) без дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="52f0a-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>
  
```
Get-CsOnlineUser
```

<span data-ttu-id="52f0a-117">Чтобы получить сведения для одного, случайно выбранного пользователя (например, чтобы использовать эту учетную запись для тестирования) вызова командлета **Get-CsOnlineUser** и установите параметр _ResultSize_ 1.</span><span class="sxs-lookup"><span data-stu-id="52f0a-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>
  
```
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="52f0a-118">Который вызывает командлет **Get-CsOnlineUser** возвращает сведения для одного пользователя, независимо от того, сколько пользователей в вашей организации есть.</span><span class="sxs-lookup"><span data-stu-id="52f0a-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="52f0a-119">Для возвращения сведений о пяти пользователей, задайте значение параметра _ResultSize_ до 5.</span><span class="sxs-lookup"><span data-stu-id="52f0a-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>
  
```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="52f0a-120">Получить сведения для определенного пользователя в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="52f0a-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="52f0a-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="52f0a-121"></span></span>

<span data-ttu-id="52f0a-122">Существует несколько способов обращения к учетной записи пользователя при вызове командлета [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) .</span><span class="sxs-lookup"><span data-stu-id="52f0a-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="52f0a-123">Можно использовать отображаемое имя пользователя доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="52f0a-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="52f0a-124">Можно использовать адрес SIP пользователя.</span><span class="sxs-lookup"><span data-stu-id="52f0a-124">You can use the user's SIP address.</span></span>
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="52f0a-125">Можно использовать его имя участника-пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="52f0a-125">You can use the user's user principal name (UPN).</span></span>
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="52f0a-126">Возвращает сведения, относящиеся к определенным пользователям в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="52f0a-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="52f0a-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="52f0a-127"></span></span>

<span data-ttu-id="52f0a-128">По умолчанию командлет [Get-CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) возвращает большой объем сведений для каждого Скайп для бизнеса в Интернет учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="52f0a-128">By default, the [Get-CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="52f0a-129">Если вы заинтересованы в подмножество эти сведения, передайте возвращаемые данные в командлет **Select-Object** .</span><span class="sxs-lookup"><span data-stu-id="52f0a-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="52f0a-130">Например эта команда возвращает все данные для пользователя Кен Майер, а затем использует командлет **Select-Object** , чтобы ограничить сведения, отображаемые на экране чтобы Кена Доменные службы Active Directory отображаемое имя и абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="52f0a-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="52f0a-131">Следующие команды Возвращает отображаемое имя и абонентская группа планирования для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="52f0a-131">The following command returns the display name and dial plan for all your users.</span></span>
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="52f0a-132">Чтобы найти свойства Скайп для бизнеса в Интернет учетной записи пользователя, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="52f0a-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>
  
```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="52f0a-133">Возвращает фильтрованного списка пользователей в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="52f0a-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="52f0a-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="52f0a-134"></span></span>

<span data-ttu-id="52f0a-135">С помощью командлета [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) и параметры _LdapFilter_ или _Фильтр_ , можно легко возвращать сведения о целевой группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="52f0a-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="52f0a-136">Например эта команда возвращает все пользователи, работающие в финансовом подразделении.</span><span class="sxs-lookup"><span data-stu-id="52f0a-136">For example, this command returns all the users who work in the Finance department.</span></span>
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="52f0a-137">See also</span><span class="sxs-lookup"><span data-stu-id="52f0a-137">Related topics</span></span>
[<span data-ttu-id="52f0a-138">Настройка компьютера для Скайп online управления бизнес-процессов с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="52f0a-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
