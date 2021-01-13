---
title: Назначение политики ПИН-кодов на пользователя в Skype для бизнеса Server
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
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: Сводка. Этапы сертификатов AV и OAuth для Skype для бизнеса Server.
ms.openlocfilehash: 6a0d0a1824e809a70dfee419fb5da1f663d8d779
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828529"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="6fae7-103">Назначение политики ПИН-кодов на пользователя в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6fae7-103">Assign a per-user PIN policy in Skype for Business Server</span></span>

<span data-ttu-id="6fae7-104">**Сводка:** Stage AV and OAuth certificates for Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6fae7-104">**Summary:** Stage AV and OAuth certificates for Skype for Business Server.</span></span>
  
<span data-ttu-id="6fae7-105">Политика персонального идентификационного номера (ПИН-кода) для телефонной сети — это один из индивидуальных параметров учетной записи пользователя, которую можно настроить на панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6fae7-105">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="6fae7-106">Развертывание одной или более политик ПИН-кодов на пользователя является необязательным.</span><span class="sxs-lookup"><span data-stu-id="6fae7-106">Deploying one or more per-user PIN policies is optional.</span></span> <span data-ttu-id="6fae7-107">Вы также можете развернуть только политику ПИН-кодов глобального уровня или политику ПИН-кодов на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="6fae7-107">You can also deploy only a global-level PIN policy or site-level PIN policy.</span></span> <span data-ttu-id="6fae7-108">При развертывании политик для отдельных пользователей необходимо явным образом назначить их пользователям, группам или контактному объекту.</span><span class="sxs-lookup"><span data-stu-id="6fae7-108">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="6fae7-109">Права и разрешения пользователей, касающиеся использования ПИН-кодов для телефонной связи, автоматически по умолчанию имеют значения, определенные в политике ПИН-кодов глобального уровня, если не назначена определенная политика уровня сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="6fae7-109">User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>
  
<span data-ttu-id="6fae7-110">После создания по крайней мере одной политики ПИН-кодов для отдельных пользователей используйте процедуры, указанные в этом разделе, чтобы назначить политику, которая определяет ограничения, которые сервер должен налагать на ПИН-коды, созданные и используемые определенным пользователем.</span><span class="sxs-lookup"><span data-stu-id="6fae7-110">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="6fae7-111">Назначение политики ПИН-кодов на пользователя</span><span class="sxs-lookup"><span data-stu-id="6fae7-111">To assign a per-user PIN policy</span></span>

