---
title: 'Lync Server 2013: назначение политики расположения для отдельных пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d66df7f2d0c8a2b8603f7c08312f5b8b6aaad56
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134435"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a><span data-ttu-id="84683-102">Назначение политики расположения для отдельных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84683-102">Assign a per-user location policy in Lync Server 2013</span></span>

 


<span data-ttu-id="84683-103">Политика расположения — это один из индивидуальных параметров учетной записи пользователя, которую можно настроить в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="84683-103">The location policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="84683-p101">Развертывание одной или нескольких политик расположения для каждого пользователя необязательно. Вы также можете развернуть политику расположения только на глобальном уровне или уровне подсети. Если вы все таки развертываете политики для каждого пользователя, необходимо явно назначить их пользователям, группам или объекту контакта. Параметры E9-1-1 по умолчанию автоматически используют значения, определенные в политике глобального уровня при отсутствии политики уровня подсети или отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="84683-p101">Deploying one or more per-user location policies is optional. You can also deploy only a global-level location policy or subnet-level location policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. Enhanced 9-1-1 (E9-1-1) settings automatically default to those defined in the global-level location policy when no specific subnet-level or per-user policy is assigned.</span></span>

<span data-ttu-id="84683-108">После создания хотя бы одной политики расположения для отдельных пользователей используйте процедуры, описанные в этом разделе, чтобы назначить политику, указывающей параметры, которые необходимо применить на сервере для экстренных вызовов конкретного пользователя.</span><span class="sxs-lookup"><span data-stu-id="84683-108">After creating at least one per-user location policy, use the procedures in this topic to assign to the policy that specifies the settings that you want the server to apply for emergency calls placed by a particular user.</span></span>

<span data-ttu-id="84683-109">Список всех доступных параметров политики расположения приведен в разделе [Определение политики расположения для Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="84683-109">For a list of all available location policy settings, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="84683-110">Более подробную информацию о создании политик расположения можно узнать [в статье Создание политик расположения в Lync Server 2013](lync-server-2013-create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="84683-110">For details about creating location policies, see [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span></span>

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a><span data-ttu-id="84683-111">Назначение политики расположения для отдельных пользователей с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="84683-111">To assign a per-user location policy with the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="84683-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="84683-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="84683-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="84683-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="84683-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="84683-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="84683-115">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="84683-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="84683-116">Используйте один из следующих методов для поиска пользователя:</span><span class="sxs-lookup"><span data-stu-id="84683-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="84683-117">В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="84683-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="84683-118">Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="84683-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="84683-119">(Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:</span><span class="sxs-lookup"><span data-stu-id="84683-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="84683-120">Нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="84683-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="84683-121">Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="84683-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="84683-122">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="84683-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="84683-123">В зависимости от выбранного свойства пользователя введите критерии, которые необходимо использовать для фильтрации результатов поиска; для это введите его или щелкните стрелку в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="84683-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="84683-124">Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="84683-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="84683-125">Нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="84683-125">Click **Find**.</span></span>

6.  <span data-ttu-id="84683-126">Выберите пользователя в результатах поиска щелкните **Действие**, а затем выберите **Назначить политики**.</span><span class="sxs-lookup"><span data-stu-id="84683-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="84683-127">Если вы хотите, чтобы та же политика расположения для отдельного пользователя применялась к нескольким пользователям, выберите несколько пользователей в результатах поиска, щелкните <STRONG>Действия</STRONG>, а затем выберите параметр <STRONG>Назначить политики</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="84683-127">If you want the same per-user location policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="84683-128">В окне **Назначение политики** в разделе **Политика расположения** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="84683-128">In **Assign Policies**, under **Location policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="84683-129">Так как существует несколько политик, которые можно настроить с помощью диалогового окна <STRONG>Assign Policies (назначить политики</STRONG> ), <STRONG> &lt;&gt; </STRONG> по умолчанию для каждой политики в диалоговом окне флажок Сохранить как установлен.</span><span class="sxs-lookup"><span data-stu-id="84683-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="84683-130">Чтобы продолжить использование политики, назначенной пользователю ранее, не вносите никаких изменений в эти настройки.</span><span class="sxs-lookup"><span data-stu-id="84683-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="84683-131">Разрешить Lync Server 2013 автоматически выбирать политику глобального уровня или, если определено, политику на уровне подсети.</span><span class="sxs-lookup"><span data-stu-id="84683-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the subnet-level policy.</span></span>
    
      - <span data-ttu-id="84683-132">Щелкните имя политика расположения для пользователя, заданную ранее с помощью командлета **New-CsLocationPolicy**.</span><span class="sxs-lookup"><span data-stu-id="84683-132">Click the name of a per-user location policy you previously defined by running the **New-CsLocationPolicy** cmdlet.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="84683-133">Чтобы помочь вам определить политики, которые необходимо назначить, после выбора имени политики нажмите кнопку <STRONG>Просмотр</STRONG>, чтобы просмотреть права и разрешения пользователя, определенные политикой.</span><span class="sxs-lookup"><span data-stu-id="84683-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="84683-134">Закончив, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="84683-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a><span data-ttu-id="84683-135">Назначение политики расположения для отдельных пользователей с помощью командлетов командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="84683-135">Assigning a Per-User Location Policy by Using Lync Server Management Shell Cmdlets</span></span>

<span data-ttu-id="84683-136">Политики расположения для отдельных пользователей можно назначить с помощью командлета Grant – CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="84683-136">You can assign per-user location policies by using the Grant-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="84683-137">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84683-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="84683-138">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="84683-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a><span data-ttu-id="84683-139">Назначение политики расположения для отдельных пользователей одному пользователю</span><span class="sxs-lookup"><span data-stu-id="84683-139">To assign a per-user location policy to a single user</span></span>

  - <span data-ttu-id="84683-140">В приведенной ниже команде политика расположения RedmondLocationPolicy назначается пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="84683-140">The following command assigns the per-user location policy RedmondLocationPolicy to the user Ken Myer.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a><span data-ttu-id="84683-141">Назначение политики расположения для отдельных пользователей нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="84683-141">To assign a per-user location policy to multiple users</span></span>

  - <span data-ttu-id="84683-142">Эта команда назначает политику расположения AccountingDepartmentLocationPolicy всем пользователям, работающим в бухгалтерии (Accounting).</span><span class="sxs-lookup"><span data-stu-id="84683-142">This command assigns the per-user location policy AccountingDepartmentLocationPolicy to all the users who work for the Accounting department.</span></span> <span data-ttu-id="84683-143">Для получения дополнительных сведений о параметре LdapFilter, используемом в этой команде, обратитесь к документации по командлету [Get – CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="84683-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a><span data-ttu-id="84683-144">Отмена политики расположения для отдельного пользователя</span><span class="sxs-lookup"><span data-stu-id="84683-144">To unassign a per-user location policy</span></span>

  - <span data-ttu-id="84683-p106">Приведенная ниже команда отменяет политику расположения, назначенную ранее пользователю Ken Myer. После отмены этой политики к пользователю Ken Myer будет автоматически применяться глобальная политика или локальная политика сайта, если таковая существует. Политика сайта имеет преимущество перед глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="84683-p106">The following command unassigns any per-user location policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="84683-148">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Grant – CsLocationPolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="84683-148">For more information, see the help topic for the [Grant-CsLocationPolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) cmdlet.</span></span>

