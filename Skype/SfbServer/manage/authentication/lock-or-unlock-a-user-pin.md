---
title: Блокировка и Разблокировка PIN-кода пользователя в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Сводка: блокирование и разблокирование ПИН-кода конференц-связи с телефонным подключением пользователя для Skype для бизнеса Server.'
ms.openlocfilehash: bbf082fd85780972387cf014573e22996a9edcf0
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992316"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="6489b-103">Блокировка и Разблокировка PIN-кода пользователя в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6489b-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="6489b-104">**Сводка:** Заблокируйте или разблокируйте ПИН-код для конференц-связи с телефонным подключением пользователя для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6489b-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="6489b-105">Вы можете заблокировать или разблокировать ПИН-код пользователя в разделе " **Пользователи** " на панели управления "Skype для бизнеса Server".</span><span class="sxs-lookup"><span data-stu-id="6489b-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="6489b-106">Блокировка PIN-кода пользователя на панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6489b-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6489b-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6489b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6489b-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6489b-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="6489b-109">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="6489b-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="6489b-110">Используйте один из следующих методов для обнаружения пользователя:</span><span class="sxs-lookup"><span data-stu-id="6489b-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="6489b-111">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="6489b-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="6489b-112">Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="6489b-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="6489b-113">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="6489b-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="6489b-114">a)</span><span class="sxs-lookup"><span data-stu-id="6489b-114">a.</span></span> <span data-ttu-id="6489b-115">Щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="6489b-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="6489b-116">б)</span><span class="sxs-lookup"><span data-stu-id="6489b-116">b.</span></span> <span data-ttu-id="6489b-117">Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="6489b-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="6489b-118">в.</span><span class="sxs-lookup"><span data-stu-id="6489b-118">c.</span></span> <span data-ttu-id="6489b-119">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="6489b-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="6489b-120">г.</span><span class="sxs-lookup"><span data-stu-id="6489b-120">d.</span></span> <span data-ttu-id="6489b-121">В зависимости от выбранного свойства пользователя, введите условия, которые хотели бы использовать для фильтрации результатов поиска, введя их с клавиатуры или щелкнув стрелку соответствующего раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="6489b-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="6489b-122">Чтобы добавить в запрос дополнительные условия поиска, щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="6489b-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="6489b-123">учеб.</span><span class="sxs-lookup"><span data-stu-id="6489b-123">e.</span></span> <span data-ttu-id="6489b-124">Щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="6489b-124">Click **Find**.</span></span>
    
   <span data-ttu-id="6489b-125">н.</span><span class="sxs-lookup"><span data-stu-id="6489b-125">f.</span></span> <span data-ttu-id="6489b-126">Щелкните пользователя, затем пункт **Действие**, затем **Заблокировать ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="6489b-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="6489b-127">Разблокирование ПИН-кода пользователя на панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6489b-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6489b-128">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6489b-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6489b-129">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6489b-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="6489b-130">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="6489b-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="6489b-131">Используйте один из следующих методов для обнаружения пользователя:</span><span class="sxs-lookup"><span data-stu-id="6489b-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="6489b-132">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="6489b-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="6489b-133">Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="6489b-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="6489b-134">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="6489b-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="6489b-135">a)</span><span class="sxs-lookup"><span data-stu-id="6489b-135">a.</span></span> <span data-ttu-id="6489b-136">Щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="6489b-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="6489b-137">б)</span><span class="sxs-lookup"><span data-stu-id="6489b-137">b.</span></span> <span data-ttu-id="6489b-138">Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="6489b-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="6489b-139">в.</span><span class="sxs-lookup"><span data-stu-id="6489b-139">c.</span></span> <span data-ttu-id="6489b-140">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="6489b-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="6489b-141">г.</span><span class="sxs-lookup"><span data-stu-id="6489b-141">d.</span></span> <span data-ttu-id="6489b-142">В зависимости от выбранного свойства пользователя, введите условия, которые хотели бы использовать для фильтрации результатов поиска, введя их с клавиатуры или щелкнув стрелку соответствующего раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="6489b-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="6489b-143">Чтобы добавить в запрос дополнительные условия поиска, щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="6489b-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="6489b-144">учеб.</span><span class="sxs-lookup"><span data-stu-id="6489b-144">e.</span></span> <span data-ttu-id="6489b-145">Щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="6489b-145">Click **Find**.</span></span>
    
   <span data-ttu-id="6489b-146">н.</span><span class="sxs-lookup"><span data-stu-id="6489b-146">f.</span></span> <span data-ttu-id="6489b-147">Щелкните пользователя, затем пункт **Действие**, затем **Разблокировать ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="6489b-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6489b-148">Блокировка и разблокировка контактов пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6489b-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6489b-149">Вы можете заблокировать и разблокировать контакты пользователей с помощью Windows PowerShell и командлетов Lock-Ксклиентпин и Unlock-Ксклиентпин.</span><span class="sxs-lookup"><span data-stu-id="6489b-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="6489b-150">Эти командлеты можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6489b-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6489b-151">Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="6489b-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="6489b-152">Этот процесс одинаков в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6489b-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="6489b-153">Чтобы заблокировать ПИН-код пользователя</span><span class="sxs-lookup"><span data-stu-id="6489b-153">To lock a user PIN</span></span>

- <span data-ttu-id="6489b-154">Чтобы заблокировать закрепление пользователя, используйте командлет Lock-Ксклиентпин.</span><span class="sxs-lookup"><span data-stu-id="6489b-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="6489b-155">Пример:</span><span class="sxs-lookup"><span data-stu-id="6489b-155">For example:</span></span>
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="6489b-156">Чтобы разблокировать ПИН-код пользователя</span><span class="sxs-lookup"><span data-stu-id="6489b-156">To unlock a user PIN</span></span>

- <span data-ttu-id="6489b-157">Чтобы разблокировать закрепление пользователя, используйте командлет Unlock-Ксклиентпин.</span><span class="sxs-lookup"><span data-stu-id="6489b-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="6489b-158">Например:</span><span class="sxs-lookup"><span data-stu-id="6489b-158">For example:</span></span>
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="6489b-159">Дополнительные сведения можно найти в разделе справки по командлетам [Lock-ксклиентпин](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) и [Unlock-ксклиентпин](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="6489b-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
