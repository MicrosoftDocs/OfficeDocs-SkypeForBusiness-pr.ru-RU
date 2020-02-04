---
title: 'Lync Server 2013: назначение политики ПИН для отдельных пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user PIN policy
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48185475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0864fdf4d2356ee04e1084c2f6b0149b2a6ebd5a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722819"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a><span data-ttu-id="8f9ac-102">Назначение политики PIN-кода для пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f9ac-102">Assign a per-user PIN policy in Lync Server 2013</span></span>

 


<span data-ttu-id="8f9ac-103">Персональный идентификационный номер конференц-связи с телефонным подключением — это один из отдельных параметров учетной записи пользователя, которую можно настроить в панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-103">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="8f9ac-p101">Развертывание одной или нескольких политик ПИН-кода на пользователя выполняется по желанию. Также можно развернуть только политику ПИН-кода глобального уровня или уровня сайта. Если выполняется развертывание политик на пользователя, необходимо явно назначить их пользователям, группам или контактным объектам. Значения по умолчанию прав и разрешений пользователей, связанные с использованием ПИН-кодов для конференц-связи с телефонным подключением, задаются автоматически на основе определенных в политике ПИН-кода глобального уровня, если не назначены политики уровня сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-p101">Deploying one or more per-user PIN policies is optional. You can also deploy only a global-level PIN policy or site-level PIN policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="8f9ac-108">Создав по крайней мере одну политику ПИН-кода на пользователя, используйте процедуры, описанные в этой статье, чтобы назначить политику, указывающую ограничения, которые будут налагаться сервером на ПИН-коды, создаваемые и используемые конкретным пользователем.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-108">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>

<span data-ttu-id="8f9ac-109">Дополнительные сведения о создании политик ПИН для конференц-связи с телефонным подключением для пользователей можно найти [в разделе Создание и изменение параметров контактов для конференц-связи с телефонным подключением в Lync Server 2013 для сайта или группы пользователей](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span><span class="sxs-lookup"><span data-stu-id="8f9ac-109">For details about creating per-user dial-in conferencing PIN policies, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

## <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="8f9ac-110">Назначение политики ПИН-кода на пользователя</span><span class="sxs-lookup"><span data-stu-id="8f9ac-110">To assign a per-user PIN policy</span></span>

1.  <span data-ttu-id="8f9ac-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8f9ac-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8f9ac-113">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8f9ac-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8f9ac-114">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="8f9ac-115">Используйте один из следующих методов для обнаружения пользователя:</span><span class="sxs-lookup"><span data-stu-id="8f9ac-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="8f9ac-116">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="8f9ac-117">Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="8f9ac-118">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="8f9ac-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="8f9ac-119">Щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="8f9ac-120">Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="8f9ac-121">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="8f9ac-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="8f9ac-122">В зависимости от выбранного свойства пользователя введите критерии, которые необходимо использовать для фильтрации результатов поиска; для это введите его или щелкните стрелку в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="8f9ac-123">Чтобы добавить в запрос дополнительные условия поиска, щелкните <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="8f9ac-124">Щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-124">Click **Find**.</span></span>

6.  <span data-ttu-id="8f9ac-125">Выберите пользователя в списке результатов поиска, щелкните **Действие**, а затем **Назначить политики**.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="8f9ac-126">Чтобы применить одну политику ПИН-кода на пользователя к нескольким пользователям, выберите пользователей в результатах поиска, а затем в меню <STRONG>Действия</STRONG> выберите <STRONG>Назначить политики</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-126">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="8f9ac-127">В окне **Назначение политик** в разделе **Политика ПИН-кода** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-127">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="8f9ac-128">Из <STRONG> &lt;-&gt; </STRONG> за нескольких политик, которые можно настроить с помощью диалогового окна <STRONG>назначение политик</STRONG> , по умолчанию для каждой политики в диалоговом окне выбрать пункт Сохранить как.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="8f9ac-129">Чтобы продолжить использование политики, назначенной пользователю ранее, не вносите никаких изменений в эти настройки.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="8f9ac-130">Разрешение Lync Server 2013 для автоматического выбора политики глобального уровня или, если определено, политики на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="8f9ac-131">Щелкните имя политики ПИН-кода на пользователя, ранее заданную на странице **Политика ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-131">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="8f9ac-132">Чтобы с легкостью определить политику, которую необходимо назначить, после выбора названия политики щелкните <STRONG>Просмотр</STRONG> для просмотра прав и разрешений пользователя, заданных в политике.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="8f9ac-133">По завершении щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8f9ac-134">Назначение политики PIN-кода для пользователя с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f9ac-134">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8f9ac-135">Вы можете назначать политики ПИН для каждого пользователя с помощью Windows PowerShell и командлета **Grant-кспинполици** .</span><span class="sxs-lookup"><span data-stu-id="8f9ac-135">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="8f9ac-136">Этот командлет можно выполнить из управляющей оболочки Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8f9ac-137">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="8f9ac-138">Назначение индивидуальной политики ПИН-кодов отдельному пользователю</span><span class="sxs-lookup"><span data-stu-id="8f9ac-138">To assign a per-user PIN policy to a single user</span></span>

  - <span data-ttu-id="8f9ac-139">Следующая команда позволяет назначить индивидуальную политику ПИН-кодов RedmondPinPolicy пользователю Кену Майеру.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-139">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="8f9ac-140">Назначение индивидуальной политики ПИН-кодов нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="8f9ac-140">To assign a per-user PIN policy to multiple users</span></span>

  - <span data-ttu-id="8f9ac-141">Следующая команда назначает политику ПИН для пользователя Редмондусерспинполици всем пользователям, которые работают в городе Redmond.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-141">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="8f9ac-142">Дополнительные сведения о параметре Лдапфилтер, который используется в этой команде, см. в разделе [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="8f9ac-142">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="8f9ac-143">Отмена назначения индивидуальной политики ПИН-кодов</span><span class="sxs-lookup"><span data-stu-id="8f9ac-143">To unassign a per-user PIN policy</span></span>

  - <span data-ttu-id="8f9ac-p106">Следующая команда отменяет назначение каких-либо индивидуальных политик ПИН-кодов, ранее назначенных Кену Майеру. После отмены назначения для Кена Майера будет автоматически действовать глобальная политика или локальная политика сайта, если такая существует. Политика сайта имеет приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="8f9ac-p106">The following command unassigns any per-user PIN policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="8f9ac-147">Подробности можно найти в разделе [Grant-кспинполици](https://technet.microsoft.com/en-us/library/gg398871\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="8f9ac-147">For details, see [Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/gg398871\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="8f9ac-148">См. также</span><span class="sxs-lookup"><span data-stu-id="8f9ac-148">See Also</span></span>


[<span data-ttu-id="8f9ac-149">Создание новой политики ПИН-кода в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f9ac-149">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  


[<span data-ttu-id="8f9ac-150">Назначение политик для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f9ac-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

