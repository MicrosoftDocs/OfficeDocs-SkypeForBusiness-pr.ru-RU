---
title: Назначение политики PIN-кода для пользователя в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Сводка: стадия действия (AV) и сертификаты OAuth для сервера Skype для бизнеса Server.'
ms.openlocfilehash: 7591464d55970a9aee4fb1f7ddbb28c2efbac601
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992726"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="c8ca6-103">Назначение политики PIN-кода для пользователя в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c8ca6-103">Assign a per-user PIN policy in Skype for Business Server</span></span>

<span data-ttu-id="c8ca6-104">**Сводка:** Stage (AV) и сертификаты OAuth для сервера Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-104">**Summary:** Stage AV and OAuth certificates for Skype for Business Server.</span></span>
  
<span data-ttu-id="c8ca6-105">Персональный идентификационный номер конференц-связи с телефонным подключением — это один из параметров учетной записи пользователя, которую можно настроить на панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-105">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="c8ca6-p101">Развертывание одной или нескольких политик ПИН-кода на пользователя выполняется по желанию. Также можно развернуть только политику ПИН-кода глобального уровня или уровня сайта. Если выполняется развертывание политик на пользователя, необходимо явно назначить их пользователям, группам или контактным объектам. Значения по умолчанию прав и разрешений пользователей, связанные с использованием ПИН-кодов для конференц-связи с телефонным подключением, задаются автоматически на основе определенных в политике ПИН-кода глобального уровня, если не назначены политики уровня сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-p101">Deploying one or more per-user PIN policies is optional. You can also deploy only a global-level PIN policy or site-level PIN policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>
  
<span data-ttu-id="c8ca6-110">Создав по крайней мере одну политику ПИН-кода на пользователя, используйте процедуры, описанные в этой статье, чтобы назначить политику, указывающую ограничения, которые будут налагаться сервером на ПИН-коды, создаваемые и используемые конкретным пользователем.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-110">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="c8ca6-111">Назначение политики ПИН-кода на пользователя</span><span class="sxs-lookup"><span data-stu-id="c8ca6-111">To assign a per-user PIN policy</span></span>

1. <span data-ttu-id="c8ca6-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c8ca6-113">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-113">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c8ca6-114">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="c8ca6-115">Используйте один из следующих методов для обнаружения пользователя:</span><span class="sxs-lookup"><span data-stu-id="c8ca6-115">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="c8ca6-116">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="c8ca6-117">Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="c8ca6-118">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="c8ca6-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="c8ca6-119">a)</span><span class="sxs-lookup"><span data-stu-id="c8ca6-119">a.</span></span> <span data-ttu-id="c8ca6-120">Щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-120">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="c8ca6-121">б)</span><span class="sxs-lookup"><span data-stu-id="c8ca6-121">b.</span></span> <span data-ttu-id="c8ca6-122">Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="c8ca6-123">в.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-123">c.</span></span> <span data-ttu-id="c8ca6-124">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="c8ca6-124">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="c8ca6-125">г.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-125">d.</span></span> <span data-ttu-id="c8ca6-126">В зависимости от выбранного свойства пользователя введите критерии, которые необходимо использовать для фильтрации результатов поиска; для это введите его или щелкните стрелку в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-126">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c8ca6-127">Чтобы добавить в запрос дополнительные условия поиска, щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-127">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="c8ca6-128">учеб.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-128">e.</span></span> <span data-ttu-id="c8ca6-129">Щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-129">Click **Find**.</span></span>
    
6. <span data-ttu-id="c8ca6-130">Выберите пользователя в списке результатов поиска, щелкните **Действие**, а затем **Назначить политики**.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-130">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c8ca6-131">Чтобы применить одну политику ПИН-кода на пользователя к нескольким пользователям, выберите пользователей в результатах поиска, а затем в меню **Действия** выберите **Назначить политики**.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-131">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click **Actions**, and then click **Assign policies**.</span></span> 
  
