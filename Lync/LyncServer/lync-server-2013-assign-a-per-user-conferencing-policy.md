---
title: 'Lync Server 2013: назначение политики конференц-связи на уровне пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47419dfde4bf41b0edfccb2bce23393f04c49a3d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134455"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="660a2-102">Назначение политики конференц-связи на уровне пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="660a2-102">Assign a per-user conferencing policy in Lync Server 2013</span></span>

 


<span data-ttu-id="660a2-103">Политика конференц-связи — это один из индивидуальных параметров учетной записи пользователя, которую можно настроить в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="660a2-103">The conferencing policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel.</span></span>

<span data-ttu-id="660a2-p101">Развертывание одной или нескольких политик конференц-связи на уровне пользователей не является обязательным. Вы можете развернуть политику конференц-связи только на глобальном уровне или на уровне сайта. Если вы развертываете политики на уровне пользователей, их нужно явно назначить пользователям, группам или объектам контактов. Если не назначена политика на уровне сайта или пользователя, по умолчанию пользователю предоставляются права и разрешения конференц-связи, определенные в глобальной политике конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="660a2-p101">Deploying one or more per-user conferencing policies is optional. You can also deploy only a global-level conferencing policy or site-level conferencing policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects. Conferencing user rights and permissions automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="660a2-108">Создав по крайней мере одну политику конференц-связи на уровне пользователя, определяющую права и разрешения, которые сервер должен предоставлять организованным пользователем собраниям, назначьте ее с помощью инструкций в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="660a2-108">After creating at least one per-user conferencing policy, use the procedures in this topic to assign the policy that specifies the user rights and permissions that you want the server to grant to the meetings organized by a particular user.</span></span>

<span data-ttu-id="660a2-109">Список всех доступных параметров политики конференц-связи представлен в статье [сведения о параметрах политики конференц-связи для Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="660a2-109">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<span data-ttu-id="660a2-110">Дополнительные сведения о создании политик конференц-связи можно найти [в статье Создание или изменение политики конференц-связи в Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="660a2-110">For details about creating conferencing policies, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy"></a><span data-ttu-id="660a2-111">Назначение политики конференц-связи на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="660a2-111">To assign a per-user conferencing policy</span></span>

1.  <span data-ttu-id="660a2-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="660a2-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="660a2-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="660a2-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="660a2-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="660a2-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="660a2-115">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="660a2-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="660a2-116">Используйте один из следующих методов для поиска пользователя:</span><span class="sxs-lookup"><span data-stu-id="660a2-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="660a2-117">В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="660a2-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="660a2-118">Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="660a2-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="660a2-119">(Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:</span><span class="sxs-lookup"><span data-stu-id="660a2-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="660a2-120">Нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="660a2-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="660a2-121">Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="660a2-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="660a2-122">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="660a2-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="660a2-123">В зависимости от выбранного свойства пользователя введите критерии, которые необходимо использовать для фильтрации результатов поиска; для это введите его или щелкните стрелку в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="660a2-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="660a2-124">Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="660a2-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="660a2-125">Нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="660a2-125">Click **Find**.</span></span>

6.  <span data-ttu-id="660a2-126">Выберите пользователя в результатах поиска, щелкните пункт **Действие**, а затем щелкните **Назначить политики**.</span><span class="sxs-lookup"><span data-stu-id="660a2-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="660a2-127">Если вы хотите применить одну политику конференц-связи к нескольким пользователям, выберите в результатах поиска нескольких пользователей, щелкните пункт <STRONG>Действия</STRONG>, а затем щелкните <STRONG>Назначить политики</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="660a2-127">If you want the same per-user conferencing policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="660a2-128">В окне **Назначение политик** в разделе **Политика конференц-связи** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="660a2-128">In **Assign Policies**, under **Conferencing policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="660a2-129">Так как существует несколько политик, которые можно настроить в разделе <STRONG>назначение политик</STRONG>, <STRONG> &lt;&gt; </STRONG> по умолчанию для каждой политики в диалоговом окне выбран параметр Сохранить как.</span><span class="sxs-lookup"><span data-stu-id="660a2-129">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="660a2-130">Чтобы продолжить использование политики, назначенной пользователю ранее, не вносите никаких изменений в эти настройки.</span><span class="sxs-lookup"><span data-stu-id="660a2-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="660a2-131">Выберите \*\* \<автоматически\> \*\* , чтобы разрешить Lync Server 2013 автоматически выбрать политику глобального уровня или, если она определена, политику на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="660a2-131">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="660a2-132">Щелкните название политики конференц-связи на уровне пользователя, которую вы ранее определили на странице **Политика конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="660a2-132">Click the name of a per-user conferencing policy you previously defined on the **Conferencing Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="660a2-133">Чтобы вам было легче определить политику, которую нужно назначить пользователю, после выбора названия политики вы можете нажать кнопку <STRONG>Просмотреть</STRONG>, чтобы просмотреть права и разрешения, определенные в рамках этой политики.</span><span class="sxs-lookup"><span data-stu-id="660a2-133">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="660a2-134">По завершении нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="660a2-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="660a2-135">Назначение политики конференц-связи на уровне пользователя с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="660a2-135">Assigning a Per-User Conferencing Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="660a2-136">Политики конференц-связи для отдельных пользователей можно назначить с помощью Windows PowerShell и командлета Grant-CsConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="660a2-136">Per-user conferencing policies can be assigned by using Windows PowerShell and the Grant-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="660a2-137">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="660a2-137">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="660a2-138">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="660a2-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a><span data-ttu-id="660a2-139">Назначение индивидуальной политики конференц-связи одному пользователю</span><span class="sxs-lookup"><span data-stu-id="660a2-139">To assign a per-user conferencing policy to a single user</span></span>

  - <span data-ttu-id="660a2-140">Следующей командой пользователю Ken Myer назначается политика конференц-связи edmondConferencingPolicy на уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="660a2-140">The following command assigns the per-user conferencing policy RedmondConferencingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a><span data-ttu-id="660a2-141">Назначение политики конференц-связи на уровне пользователей нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="660a2-141">To assign a per-user conferencing policy to multiple users</span></span>

  - <span data-ttu-id="660a2-142">Эта команда назначает политику конференц-связи на уровне пользователя HRConferencingPolicy всем пользователям, которые работают в отделе кадров.</span><span class="sxs-lookup"><span data-stu-id="660a2-142">This command assigns the per-user conferencing policy HRConferencingPolicy to all the users who work for the Human Resources department.</span></span> <span data-ttu-id="660a2-143">Для получения дополнительных сведений о параметре LdapFilter, используемом в этой команде, обратитесь к документации по командлету [Get – CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="660a2-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a><span data-ttu-id="660a2-144">Отмена назначения политики конференц-связи на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="660a2-144">To unassign a per-user conferencing policy</span></span>

  - <span data-ttu-id="660a2-p106">Следующей командой отменяется любая политика конференц-связи на уровне пользователей, ранее назначенная пользователю Ken Myer. После того как политика на уровне пользователей отменена, Ken Myer будет автоматически управляться с помощью глобальной политики или политики его локального сайта, если такая существует. Политика сайта имеет приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="660a2-p106">The following command unassigns any per-user conferencing policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="660a2-148">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Grant – CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="660a2-148">For more information, see the help topic for the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="660a2-149">См. также</span><span class="sxs-lookup"><span data-stu-id="660a2-149">See Also</span></span>


[<span data-ttu-id="660a2-150">Создание или изменение политики конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="660a2-150">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[<span data-ttu-id="660a2-151">Назначение политик для отдельных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="660a2-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

