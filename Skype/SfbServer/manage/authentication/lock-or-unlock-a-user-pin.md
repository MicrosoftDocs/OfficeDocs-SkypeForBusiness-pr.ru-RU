---
title: Блокировка и разблокировка ПИН-кода пользователя в Skype для бизнеса Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Сводка: Блокировка и разблокировка пользователя телефонных конференций ПИН-кода для Скайп для Business Server 2015.'
ms.openlocfilehash: 5bd4a334f9c0b543d9b4cade8631f992a920dfb1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server-2015"></a><span data-ttu-id="d322d-103">Блокировка и разблокировка ПИН-кода пользователя в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="d322d-103">Lock or unlock a user PIN in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d322d-104">**Сводка:** Блокировка и разблокировка пользователя телефонных конференций ПИН-кода для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d322d-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d322d-105">Можно заблокировать или разблокировать ПИН-код пользователя в разделе **Пользователи** Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="d322d-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="d322d-106">Чтобы заблокировать ПИН пользователя Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="d322d-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d322d-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d322d-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d322d-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="d322d-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="d322d-109">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="d322d-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="d322d-110">Используйте один из следующих методов для обнаружения пользователя:</span><span class="sxs-lookup"><span data-stu-id="d322d-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="d322d-111">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="d322d-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="d322d-112">Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="d322d-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="d322d-113">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="d322d-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="d322d-114">а.</span><span class="sxs-lookup"><span data-stu-id="d322d-114">a.</span></span> <span data-ttu-id="d322d-115">Щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="d322d-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="d322d-116">б.</span><span class="sxs-lookup"><span data-stu-id="d322d-116">b.</span></span> <span data-ttu-id="d322d-117">Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="d322d-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="d322d-118">в.</span><span class="sxs-lookup"><span data-stu-id="d322d-118">c.</span></span> <span data-ttu-id="d322d-119">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="d322d-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="d322d-120">г.</span><span class="sxs-lookup"><span data-stu-id="d322d-120">d.</span></span> <span data-ttu-id="d322d-121">В зависимости от выбранного свойства пользователя, введите условия, которые хотели бы использовать для фильтрации результатов поиска, введя их с клавиатуры или щелкнув стрелку соответствующего раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="d322d-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="d322d-122">Чтобы добавить в запрос дополнительные условия поиска, щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="d322d-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="d322d-123">e.</span><span class="sxs-lookup"><span data-stu-id="d322d-123">e.</span></span> <span data-ttu-id="d322d-124">Щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="d322d-124">Click **Find**.</span></span>
    
   <span data-ttu-id="d322d-125">f.</span><span class="sxs-lookup"><span data-stu-id="d322d-125">f.</span></span> <span data-ttu-id="d322d-126">Щелкните пользователя, затем пункт **Действие**, затем **Заблокировать ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="d322d-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="d322d-127">Чтобы разблокировать ПИН-код пользователя в Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="d322d-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d322d-128">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d322d-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d322d-129">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="d322d-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="d322d-130">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="d322d-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="d322d-131">Используйте один из следующих методов для обнаружения пользователя:</span><span class="sxs-lookup"><span data-stu-id="d322d-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="d322d-132">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="d322d-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="d322d-133">Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="d322d-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="d322d-134">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="d322d-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="d322d-135">а.</span><span class="sxs-lookup"><span data-stu-id="d322d-135">a.</span></span> <span data-ttu-id="d322d-136">Щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="d322d-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="d322d-137">б.</span><span class="sxs-lookup"><span data-stu-id="d322d-137">b.</span></span> <span data-ttu-id="d322d-138">Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="d322d-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="d322d-139">в.</span><span class="sxs-lookup"><span data-stu-id="d322d-139">c.</span></span> <span data-ttu-id="d322d-140">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="d322d-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="d322d-141">г.</span><span class="sxs-lookup"><span data-stu-id="d322d-141">d.</span></span> <span data-ttu-id="d322d-142">В зависимости от выбранного свойства пользователя, введите условия, которые хотели бы использовать для фильтрации результатов поиска, введя их с клавиатуры или щелкнув стрелку соответствующего раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="d322d-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="d322d-143">Чтобы добавить в запрос дополнительные условия поиска, щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="d322d-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="d322d-144">e.</span><span class="sxs-lookup"><span data-stu-id="d322d-144">e.</span></span> <span data-ttu-id="d322d-145">Щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="d322d-145">Click **Find**.</span></span>
    
   <span data-ttu-id="d322d-146">f.</span><span class="sxs-lookup"><span data-stu-id="d322d-146">f.</span></span> <span data-ttu-id="d322d-147">Щелкните пользователя, затем пункт **Действие**, затем **Разблокировать ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="d322d-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d322d-148">Блокировка и разблокировка PIN-кодами пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d322d-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d322d-149">Блокировать и разблокировать ПИН-коды пользователей с помощью Windows PowerShell и командлетов Lock CsClientPin и Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="d322d-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="d322d-150">Можно выполнить эти командлеты из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d322d-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d322d-151">Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="d322d-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="d322d-152">Процесс одинаков в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="d322d-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="d322d-153">Чтобы заблокировать ПИН-код пользователя</span><span class="sxs-lookup"><span data-stu-id="d322d-153">To lock a user PIN</span></span>

- <span data-ttu-id="d322d-154">Чтобы заблокировать ПИН-код пользователя, используйте командлет Lock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="d322d-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="d322d-155">Пример:</span><span class="sxs-lookup"><span data-stu-id="d322d-155">For example:</span></span>
    
  ```
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="d322d-156">Чтобы разблокировать ПИН-код пользователя</span><span class="sxs-lookup"><span data-stu-id="d322d-156">To unlock a user PIN</span></span>

- <span data-ttu-id="d322d-157">Чтобы разблокировать ПИН-код пользователя, используйте командлет Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="d322d-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="d322d-158">Например:</span><span class="sxs-lookup"><span data-stu-id="d322d-158">For example:</span></span>
    
  ```
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="d322d-159">Для получения дополнительных сведений см раздел справки по командлетам [Lock CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) и [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="d322d-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>