7. <span data-ttu-id="c8ca6-132">В окне **Назначение политик** в разделе **Политика ПИН-кода** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-132">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c8ca6-133">Из \*\* \<-\> \*\* за нескольких политик, которые можно настроить с помощью диалогового окна **назначение политик** , по умолчанию для каждой политики в диалоговом окне выбрать пункт Сохранить как.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-133">Because there are multiple policies that you can configure by using the **Assign Policies** dialog box, **\<Keep as is\>** is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="c8ca6-134">Чтобы продолжить использование политики, назначенной пользователю ранее, не вносите никаких изменений в эти настройки.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-134">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>
  
   - <span data-ttu-id="c8ca6-135">Разрешить в Skype для бизнеса Server автоматический выбор политики глобального уровня или, если она определена, в соответствии с политикой уровня сайта.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-135">Allow Skype for Business Server to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
   - <span data-ttu-id="c8ca6-136">Щелкните имя политики ПИН-кода на пользователя, ранее заданную на странице **Политика ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-136">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
    
     > [!TIP]
     > <span data-ttu-id="c8ca6-137">Чтобы с легкостью определить политику, которую необходимо назначить, после выбора названия политики щелкните **Просмотр** для просмотра прав и разрешений пользователя, заданных в политике.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-137">To help you decide the policy you want to assign, after you click a policy name, click **View** to view the user rights and permissions defined in the policy.</span></span>
  
8. <span data-ttu-id="c8ca6-138">По завершении щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-138">When you are finished, click **OK**.</span></span>
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c8ca6-139">Назначение политики PIN-кода для пользователя с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8ca6-139">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c8ca6-140">Вы можете назначать политики ПИН для каждого пользователя с помощью Windows PowerShell и командлета **Grant-кспинполици** .</span><span class="sxs-lookup"><span data-stu-id="c8ca6-140">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="c8ca6-141">Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-141">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c8ca6-142">Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="c8ca6-142">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c8ca6-143">Этот процесс одинаков в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-143">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="c8ca6-144">Назначение индивидуальной политики ПИН-кодов отдельному пользователю</span><span class="sxs-lookup"><span data-stu-id="c8ca6-144">To assign a per-user PIN policy to a single user</span></span>

- <span data-ttu-id="c8ca6-145">Следующая команда позволяет назначить индивидуальную политику ПИН-кодов RedmondPinPolicy пользователю Кену Майеру.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-145">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="c8ca6-146">Назначение индивидуальной политики ПИН-кодов нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="c8ca6-146">To assign a per-user PIN policy to multiple users</span></span>

- <span data-ttu-id="c8ca6-147">Следующая команда назначает политику ПИН для пользователя Редмондусерспинполици всем пользователям, которые работают в городе Redmond.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-147">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="c8ca6-148">Дополнительные сведения о параметре Лдапфилтер, который используется в этой команде, см. в разделе [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c8ca6-148">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="c8ca6-149">Отмена назначения индивидуальной политики ПИН-кодов</span><span class="sxs-lookup"><span data-stu-id="c8ca6-149">To unassign a per-user PIN policy</span></span>

- <span data-ttu-id="c8ca6-p110">Следующая команда отменяет назначение каких-либо индивидуальных политик ПИН-кодов, ранее назначенных Кену Майеру. После отмены назначения для Кена Майера будет автоматически действовать глобальная политика или локальная политика сайта, если такая существует. Политика сайта имеет приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="c8ca6-p110">The following command unassigns any per-user PIN policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

<span data-ttu-id="c8ca6-153">Подробности можно найти в разделе [Grant-кспинполици](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c8ca6-153">For details, see [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c8ca6-154">См. также</span><span class="sxs-lookup"><span data-stu-id="c8ca6-154">See also</span></span>

[<span data-ttu-id="c8ca6-155">Создание новой политики ПИН-кода в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c8ca6-155">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
