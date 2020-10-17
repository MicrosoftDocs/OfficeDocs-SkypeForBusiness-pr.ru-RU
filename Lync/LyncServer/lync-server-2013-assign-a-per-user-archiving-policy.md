---
title: 'Lync Server 2013: назначение политики архивации на уровне пользователя'
description: 'Lync Server 2013: назначение политики архивации на уровне пользователя.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c81d7e426f16c298196aba733d720a92d0854bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559995"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="56ba4-103">Назначение политики архивации на уровне пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56ba4-103">Assign a per-user archiving policy in Lync Server 2013</span></span>

 


<span data-ttu-id="56ba4-104">Политика архивации это один из индивидуальных параметров учетной записи пользователя, которую можно настроить в панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="56ba4-104">The archiving policy is one of the individual settings of a user account that you can configure in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="56ba4-p101">Развертывание политик архивации на уровне пользователя является необязательным. Вы можете развернуть политику архивации только на глобальном уровне или на уровне сайта. При развертывании политик на уровне пользователей вам потребуется явно назначить их пользователям, группам или объектам контакта. Если политика архивации на уровне сайта или пользователя не задана, то по умолчанию будут использоваться параметры архивации, заданные в политике конференц-связи глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="56ba4-p101">Deploying one or more per-user archiving policies is optional. You can also deploy only a global-level archiving policy or site-level archiving policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. Archiving requirements automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="56ba4-109">После создания политики архивации на уровне пользователя назначьте политику, которая задает параметры архивации внутренних коммуникаций пользователя, внешних коммуникаций пользователя или коммуникаций обоих типов, с помощью процедур, описанных в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="56ba4-109">After creating at least one per-user archiving policy, use the procedures in this topic to assign the policy that appropriately specifies whether a particular user’s internal communications, external communications, or both, will be archived by the server.</span></span>

<span data-ttu-id="56ba4-110">Дополнительные сведения о создании политик архивации на уровне пользователя приведены [в статье Создание политики архивации в Lync Server 2013 для включения или отключения архивации внутренних или внешних коммуникаций для определенных сайтов или пользователей](lync-server-2013-create-archiving-policy-sites-users.md).</span><span class="sxs-lookup"><span data-stu-id="56ba4-110">For details about creating per-user archiving policies, see [Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users](lync-server-2013-create-archiving-policy-sites-users.md).</span></span>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="56ba4-111">Назначение политики архивации на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="56ba4-111">To assign a per-user archiving policy</span></span>

1.  <span data-ttu-id="56ba4-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="56ba4-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="56ba4-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56ba4-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="56ba4-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="56ba4-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="56ba4-115">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="56ba4-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="56ba4-116">Используйте один из следующих методов для поиска пользователя:</span><span class="sxs-lookup"><span data-stu-id="56ba4-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="56ba4-117">В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="56ba4-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="56ba4-118">Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="56ba4-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="56ba4-119">(Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:</span><span class="sxs-lookup"><span data-stu-id="56ba4-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="56ba4-120">Нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="56ba4-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="56ba4-121">Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="56ba4-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="56ba4-122">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="56ba4-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="56ba4-123">В зависимости от выбранного свойства пользователя введите критерии, которые необходимо использовать для фильтрации результатов поиска; для это введите его или щелкните стрелку в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="56ba4-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="56ba4-124">Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="56ba4-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="56ba4-125">Нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="56ba4-125">Click **Find**.</span></span>

6.  <span data-ttu-id="56ba4-126">Выберите пользователя в результатах поиска, щелкните **Действие** и затем щелкните **Назначить политики**.</span><span class="sxs-lookup"><span data-stu-id="56ba4-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="56ba4-127">Если требуется применить одну политику архивации к нескольким пользователям, выберите нескольких пользователей в результатах поиска, щелкните <STRONG>Действия</STRONG> и затем щелкните <STRONG>Назначить политики</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="56ba4-127">If you want the same per-user archiving policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="56ba4-128">В разделе **Политика архивации** диалогового окна **Назначение политик** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="56ba4-128">In **Assign Policies**, under **Archiving policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="56ba4-129">Так как существует несколько политик, которые можно настроить с помощью диалогового окна <STRONG>Assign Policies (назначить политики</STRONG> ), по умолчанию для каждой политики в диалоговом окне флажок <STRONG> &lt; &gt; Сохранить как</STRONG> установлен.</span><span class="sxs-lookup"><span data-stu-id="56ba4-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="56ba4-130">Чтобы продолжить использование политики, назначенной пользователю ранее, не вносите никаких изменений в эти настройки.</span><span class="sxs-lookup"><span data-stu-id="56ba4-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="56ba4-131">Разрешить Lync Server 2013 автоматически выбирать политику глобального уровня или, если определено, политику на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="56ba4-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="56ba4-132">Щелкните имя политики архивации на уровне пользователя, которую вы задали ранее на странице **Политика архивации**.</span><span class="sxs-lookup"><span data-stu-id="56ba4-132">Click the name of a per-user archiving policy you previously defined on the **Archiving Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="56ba4-133">Чтобы упростить выбор назначаемой политики, выделите имя политики и затем щелкните <STRONG>Просмотр</STRONG> для получения сведений о правах и разрешениях, определенных в политике.</span><span class="sxs-lookup"><span data-stu-id="56ba4-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="56ba4-134">Закончив, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="56ba4-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="56ba4-135">Назначение политики архивации Per-User с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="56ba4-135">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="56ba4-136">Политики архивации для отдельных пользователей можно назначить с помощью Windows PowerShell и командлета **Grant – CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="56ba4-136">You can assign per-user archiving policies by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="56ba4-137">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56ba4-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="56ba4-138">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="56ba4-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="56ba4-139">Назначение политики архивации на уровне пользователя одному пользователю</span><span class="sxs-lookup"><span data-stu-id="56ba4-139">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="56ba4-140">Следующей командой пользователю Ken Myer назначается политика архивации RedmondArchivingPolicy на уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="56ba4-140">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="56ba4-141">Назначение политики архивации на уровне пользователей нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="56ba4-141">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="56ba4-142">Этот командлет назначает индивидуальную политику архивации RedmondArchivingPolicy всем пользователям, имеющим учетные записи, размещенные в пуле регистратора (Registrar) atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="56ba4-142">This command assigns the per-user archiving policy RedmondArchivingPolicy to all the users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="56ba4-143">Для получения дополнительных сведений о параметре Filter, используемом в этой команде, обратитесь к документации по командлету [Get – CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="56ba4-143">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a><span data-ttu-id="56ba4-144">Отмена назначения политики архивации на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="56ba4-144">To unassign a per-user archiving policy</span></span>

  - <span data-ttu-id="56ba4-p106">Следующей командой отменяется любая политика архивации на уровне пользователей, ранее назначенная пользователю Ken Myer. После того как политика на уровне пользователей отменена, Ken Myer будет автоматически управляться с помощью глобальной политики или политики его локального сайта, если такая существует. Политика сайта имеет приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="56ba4-p106">The following command unassigns any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="56ba4-148">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Grant – CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="56ba4-148">For more information, see the help topic for the [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="56ba4-149">См. также</span><span class="sxs-lookup"><span data-stu-id="56ba4-149">See Also</span></span>


[<span data-ttu-id="56ba4-150">Создание политики архивации в Lync Server 2013 для включения или отключения архивации внутренних или внешних коммуникаций для определенных сайтов или пользователей</span><span class="sxs-lookup"><span data-stu-id="56ba4-150">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)  


[<span data-ttu-id="56ba4-151">Назначение политик для отдельных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56ba4-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

