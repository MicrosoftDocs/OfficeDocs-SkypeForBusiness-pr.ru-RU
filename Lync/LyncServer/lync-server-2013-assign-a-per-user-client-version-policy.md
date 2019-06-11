---
title: 'Lync Server 2013: назначение политики клиентской версии для пользователя'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bfd26aff4ae2e5d8dacf7ec145bec0e3247facf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841753"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="a3594-102">Назначение политики клиентской версии для пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3594-102">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="a3594-103">Политика Client Version — это один из параметров учетной записи пользователя, которую можно настроить на панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3594-103">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="a3594-104">Развертывание одной или нескольких политик клиентской версии для каждого пользователя является необязательным.</span><span class="sxs-lookup"><span data-stu-id="a3594-104">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="a3594-105">Вы также можете развернуть только политику глобального уровня клиента или политики версии на уровне сайта или в пуле для клиента.</span><span class="sxs-lookup"><span data-stu-id="a3594-105">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="a3594-106">Если выполняется развертывание политик на пользователя, необходимо явно назначить их пользователям, группам или контактным объектам.</span><span class="sxs-lookup"><span data-stu-id="a3594-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="a3594-107">Если вы не назначили определенную политику на уровне сайта, в пуле или на уровне пользователя, в Lync Server 2013 используются клиенты по умолчанию, которые могут регистрироваться в соответствии с политикой версии глобального уровня в клиенте.</span><span class="sxs-lookup"><span data-stu-id="a3594-107">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="a3594-108">После создания хотя бы одной политики клиентской версии для пользователей используйте процедуры из этого раздела, чтобы назначить политику, указывающую версии клиентов, которые нужно разрешить для регистрации в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3594-108">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="a3594-109">Дополнительные сведения о создании политик клиентской версии для каждого пользователя можно найти в разделе [Определение клиентских приложений, которые могут использоваться для входа в Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="a3594-109">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="a3594-110">Назначение политики клиентской версии для пользователя</span><span class="sxs-lookup"><span data-stu-id="a3594-110">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="a3594-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a3594-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a3594-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3594-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a3594-113">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a3594-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a3594-114">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="a3594-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="a3594-115">Используйте один из следующих методов для обнаружения пользователя:</span><span class="sxs-lookup"><span data-stu-id="a3594-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="a3594-116">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="a3594-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="a3594-117">Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="a3594-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="a3594-118">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="a3594-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="a3594-119">Щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="a3594-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="a3594-120">Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="a3594-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="a3594-121">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="a3594-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="a3594-122">В зависимости от выбранного свойства пользователя введите критерии, которые необходимо использовать для фильтрации результатов поиска; для это введите его или щелкните стрелку в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="a3594-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="a3594-123">Чтобы добавить в запрос дополнительные условия поиска, щелкните <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a3594-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="a3594-124">Щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="a3594-124">Click **Find**.</span></span>

6.  <span data-ttu-id="a3594-125">Выберите пользователя в списке результатов поиска, щелкните **Действие**, а затем **Назначить политики**.</span><span class="sxs-lookup"><span data-stu-id="a3594-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="a3594-126">Если вы хотите применить одну и ту же политику пользовательской версии для нескольких пользователей, выберите в результатах поиска нескольких пользователей, а затем нажмите кнопку <STRONG>действия</STRONG>и выберите команду <STRONG>назначить политики</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a3594-126">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="a3594-127">В группе **назначение политик**в разделе **Политика версии клиента**выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="a3594-127">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="a3594-128">Из <STRONG> &lt;-&gt; </STRONG> за нескольких политик, которые можно настроить с помощью диалогового окна <STRONG>назначение политик</STRONG> , по умолчанию для каждой политики в диалоговом окне выбрать пункт Сохранить как.</span><span class="sxs-lookup"><span data-stu-id="a3594-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="a3594-129">Чтобы продолжить использование политики, назначенной пользователю ранее, не вносите никаких изменений в эти настройки.</span><span class="sxs-lookup"><span data-stu-id="a3594-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="a3594-130">Разрешить Lync Server автоматический выбор политики глобального уровня или, если она определена, политики уровня сайта или политики уровня пула.</span><span class="sxs-lookup"><span data-stu-id="a3594-130">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="a3594-131">Щелкните имя политики клиентской версии, которая ранее была определена на странице **политики Client Version** .</span><span class="sxs-lookup"><span data-stu-id="a3594-131">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="a3594-132">Чтобы с легкостью определить политику, которую необходимо назначить, после выбора названия политики щелкните <STRONG>Просмотр</STRONG> для просмотра прав и разрешений пользователя, заданных в политике.</span><span class="sxs-lookup"><span data-stu-id="a3594-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="a3594-133">По завершении щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a3594-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a3594-134">Назначение политики клиентской версии для пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3594-134">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a3594-135">Вы можете назначить политики клиентской версии для пользователей с помощью командлета Grant-Ксклиентверсионполици.</span><span class="sxs-lookup"><span data-stu-id="a3594-135">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="a3594-136">Этот командлет можно выполнить из управляющей оболочки Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3594-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a3594-137">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3594-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="a3594-138">Назначение индивидуальной политики клиентской версии для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="a3594-138">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="a3594-139">Следующая команда назначает пользователю политику пользовательской версии для пользователя Редмондклиентверсионполици, которая Кен мер.</span><span class="sxs-lookup"><span data-stu-id="a3594-139">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="a3594-140">Назначение политики клиентской версии для каждого пользователя нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="a3594-140">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="a3594-141">Эта команда назначает политику клиентской версии для пользователя Редмондклиентверсионполици всем пользователям, которым в данный момент назначена политика голосовой связи Редмондвоицеполици.</span><span class="sxs-lookup"><span data-stu-id="a3594-141">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="a3594-142">Дополнительные сведения о параметре фильтрации, используемом в этой команде, можно найти в документации по командлету [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="a3594-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="a3594-143">Отмена политики клиентской версии для пользователя</span><span class="sxs-lookup"><span data-stu-id="a3594-143">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="a3594-144">Следующая команда отменяет назначение любой политики клиентской версии для каждого пользователя, ранее назначенной для Кен мер.</span><span class="sxs-lookup"><span data-stu-id="a3594-144">The following command unassigns any per-user client version policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="a3594-145">После того как политика для пользователя не будет назначена, Кен мер будет автоматически управляться с помощью глобальной политики, политики локального сайта (если она существует) или политики области действия, назначенной своему регистратору.</span><span class="sxs-lookup"><span data-stu-id="a3594-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar.</span></span> <span data-ttu-id="a3594-146">Политика области обслуживания имеет приоритет над любой политикой сайта, а политика сайта имеет приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="a3594-146">A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="a3594-147">Дополнительные сведения можно найти в разделе справки о командлете [Grant-ксклиентверсионполици](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="a3594-147">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3594-148">См. также</span><span class="sxs-lookup"><span data-stu-id="a3594-148">See Also</span></span>


[<span data-ttu-id="a3594-149">Назначение политик для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3594-149">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="a3594-150">Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3594-150">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

