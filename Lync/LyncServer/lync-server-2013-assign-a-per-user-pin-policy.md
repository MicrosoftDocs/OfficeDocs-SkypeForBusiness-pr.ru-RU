---
title: 'Lync Server 2013: назначение политики ПИН-кодов для отдельных пользователей'
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
ms.openlocfilehash: 9523794808ca3b689cf1f3213c1f4ad657c83c25
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030122"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a><span data-ttu-id="2f7c2-102">Назначение политики ПИН-кодов для отдельных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f7c2-102">Assign a per-user PIN policy in Lync Server 2013</span></span>

 


<span data-ttu-id="2f7c2-103">Политика ПИН-кода конференц-связи с телефонным подключением — это один из индивидуальных параметров учетной записи пользователя, который можно настроить в панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-103">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="2f7c2-104">Развертывать одну или несколько политик ПИН-кодов для отдельных пользователей не обязательно.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-104">Deploying one or more per-user PIN policies is optional.</span></span> <span data-ttu-id="2f7c2-105">Вы также можете развернуть только глобальную политику ПИН-кодов или политику ПИН-кодов на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-105">You can also deploy only a global-level PIN policy or site-level PIN policy.</span></span> <span data-ttu-id="2f7c2-106">При развертывании политик для отдельных пользователей необходимо явным образом назначить их пользователям, группам или контактному объекту.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="2f7c2-107">Права и разрешения пользователей, относящиеся к использованию ПИН-кодов для конференц-связи с телефонным подключением, автоматически задаются по умолчанию в политике ПИН-кода глобального уровня, если не назначена определенная политика на уровне сайта или на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-107">User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="2f7c2-108">После создания хотя бы одной политики ПИН-кодов для отдельных пользователей используйте процедуры, описанные в этом разделе, чтобы назначить политику, определяющую ограничения, которые сервер должен применять к ПИН-кодам, созданным и используемым конкретным пользователем.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-108">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>

<span data-ttu-id="2f7c2-109">Дополнительные сведения о создании политик ПИН-кодов для конференц-связи с телефонным подключением для отдельных пользователей приведены [в статье Создание или изменение параметров ПИН-кода конференц-связи с телефонным подключением в Lync Server 2013 для сайта или группы пользователей](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span><span class="sxs-lookup"><span data-stu-id="2f7c2-109">For details about creating per-user dial-in conferencing PIN policies, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

## <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="2f7c2-110">Назначение политики ПИН-кодов для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="2f7c2-110">To assign a per-user PIN policy</span></span>

1.  <span data-ttu-id="2f7c2-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2f7c2-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2f7c2-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2f7c2-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2f7c2-114">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="2f7c2-115">Используйте один из следующих методов для поиска пользователя:</span><span class="sxs-lookup"><span data-stu-id="2f7c2-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="2f7c2-116">В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="2f7c2-117">Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="2f7c2-118">(Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:</span><span class="sxs-lookup"><span data-stu-id="2f7c2-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="2f7c2-119">Нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="2f7c2-120">Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="2f7c2-121">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="2f7c2-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="2f7c2-122">В зависимости от выбранного свойства пользователя введите критерии, которые необходимо использовать для фильтрации результатов поиска; для это введите его или щелкните стрелку в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="2f7c2-123">Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="2f7c2-124">Нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-124">Click **Find**.</span></span>

6.  <span data-ttu-id="2f7c2-125">Выберите пользователя в списке результатов поиска, щелкните **Действие**, а затем щелкните **Назначить политики**.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="2f7c2-126">Чтобы применить одну политику ПИН-кода на уровне пользователя к нескольким пользователям, выберите несколько пользователей в результатах поиска, щелкните <STRONG>действия</STRONG>, а затем выберите <STRONG>назначить политики</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-126">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="2f7c2-127">В разделе **назначение политик**в разделе **политика ПИН-кода**выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-127">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="2f7c2-128">Так как существует несколько политик, которые можно настроить с помощью диалогового окна <STRONG>Assign Policies (назначить политики</STRONG> ), <STRONG> &lt;&gt; </STRONG> по умолчанию для каждой политики в диалоговом окне флажок Сохранить как установлен.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="2f7c2-129">Чтобы продолжить использование политики, назначенной пользователю ранее, не вносите никаких изменений в эти настройки.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="2f7c2-130">Разрешить Lync Server 2013 автоматически выбирать политику глобального уровня или, если определено, политику на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="2f7c2-131">Щелкните имя политики ПИН-кода на уровне пользователя, заданной ранее на странице **политика ПИН-кода** .</span><span class="sxs-lookup"><span data-stu-id="2f7c2-131">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="2f7c2-132">Чтобы с легкостью определить политику, которую необходимо назначить, после выбора названия политики щелкните <STRONG>Просмотр</STRONG> для просмотра прав и разрешений пользователя, заданных в политике.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="2f7c2-133">По завершении нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2f7c2-134">Назначение политики ПИН-кодов для отдельных пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f7c2-134">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2f7c2-135">Политики ПИН-кодов для отдельных пользователей можно назначить с помощью Windows PowerShell и командлета **Grant-CsPinPolicy** .</span><span class="sxs-lookup"><span data-stu-id="2f7c2-135">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="2f7c2-136">Этот командлет можно выполнить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2f7c2-137">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="2f7c2-138">Назначение индивидуальной политики ПИН-кодов для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="2f7c2-138">To assign a per-user PIN policy to a single user</span></span>

  - <span data-ttu-id="2f7c2-139">Следующая команда назначает политику ПИН-кода на пользователя RedmondPinPolicy пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-139">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="2f7c2-140">Назначение индивидуальной политики ПИН-кодов нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="2f7c2-140">To assign a per-user PIN policy to multiple users</span></span>

  - <span data-ttu-id="2f7c2-141">Следующая команда назначает политику ПИН-кода на уровне пользователя RedmondUsersPinPolicy всем пользователям, которые работают в городе Redmond.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-141">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="2f7c2-142">Сведения о параметре LdapFilter, используемом в этой команде, приведены в разделе [Get – CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="2f7c2-142">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="2f7c2-143">Отмена назначения политики ПИН-кодов для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="2f7c2-143">To unassign a per-user PIN policy</span></span>

  - <span data-ttu-id="2f7c2-144">Следующая команда отменяет назначение любой политики ПИН-кода на пользователя, которая ранее была назначена Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-144">The following command unassigns any per-user PIN policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="2f7c2-145">После отмены назначения политики пользователь Ken Myer будет автоматически управляться глобальной политикой или, если такая существует, локальной политикой сайта.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="2f7c2-146">Политика сайта имеет более высокий приоритет, чем глобальная политика.</span><span class="sxs-lookup"><span data-stu-id="2f7c2-146">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="2f7c2-147">Дополнительные сведения см. в разделе [Grant – CsPinPolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="2f7c2-147">For details, see [Grant-CsPinPolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="2f7c2-148">См. также</span><span class="sxs-lookup"><span data-stu-id="2f7c2-148">See Also</span></span>


[<span data-ttu-id="2f7c2-149">Создание новой политики ПИН-кодов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f7c2-149">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  


[<span data-ttu-id="2f7c2-150">Назначение политик для отдельных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f7c2-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

