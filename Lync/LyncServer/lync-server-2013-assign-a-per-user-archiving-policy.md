---
title: 'Lync Server 2013: назначение политики архивации для отдельных пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36d23e44e397a77f0d490d8fda27ee711d1c61c5
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111583"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="09b23-102">Назначение политики архивации по пользователям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09b23-102">Assign a per-user archiving policy in Lync Server 2013</span></span>

 


<span data-ttu-id="09b23-103">Политика архивации — это один из параметров учетной записи пользователя, которую можно настроить на панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="09b23-103">The archiving policy is one of the individual settings of a user account that you can configure in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="09b23-104">Развертывание одной или нескольких политик архивации отдельных пользователей не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="09b23-104">Deploying one or more per-user archiving policies is optional.</span></span> <span data-ttu-id="09b23-105">Вы также можете развернуть только политику архивации глобального уровня или политику архивации на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="09b23-105">You can also deploy only a global-level archiving policy or site-level archiving policy.</span></span> <span data-ttu-id="09b23-106">Если выполняется развертывание политик на пользователя, необходимо явно назначить их пользователям, группам или контактным объектам.</span><span class="sxs-lookup"><span data-stu-id="09b23-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="09b23-107">Требования к архивированию автоматически по умолчанию задаются в политике Конференции глобального уровня, если не назначено ни одного определенного уровня сайта или политики пользователя.</span><span class="sxs-lookup"><span data-stu-id="09b23-107">Archiving requirements automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="09b23-108">После создания хотя бы одной политики архивации для пользователей с помощью описанных в этой статье процедур вы можете назначить политику, которая будет заархивирована на сервере с использованием внутренней связи, внешней связи или того или иного пользователя.</span><span class="sxs-lookup"><span data-stu-id="09b23-108">After creating at least one per-user archiving policy, use the procedures in this topic to assign the policy that appropriately specifies whether a particular user’s internal communications, external communications, or both, will be archived by the server.</span></span>

<span data-ttu-id="09b23-109">Подробнее о создании политик архивации для каждого пользователя можно узнать [в разделе Создание политики архивации в Lync Server 2013, чтобы включить или отключить архивирование внутренних или внешних сообщений для определенных сайтов или пользователей](lync-server-2013-create-archiving-policy-sites-users.md).</span><span class="sxs-lookup"><span data-stu-id="09b23-109">For details about creating per-user archiving policies, see [Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users](lync-server-2013-create-archiving-policy-sites-users.md).</span></span>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="09b23-110">Назначение политики архивации на пользователя</span><span class="sxs-lookup"><span data-stu-id="09b23-110">To assign a per-user archiving policy</span></span>

1.  <span data-ttu-id="09b23-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="09b23-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="09b23-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="09b23-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="09b23-113">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="09b23-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="09b23-114">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="09b23-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="09b23-115">Используйте один из следующих методов для обнаружения пользователя:</span><span class="sxs-lookup"><span data-stu-id="09b23-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="09b23-116">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="09b23-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="09b23-117">Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="09b23-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="09b23-118">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="09b23-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="09b23-119">Щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="09b23-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="09b23-120">Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="09b23-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="09b23-121">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="09b23-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="09b23-122">В зависимости от выбранного свойства пользователя введите критерии, которые необходимо использовать для фильтрации результатов поиска; для это введите его или щелкните стрелку в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="09b23-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="09b23-123">Чтобы добавить в запрос дополнительные условия поиска, щелкните <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="09b23-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="09b23-124">Щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="09b23-124">Click **Find**.</span></span>