1. <span data-ttu-id="6fae7-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6fae7-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6fae7-113">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6fae7-113">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="6fae7-114">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="6fae7-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="6fae7-115">Используйте один из следующих методов для поиска пользователя:</span><span class="sxs-lookup"><span data-stu-id="6fae7-115">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="6fae7-116">В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="6fae7-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="6fae7-117">Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="6fae7-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="6fae7-118">(Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:</span><span class="sxs-lookup"><span data-stu-id="6fae7-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="6fae7-119">а.</span><span class="sxs-lookup"><span data-stu-id="6fae7-119">a.</span></span> <span data-ttu-id="6fae7-120">Нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="6fae7-120">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="6fae7-121">б.</span><span class="sxs-lookup"><span data-stu-id="6fae7-121">b.</span></span> <span data-ttu-id="6fae7-122">Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="6fae7-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="6fae7-123">c.</span><span class="sxs-lookup"><span data-stu-id="6fae7-123">c.</span></span> <span data-ttu-id="6fae7-124">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="6fae7-124">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="6fae7-125">г.</span><span class="sxs-lookup"><span data-stu-id="6fae7-125">d.</span></span> <span data-ttu-id="6fae7-126">В зависимости от выбранного свойства пользователя введите критерии, которые необходимо использовать для фильтрации результатов поиска; для это введите его или щелкните стрелку в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="6fae7-126">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="6fae7-127">Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="6fae7-127">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="6fae7-128">д.</span><span class="sxs-lookup"><span data-stu-id="6fae7-128">e.</span></span> <span data-ttu-id="6fae7-129">Нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="6fae7-129">Click **Find**.</span></span>
    
6. <span data-ttu-id="6fae7-130">Выберите пользователя в списке результатов поиска, щелкните **Действие**, а затем щелкните **Назначить политики**.</span><span class="sxs-lookup"><span data-stu-id="6fae7-130">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="6fae7-131">Если вы хотите, чтобы к нескольким пользователям применялись одинаковые политики ПИН-кодов на уровне пользователей, выберите несколько пользователей в результатах поиска, затем щелкните "Действия" и выберите "Назначить **политики".** </span><span class="sxs-lookup"><span data-stu-id="6fae7-131">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click **Actions**, and then click **Assign policies**.</span></span> 
  
7. <span data-ttu-id="6fae7-132">В **области "Назначить политики"** в **политике ПИН-кодов** сделайте одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="6fae7-132">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6fae7-133">Поскольку существует несколько политик, которые можно настроить  с помощью диалоговых окна "Назначение политик", по умолчанию выбраны для каждой политики в диалоговом **\<Keep as is\>** окне.</span><span class="sxs-lookup"><span data-stu-id="6fae7-133">Because there are multiple policies that you can configure by using the **Assign Policies** dialog box, **\<Keep as is\>** is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="6fae7-134">Чтобы продолжить использование политики, назначенной пользователю ранее, не вносите никаких изменений в эти настройки.</span><span class="sxs-lookup"><span data-stu-id="6fae7-134">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>
  
   - <span data-ttu-id="6fae7-135">Разрешить Skype для бизнеса Server автоматически выбирать политику глобального уровня или, если она определена, политику уровня сайта.</span><span class="sxs-lookup"><span data-stu-id="6fae7-135">Allow Skype for Business Server to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
   - <span data-ttu-id="6fae7-136">Щелкните имя политики ПИН-кодов на пользователя, ранее определенной на странице **"Политика ПИН-кодов".**</span><span class="sxs-lookup"><span data-stu-id="6fae7-136">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
    
     > [!TIP]
     > <span data-ttu-id="6fae7-137">Чтобы с легкостью определить политику, которую необходимо назначить, после выбора названия политики щелкните **Просмотр** для просмотра прав и разрешений пользователя, заданных в политике.</span><span class="sxs-lookup"><span data-stu-id="6fae7-137">To help you decide the policy you want to assign, after you click a policy name, click **View** to view the user rights and permissions defined in the policy.</span></span>
  
8. <span data-ttu-id="6fae7-138">По завершении нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6fae7-138">When you are finished, click **OK**.</span></span>
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6fae7-139">Назначение политики ПИН-Per-User с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6fae7-139">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6fae7-140">Политики ПИН-кодов для каждого пользователя можно назначить с Windows PowerShell и с помощью Windows PowerShell **Grant-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="6fae7-140">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="6fae7-141">Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fae7-141">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6fae7-142">Подробные сведения об использовании удаленного Windows PowerShell для подключения к Skype для бизнеса Server см. в статье [блога "Краткое руководство. Управление Microsoft Lync Server 2010 с помощью удаленной службы PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="6fae7-142">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="6fae7-143">В Skype для бизнеса Server этот процесс тот же.</span><span class="sxs-lookup"><span data-stu-id="6fae7-143">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="6fae7-144">Назначение политики ПИН-кодов на пользователя одному пользователю</span><span class="sxs-lookup"><span data-stu-id="6fae7-144">To assign a per-user PIN policy to a single user</span></span>

- <span data-ttu-id="6fae7-145">Следующая команда назначает политику ПИН-кодов на пользователя RedmondPinPolicy пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="6fae7-145">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="6fae7-146">Назначение политики ПИН-кодов на пользователя нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="6fae7-146">To assign a per-user PIN policy to multiple users</span></span>

- <span data-ttu-id="6fae7-147">Следующая команда назначает политику ПИН-кодов на пользователя RedmondUsersPinPolicy всем пользователям, которые работают в городе Редмонд.</span><span class="sxs-lookup"><span data-stu-id="6fae7-147">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="6fae7-148">Подробные сведения о параметре LdapFilter, используемом в этой команде, см. в командной [команде Get-CsUser.](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="6fae7-148">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="6fae7-149">Чтобы отоименовать политику ПИН-кодов на пользователя</span><span class="sxs-lookup"><span data-stu-id="6fae7-149">To unassign a per-user PIN policy</span></span>

- <span data-ttu-id="6fae7-150">Следующая команда открепит любую политику ПИН-кодов на пользователя, ранее назначенную пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="6fae7-150">The following command unassigns any per-user PIN policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="6fae7-151">После отмены назначения политики пользователь Ken Myer будет автоматически управляться глобальной политикой или, если такая существует, локальной политикой сайта.</span><span class="sxs-lookup"><span data-stu-id="6fae7-151">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="6fae7-152">Политика сайта имеет более высокий приоритет, чем глобальная политика.</span><span class="sxs-lookup"><span data-stu-id="6fae7-152">A site policy takes precedence over the global policy.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

<span data-ttu-id="6fae7-153">Подробные сведения [см. в поле Grant-CsPinPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="6fae7-153">For details, see [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6fae7-154">См. также</span><span class="sxs-lookup"><span data-stu-id="6fae7-154">See also</span></span>

[<span data-ttu-id="6fae7-155">Создание новой политики ПИН-кодов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6fae7-155">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
