---
title: Блокировка или разблокирование ПИН-кода пользователя в Skype для бизнеса Server
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
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: Сводка. Блокировка или разблокирование ПИН-кода телефонных разговоров пользователя для Skype для бизнес-сервера.
ms.openlocfilehash: 46c46d2bffc8d9c0c8d3456192fb506ce754aecd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119598"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="de410-103">Блокировка или разблокирование ПИН-кода пользователя в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="de410-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="de410-104">**Сводка:** Блокировка или разблокирование ПИН-кода телефонных разговоров пользователя для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="de410-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="de410-105">Пин-код пользователя можно заблокировать или разблокировать в разделе **Пользователи** панели управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="de410-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="de410-106">Блокировка ПИН-кода пользователя в панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="de410-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="de410-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="de410-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="de410-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="de410-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="de410-109">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="de410-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="de410-110">Используйте один из следующих методов для поиска пользователя:</span><span class="sxs-lookup"><span data-stu-id="de410-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="de410-111">В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="de410-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="de410-112">Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="de410-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="de410-113">(Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:</span><span class="sxs-lookup"><span data-stu-id="de410-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="de410-114">а)</span><span class="sxs-lookup"><span data-stu-id="de410-114">a.</span></span> <span data-ttu-id="de410-115">Нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="de410-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="de410-116">б)</span><span class="sxs-lookup"><span data-stu-id="de410-116">b.</span></span> <span data-ttu-id="de410-117">Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="de410-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="de410-118">в.</span><span class="sxs-lookup"><span data-stu-id="de410-118">c.</span></span> <span data-ttu-id="de410-119">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="de410-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="de410-120">г.</span><span class="sxs-lookup"><span data-stu-id="de410-120">d.</span></span> <span data-ttu-id="de410-121">В зависимости от выбранного свойства пользователя введите критерии, которые будут использоваться для фильтрации результатов поиска, набрав его или нажав кнопку стрелки в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="de410-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="de410-122">Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="de410-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="de410-123">д.</span><span class="sxs-lookup"><span data-stu-id="de410-123">e.</span></span> <span data-ttu-id="de410-124">Нажмите кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="de410-124">Click **Find**.</span></span>
    
   <span data-ttu-id="de410-125">е.</span><span class="sxs-lookup"><span data-stu-id="de410-125">f.</span></span> <span data-ttu-id="de410-126">Щелкните пользователя, затем пункт **Действие**, затем **Заблокировать ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="de410-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="de410-127">Разблокировка ПИН-кода пользователя в панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="de410-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="de410-128">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="de410-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="de410-129">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="de410-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="de410-130">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="de410-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="de410-131">Используйте один из следующих методов для поиска пользователя:</span><span class="sxs-lookup"><span data-stu-id="de410-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="de410-132">В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="de410-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="de410-133">Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="de410-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="de410-134">(Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:</span><span class="sxs-lookup"><span data-stu-id="de410-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="de410-135">а)</span><span class="sxs-lookup"><span data-stu-id="de410-135">a.</span></span> <span data-ttu-id="de410-136">Нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="de410-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="de410-137">б)</span><span class="sxs-lookup"><span data-stu-id="de410-137">b.</span></span> <span data-ttu-id="de410-138">Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="de410-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="de410-139">в.</span><span class="sxs-lookup"><span data-stu-id="de410-139">c.</span></span> <span data-ttu-id="de410-140">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="de410-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="de410-141">г.</span><span class="sxs-lookup"><span data-stu-id="de410-141">d.</span></span> <span data-ttu-id="de410-142">В зависимости от выбранного свойства пользователя введите критерии, которые будут использоваться для фильтрации результатов поиска, набрав его или нажав кнопку стрелки в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="de410-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="de410-143">Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="de410-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="de410-144">д.</span><span class="sxs-lookup"><span data-stu-id="de410-144">e.</span></span> <span data-ttu-id="de410-145">Нажмите кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="de410-145">Click **Find**.</span></span>
    
   <span data-ttu-id="de410-146">е.</span><span class="sxs-lookup"><span data-stu-id="de410-146">f.</span></span> <span data-ttu-id="de410-147">Щелкните пользователя, затем пункт **Действие**, затем **Разблокировать ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="de410-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="de410-148">Блокировка и разблокировка пин-кодов пользователей с помощью Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="de410-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="de410-149">Вы можете заблокировать и разблокировать пин-коды пользователей с помощью Windows PowerShell и Lock-CsClientPin и Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="de410-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="de410-150">Эти команды можно запускать либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de410-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="de410-151">Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога ["Быстрый запуск: управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell".</span><span class="sxs-lookup"><span data-stu-id="de410-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="de410-152">В Skype для бизнеса Server этот процесс является одинаковым.</span><span class="sxs-lookup"><span data-stu-id="de410-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="de410-153">Чтобы заблокировать ПИН-код пользователя</span><span class="sxs-lookup"><span data-stu-id="de410-153">To lock a user PIN</span></span>

- <span data-ttu-id="de410-154">Чтобы заблокировать ПИН-код пользователя, используйте Lock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="de410-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="de410-155">Пример:</span><span class="sxs-lookup"><span data-stu-id="de410-155">For example:</span></span>
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="de410-156">Чтобы разблокировать ПИН-код пользователя</span><span class="sxs-lookup"><span data-stu-id="de410-156">To unlock a user PIN</span></span>

- <span data-ttu-id="de410-157">Чтобы разблокировать ПИН-код пользователя, используйте Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="de410-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="de410-158">Например:</span><span class="sxs-lookup"><span data-stu-id="de410-158">For example:</span></span>
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="de410-159">Дополнительные сведения см. в разделе справки для [cmdlets Lock-CsClientPin](/powershell/module/skype/lock-csclientpin?view=skype-ps) и [Unlock-CsClientPin.](/powershell/module/skype/unlock-csclientpin?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="de410-159">For more information, see the help topic for the [Lock-CsClientPin](/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>