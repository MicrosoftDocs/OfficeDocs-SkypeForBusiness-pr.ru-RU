---
title: Представление пользователя сведения о ПИН-код в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Сводка: Просмотр сведений о пользователе ПИН-код в Скайп для Business Server.'
ms.openlocfilehash: a2e9d7d3e2341590a8eb6a4779bbb1a9c5c26227
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919369"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a><span data-ttu-id="68baa-103">Представление пользователя сведения о ПИН-код в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="68baa-103">View user PIN information in Skype for Business Server</span></span>
 
<span data-ttu-id="68baa-104">**Сводка:** Просмотр пользователя сведения о ПИН-код в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="68baa-104">**Summary:** View user PIN information in Skype for Business Server.</span></span>
  
<span data-ttu-id="68baa-105">Чтобы присоединиться к конференции номера в качестве пользователя с разрешением, Скайп для пользователя Business Server с использованием учетных данных доменных служб Active Directory (AD DS) требуется персонального идентификационного номера (ПИН-кода).</span><span class="sxs-lookup"><span data-stu-id="68baa-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="68baa-106">Можно просмотреть сведения о ПИН пользователя из Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="68baa-106">You can view a user's PIN information from Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="68baa-107">Можно просмотреть сведения о состоянии ПИН, такие как когда ПИН был определен или когда был в последний раз изменен, однако сведения о состоянии не содержат самого ПИН.</span><span class="sxs-lookup"><span data-stu-id="68baa-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="68baa-108">Если пользователь теряет свой ПИН-код, который может сбросить, выполнив процедуры, описанные в [задать пользователя телефонных конференций ПИН-код в Скайп для Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="68baa-108">If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span></span>
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="68baa-109">Чтобы просмотреть ПИН пользователя в Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="68baa-109">To view a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="68baa-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="68baa-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="68baa-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="68baa-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="68baa-112">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="68baa-112">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="68baa-113">Используйте один из следующих методов для обнаружения пользователя:</span><span class="sxs-lookup"><span data-stu-id="68baa-113">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="68baa-114">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="68baa-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="68baa-115">Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="68baa-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="68baa-116">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="68baa-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="68baa-117">a)</span><span class="sxs-lookup"><span data-stu-id="68baa-117">a.</span></span> <span data-ttu-id="68baa-118">Щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="68baa-118">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="68baa-119">б)</span><span class="sxs-lookup"><span data-stu-id="68baa-119">b.</span></span> <span data-ttu-id="68baa-120">Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="68baa-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="68baa-121">в.</span><span class="sxs-lookup"><span data-stu-id="68baa-121">c.</span></span> <span data-ttu-id="68baa-122">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="68baa-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="68baa-123">г.</span><span class="sxs-lookup"><span data-stu-id="68baa-123">d.</span></span> <span data-ttu-id="68baa-124">В зависимости от выбранного свойства пользователя, введите условия, которые хотели бы использовать для фильтрации результатов поиска, введя их с клавиатуры или щелкнув стрелку соответствующего раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="68baa-124">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="68baa-125">Чтобы добавить в запрос дополнительные условия поиска, щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="68baa-125">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="68baa-126">e.</span><span class="sxs-lookup"><span data-stu-id="68baa-126">e.</span></span> <span data-ttu-id="68baa-127">Щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="68baa-127">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="68baa-p108">Если ПИН-код заблокирован, перед определением необходимо его разблокировать. Чтобы разблокировать ПИН-код, щелкните **Действие**, затем **Разблокировать ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="68baa-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="68baa-130">Щелкните пользователя в результатах поиска, щелкните **Действие**, затем щелкните **Просмотреть состояние ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="68baa-130">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="68baa-131">Просмотр сведений о ПИН-код пользователя с помощью Windows PowerShell командлетов</span><span class="sxs-lookup"><span data-stu-id="68baa-131">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="68baa-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="68baa-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="68baa-133">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68baa-133">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="68baa-134">Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="68baa-134">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="68baa-135">Процесс одинаков в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="68baa-135">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-user-pin-information"></a><span data-ttu-id="68baa-136">Порядок просмотра сведений о ПИН-коде пользователя</span><span class="sxs-lookup"><span data-stu-id="68baa-136">To view user PIN information</span></span>

<span data-ttu-id="68baa-137">Чтобы просмотреть сведения о ПИН пользователя, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="68baa-137">To view PIN information for a user, type a command similar to the following in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

<span data-ttu-id="68baa-138">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="68baa-138">That will return information similar to this:</span></span>

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

<span data-ttu-id="68baa-139">Для получения дополнительных сведений см раздел справки для командлета [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="68baa-139">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="68baa-140">См. также</span><span class="sxs-lookup"><span data-stu-id="68baa-140">See also</span></span>

[<span data-ttu-id="68baa-141">Задать пользователя телефонных конференций ПИН-код в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="68baa-141">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>](set-a-user-s-dial-in-conferencing-pin.md)
  
[<span data-ttu-id="68baa-142">Заблокировать или разблокировать ПИН-код, в Скайп пользователя для Business Server</span><span class="sxs-lookup"><span data-stu-id="68baa-142">Lock or unlock a user PIN in Skype for Business Server</span></span>](lock-or-unlock-a-user-pin.md)