6.  <span data-ttu-id="09b23-125">Выберите пользователя в списке результатов поиска, щелкните **Действие**, а затем **Назначить политики**.</span><span class="sxs-lookup"><span data-stu-id="09b23-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="09b23-126">Если вы хотите применить одну и ту же политику архивации пользователей для нескольких пользователей, выберите в результатах поиска нескольких пользователей, а затем нажмите кнопку <STRONG>действия</STRONG>и выберите команду <STRONG>назначить политики</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="09b23-126">If you want the same per-user archiving policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="09b23-127">В группе **назначение политик**в разделе **Политика архивации**выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="09b23-127">In **Assign Policies**, under **Archiving policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="09b23-128">Из <STRONG> &lt;-&gt; </STRONG> за нескольких политик, которые можно настроить с помощью диалогового окна <STRONG>назначение политик</STRONG> , по умолчанию для каждой политики в диалоговом окне выбрать пункт Сохранить как.</span><span class="sxs-lookup"><span data-stu-id="09b23-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="09b23-129">Чтобы продолжить использование политики, назначенной пользователю ранее, не вносите никаких изменений в эти настройки.</span><span class="sxs-lookup"><span data-stu-id="09b23-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="09b23-130">Разрешение Lync Server 2013 для автоматического выбора политики глобального уровня или, если определено, политики на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="09b23-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="09b23-131">Щелкните имя политики архивации для пользователей, определенной ранее на странице " **Политика архивации** ".</span><span class="sxs-lookup"><span data-stu-id="09b23-131">Click the name of a per-user archiving policy you previously defined on the **Archiving Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="09b23-132">Чтобы выбрать политику, которую вы хотите назначить, после выбора имени политики нажмите кнопку <STRONG>Просмотр</STRONG> , чтобы просмотреть права и разрешения пользователей, определенные в политике.</span><span class="sxs-lookup"><span data-stu-id="09b23-132">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="09b23-133">По завершении щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="09b23-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="09b23-134">Назначение политики архивации для пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="09b23-134">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="09b23-135">Вы можете назначать политики архивации для пользователей с помощью Windows PowerShell и командлета **Grant-ксарчивингполици** .</span><span class="sxs-lookup"><span data-stu-id="09b23-135">You can assign per-user archiving policies by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="09b23-136">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09b23-136">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="09b23-137">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09b23-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="09b23-138">Назначение политики архивации отдельных пользователей для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="09b23-138">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="09b23-139">Следующей командой пользователю Ken Myer назначается политика архивации RedmondArchivingPolicy на уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="09b23-139">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="09b23-140">Назначение политики архивации на пользователя для нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="09b23-140">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="09b23-141">Эта команда назначает политику архивации пользователей Редмондарчивингполици всем пользователям, которые имеют учетные записи, размещенные на atl-cs-001.litwareinc.com пула регистраторов.</span><span class="sxs-lookup"><span data-stu-id="09b23-141">This command assigns the per-user archiving policy RedmondArchivingPolicy to all the users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="09b23-142">Дополнительные сведения о параметре фильтрации, используемом в этой команде, можно найти в документации по командлету [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="09b23-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a><span data-ttu-id="09b23-143">Отмена политики архивации для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="09b23-143">To unassign a per-user archiving policy</span></span>

  - <span data-ttu-id="09b23-144">Следующая команда отменяет назначение каждой политики архивации пользователей, ранее назначенной для Кен мер.</span><span class="sxs-lookup"><span data-stu-id="09b23-144">The following command unassigns any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="09b23-145">После отмены назначения для Кена Майера будет автоматически действовать глобальная политика или локальная политика сайта, если такая существует.</span><span class="sxs-lookup"><span data-stu-id="09b23-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="09b23-146">Политика сайта имеет приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="09b23-146">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="09b23-147">Дополнительные сведения можно найти в разделе справки о командлете [Grant-ксарчивингполици](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="09b23-147">For more information, see the help topic for the [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="09b23-148">См. также</span><span class="sxs-lookup"><span data-stu-id="09b23-148">See Also</span></span>


[<span data-ttu-id="09b23-149">Создание политики архивации в Lync Server 2013 для включения и отключения архивации внутренних или внешних сообщений определенных сайтов и пользователей</span><span class="sxs-lookup"><span data-stu-id="09b23-149">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)  


[<span data-ttu-id="09b23-150">Назначение политик для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09b23-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

