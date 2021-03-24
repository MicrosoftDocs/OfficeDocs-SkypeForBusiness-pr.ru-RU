---
title: Просмотр сведений о ПИН-коде пользователя в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: Сводка. Просмотр сведений о ПИН-коде пользователя в Skype для бизнеса Server.
ms.openlocfilehash: c016e6edf258f63166b930be833542bf9e730f15
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099225"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a><span data-ttu-id="2f1d0-103">Просмотр сведений о ПИН-коде пользователя в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2f1d0-103">View user PIN information in Skype for Business Server</span></span>
 
<span data-ttu-id="2f1d0-104">**Сводка:** Просмотр сведений о ПИН-коде пользователя в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-104">**Summary:** View user PIN information in Skype for Business Server.</span></span>
  
<span data-ttu-id="2f1d0-105">Чтобы присоединиться к телефонной конференции в качестве пользователя с проверкой подлинности, пользователю Skype для бизнеса Server с учетными данными Active Directory Domain Services (AD DS) требуется личный идентификационный номер (PIN).</span><span class="sxs-lookup"><span data-stu-id="2f1d0-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="2f1d0-106">Сведения о ПИН-коде пользователя можно просмотреть на панели управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-106">You can view a user's PIN information from Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2f1d0-107">Можно просмотреть сведения о состоянии ПИН, такие как когда ПИН был определен или когда был в последний раз изменен, однако сведения о состоянии не содержат самого ПИН.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="2f1d0-108">Если пользователь потерял ПИН-код, его можно сбросить, следуя процедурам в Настройка [ПИН-кода](set-a-user-s-dial-in-conferencing-pin.md) телефонных разговоров пользователя в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2f1d0-108">If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span></span>
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="2f1d0-109">Просмотр ПИН-кода пользователя в панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="2f1d0-109">To view a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2f1d0-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2f1d0-111">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="2f1d0-112">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-112">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="2f1d0-113">Используйте один из следующих методов для поиска пользователя:</span><span class="sxs-lookup"><span data-stu-id="2f1d0-113">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="2f1d0-114">В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="2f1d0-115">Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="2f1d0-116">(Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:</span><span class="sxs-lookup"><span data-stu-id="2f1d0-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="2f1d0-117">а)</span><span class="sxs-lookup"><span data-stu-id="2f1d0-117">a.</span></span> <span data-ttu-id="2f1d0-118">Нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-118">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="2f1d0-119">б)</span><span class="sxs-lookup"><span data-stu-id="2f1d0-119">b.</span></span> <span data-ttu-id="2f1d0-120">Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="2f1d0-121">в.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-121">c.</span></span> <span data-ttu-id="2f1d0-122">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="2f1d0-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="2f1d0-123">г.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-123">d.</span></span> <span data-ttu-id="2f1d0-124">В зависимости от выбранного свойства пользователя введите критерии, которые будут использоваться для фильтрации результатов поиска, набрав его или нажав кнопку стрелки в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-124">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="2f1d0-125">Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-125">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="2f1d0-126">д.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-126">e.</span></span> <span data-ttu-id="2f1d0-127">Нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-127">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2f1d0-p108">Если ПИН заблокирован, перед определением необходимо его разблокировать. Чтобы разблокировать ПИН, щелкните **Действие**, затем **Разблокировать ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="2f1d0-130">Щелкните пользователя в результатах поиска, щелкните **Действие**, затем щелкните **Просмотреть состояние ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-130">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2f1d0-131">Просмотр сведений о ПИН-коде пользователя с помощью Windows PowerShell-кодов</span><span class="sxs-lookup"><span data-stu-id="2f1d0-131">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="2f1d0-132">Сведения о ПИН-коде пользователя можно просматривать с помощью Get-CsClientPinInfo.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="2f1d0-133">Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-133">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2f1d0-134">Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога ["Быстрый запуск: управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell".</span><span class="sxs-lookup"><span data-stu-id="2f1d0-134">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="2f1d0-135">В Skype для бизнеса Server этот процесс является одинаковым.</span><span class="sxs-lookup"><span data-stu-id="2f1d0-135">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-user-pin-information"></a><span data-ttu-id="2f1d0-136">Чтобы просмотреть сведения о ПИН пользователя</span><span class="sxs-lookup"><span data-stu-id="2f1d0-136">To view user PIN information</span></span>

<span data-ttu-id="2f1d0-137">Чтобы просмотреть сведения о ПИН-коде для пользователя, введите команду, аналогичную следующей в командной оболочке Skype для бизнес-серверов, а затем нажмите кнопку ENTER:</span><span class="sxs-lookup"><span data-stu-id="2f1d0-137">To view PIN information for a user, type a command similar to the following in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

<span data-ttu-id="2f1d0-138">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="2f1d0-138">That will return information similar to this:</span></span>

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

<span data-ttu-id="2f1d0-139">Дополнительные сведения см. в разделе Справка для [cmdlet Get-CsConferenceDisclaimer.](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2f1d0-139">For more information, see the help topic for the [Get-CsConferenceDisclaimer](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2f1d0-140">См. также</span><span class="sxs-lookup"><span data-stu-id="2f1d0-140">See also</span></span>

[<span data-ttu-id="2f1d0-141">Установите ПИН-код телефонных разговоров пользователя в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2f1d0-141">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>](set-a-user-s-dial-in-conferencing-pin.md)
  
[<span data-ttu-id="2f1d0-142">Блокировка или разблокирование ПИН-кода пользователя в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2f1d0-142">Lock or unlock a user PIN in Skype for Business Server</span></span>](lock-or-unlock-a-user-pin.md)