---
title: 'Lync Server 2013: назначение политики расположения для отдельных пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a387d0f603addea31bd1e3ee6b591e06a26b2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849795"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a><span data-ttu-id="9a0fc-102">Назначение политики местоположения для каждого пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a0fc-102">Assign a per-user location policy in Lync Server 2013</span></span>

 


<span data-ttu-id="9a0fc-103">Политика расположения — это один из параметров учетной записи пользователя, которую можно настроить на панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-103">The location policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="9a0fc-104">Развертывание одной или нескольких политик на расположение пользователей не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-104">Deploying one or more per-user location policies is optional.</span></span> <span data-ttu-id="9a0fc-105">Вы также можете развернуть только политику глобального уровня расположения или расположение на уровне подсети.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-105">You can also deploy only a global-level location policy or subnet-level location policy.</span></span> <span data-ttu-id="9a0fc-106">Если выполняется развертывание политик на пользователя, необходимо явно назначить их пользователям, группам или контактным объектам.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="9a0fc-107">Улучшенные параметры 9-1-1 (E9-1-1) автоматически по умолчанию заданы в соответствии с политикой расположения глобального уровня, если не назначена ни одна политика для подсети или отдельно для пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-107">Enhanced 9-1-1 (E9-1-1) settings automatically default to those defined in the global-level location policy when no specific subnet-level or per-user policy is assigned.</span></span>

<span data-ttu-id="9a0fc-108">После того как вы создадите хотя бы одну политику для каждого пользователя, выполните описанные в этой статье действия, чтобы назначить политике, указывающую параметры, которые должны применяться сервером для экстренных вызовов, размещенных конкретным пользователем.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-108">After creating at least one per-user location policy, use the procedures in this topic to assign to the policy that specifies the settings that you want the server to apply for emergency calls placed by a particular user.</span></span>

<span data-ttu-id="9a0fc-109">Список всех доступных параметров политики местоположения описан [в разделе Определение политики расположения для Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="9a0fc-109">For a list of all available location policy settings, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="9a0fc-110">Подробнее о создании политик местоположений можно узнать [в статьях создание политик местоположений в Lync Server 2013](lync-server-2013-create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9a0fc-110">For details about creating location policies, see [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span></span>

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a><span data-ttu-id="9a0fc-111">Назначение политики местоположения для пользователя с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="9a0fc-111">To assign a per-user location policy with the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9a0fc-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9a0fc-113">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9a0fc-114">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9a0fc-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9a0fc-115">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="9a0fc-116">Используйте один из следующих методов для обнаружения пользователя:</span><span class="sxs-lookup"><span data-stu-id="9a0fc-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="9a0fc-117">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="9a0fc-118">Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="9a0fc-119">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="9a0fc-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="9a0fc-120">Щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="9a0fc-121">Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="9a0fc-122">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="9a0fc-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="9a0fc-123">В зависимости от выбранного свойства пользователя введите критерии, которые необходимо использовать для фильтрации результатов поиска; для это введите его или щелкните стрелку в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="9a0fc-124">Чтобы добавить в запрос дополнительные условия поиска, щелкните <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="9a0fc-125">Щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-125">Click **Find**.</span></span>

6.  <span data-ttu-id="9a0fc-126">Выберите пользователя в списке результатов поиска, щелкните **Действие**, а затем **Назначить политики**.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="9a0fc-127">Если вы хотите применить одну и ту же политику расположения пользователей для нескольких пользователей, выберите в результатах поиска нескольких пользователей, а затем нажмите кнопку <STRONG>действия</STRONG>и выберите команду <STRONG>назначить политики</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-127">If you want the same per-user location policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="9a0fc-128">В группе **назначение политик**в разделе **Политика расположения**выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-128">In **Assign Policies**, under **Location policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="9a0fc-129">Из <STRONG> &lt;-&gt; </STRONG> за нескольких политик, которые можно настроить с помощью диалогового окна <STRONG>назначение политик</STRONG> , по умолчанию для каждой политики в диалоговом окне выбрать пункт Сохранить как.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="9a0fc-130">Чтобы продолжить использование политики, назначенной пользователю ранее, не вносите никаких изменений в эти настройки.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="9a0fc-131">Разрешение Lync Server 2013 для автоматического выбора политики глобального уровня или, если определено, политики на уровне подсети.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the subnet-level policy.</span></span>
    
      - <span data-ttu-id="9a0fc-132">Щелкните имя политики местонахождения пользователей, которая ранее была определена, запустив командлет **New-кслокатионполици** .</span><span class="sxs-lookup"><span data-stu-id="9a0fc-132">Click the name of a per-user location policy you previously defined by running the **New-CsLocationPolicy** cmdlet.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="9a0fc-133">Чтобы выбрать политику, которую вы хотите назначить, после выбора имени политики нажмите кнопку <STRONG>Просмотр</STRONG> , чтобы просмотреть права и разрешения пользователей, определенные в политике.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="9a0fc-134">По завершении щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a><span data-ttu-id="9a0fc-135">Назначение политики местоположения для пользователя с помощью командлетов командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="9a0fc-135">Assigning a Per-User Location Policy by Using Lync Server Management Shell Cmdlets</span></span>

<span data-ttu-id="9a0fc-136">Политики местоположения для каждого пользователя можно назначить с помощью командлета Grant-Кслокатионполици.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-136">You can assign per-user location policies by using the Grant-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="9a0fc-137">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9a0fc-138">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a><span data-ttu-id="9a0fc-139">Назначение политики местоположения каждому пользователю для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="9a0fc-139">To assign a per-user location policy to a single user</span></span>

  - <span data-ttu-id="9a0fc-140">Указанную ниже команду можно назначить политику расположения пользователя, Редмондлокатионполици с пользователем Кен мер.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-140">The following command assigns the per-user location policy RedmondLocationPolicy to the user Ken Myer.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a><span data-ttu-id="9a0fc-141">Назначение политики местоположения каждому пользователю для нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="9a0fc-141">To assign a per-user location policy to multiple users</span></span>

  - <span data-ttu-id="9a0fc-142">Эта команда назначает политику "на расположение пользователя" Аккаунтингдепартментлокатионполици всем пользователям, которые работают в отделе бухгалтерского учета.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-142">This command assigns the per-user location policy AccountingDepartmentLocationPolicy to all the users who work for the Accounting department.</span></span> <span data-ttu-id="9a0fc-143">Дополнительные сведения о параметре Лдапфилтер, используемом в этой команде, можно найти в документации по командлету [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="9a0fc-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a><span data-ttu-id="9a0fc-144">Отмена политики местоположения для пользователя</span><span class="sxs-lookup"><span data-stu-id="9a0fc-144">To unassign a per-user location policy</span></span>

  - <span data-ttu-id="9a0fc-145">Следующая команда отменяет назначение каждой политики местонахождения пользователя, ранее назначенной для Кен мер.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-145">The following command unassigns any per-user location policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="9a0fc-146">После отмены назначения для Кена Майера будет автоматически действовать глобальная политика или локальная политика сайта, если такая существует.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-146">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="9a0fc-147">Политика сайта имеет приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="9a0fc-147">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="9a0fc-148">Дополнительные сведения можно найти в разделе справки о командлете [Grant-кслокатионполици](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="9a0fc-148">For more information, see the help topic for the [Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) cmdlet.</span></span>

