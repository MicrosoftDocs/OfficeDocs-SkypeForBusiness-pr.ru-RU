---
title: 'Lync Server 2013: назначение политики версий клиентов на уровне пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77b84c4550d44a09e786d09d093e64cbc1901d91
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134465"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="e1a3f-102">Назначение политики версий клиентов на уровне пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1a3f-102">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="e1a3f-103">Политика версий клиентов — это один из индивидуальных параметров учетной записи пользователя, которую можно настроить в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-103">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="e1a3f-104">Развертывание одной или нескольких политик версий клиентов отдельного пользователя является необязательным.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-104">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="e1a3f-105">Также можно развернуть только политику версий клиентов глобального уровня или политики версий клиентов на уровне сайта или пула.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-105">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="e1a3f-106">При развертывании политик для отдельных пользователей необходимо явным образом назначить их пользователям, группам или контактному объекту.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="e1a3f-107">Если определенная политика уровня сайта, пула или уровня сайта не назначена, то клиенты по умолчанию, которым разрешено регистрироваться в Lync Server 2013, определяются в политике версий клиентов глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-107">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="e1a3f-108">После создания хотя бы одной политики версий клиентов на уровне пользователя используйте процедуры, описанные в этом разделе, чтобы назначить политику, указывающую версии клиентов, которые необходимо разрешить для регистрации в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-108">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="e1a3f-109">Дополнительные сведения о создании политик версий клиентов на уровне пользователей можно узнать в статье [Определение клиентских приложений, которые можно использовать для входа в Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="e1a3f-109">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="e1a3f-110">Порядок назначения политик версий клиентов на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="e1a3f-110">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="e1a3f-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e1a3f-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e1a3f-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e1a3f-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e1a3f-114">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="e1a3f-115">Используйте один из следующих методов для поиска пользователя:</span><span class="sxs-lookup"><span data-stu-id="e1a3f-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="e1a3f-116">В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="e1a3f-117">Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="e1a3f-118">(Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:</span><span class="sxs-lookup"><span data-stu-id="e1a3f-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="e1a3f-119">Нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="e1a3f-120">Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="e1a3f-121">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="e1a3f-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="e1a3f-122">В зависимости от выбранного свойства пользователя введите критерии, которые необходимо использовать для фильтрации результатов поиска; для это введите его или щелкните стрелку в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="e1a3f-123">Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="e1a3f-124">Нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-124">Click **Find**.</span></span>

6.  <span data-ttu-id="e1a3f-125">Выберите пользователя в списке результатов поиска, щелкните **Действие**, а затем щелкните **Назначить политики**.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="e1a3f-126">Если необходимо, чтобы одна и та же политика версий клиентов на уровне пользователей применялась к нескольким пользователям, выберите несколько пользователей в результатах поиска, щелкните <STRONG>Действия</STRONG>, а затем щелкните <STRONG>Назначить политики</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-126">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="e1a3f-127">В поле **Назначить политики** раздела **Политика версий клиентов** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e1a3f-127">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="e1a3f-128">Так как существует несколько политик, которые можно настроить с помощью диалогового окна <STRONG>Assign Policies (назначить политики</STRONG> ), <STRONG> &lt;&gt; </STRONG> по умолчанию для каждой политики в диалоговом окне флажок Сохранить как установлен.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="e1a3f-129">Чтобы продолжить использование политики, назначенной пользователю ранее, не вносите никаких изменений в эти настройки.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="e1a3f-130">Разрешить Lync Server автоматически выбирать либо политику глобального уровня, либо политику на уровне сайта или на уровне пула.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-130">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="e1a3f-131">Щелкните имя политики версий клиентов на уровне пользователя, заданной ранее на странице **Политика версий клиентов**.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-131">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="e1a3f-132">Чтобы с легкостью определить политику, которую необходимо назначить, после выбора названия политики щелкните <STRONG>Просмотр</STRONG> для просмотра прав и разрешений пользователя, заданных в политике.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="e1a3f-133">По завершении нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e1a3f-134">Назначение политики версий клиентов на уровне пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1a3f-134">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e1a3f-135">Индивидуальную политику версий клиента можно назначить с помощью командлета Grant-CsClientVersionPolicy.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-135">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="e1a3f-136">Этот командлет можно выполнить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e1a3f-137">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="e1a3f-138">Назначение индивидуальной политики версий клиента одному пользователю</span><span class="sxs-lookup"><span data-stu-id="e1a3f-138">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="e1a3f-139">Следующая команда назначает индивидуальную политику версий клиента RedmondClientVersionPolicy пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-139">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="e1a3f-140">Назначение индивидуальной политики версий клиента нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="e1a3f-140">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="e1a3f-141">Данная команда назначает индивидуальную политику версий клиента RedmondClientVersionPolicy всем пользователям, которым в данный момент назначена политика голосовой связи RedmondVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-141">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="e1a3f-142">Для получения дополнительных сведений о параметре Filter, используемом в этой команде, обратитесь к документации по командлету [Get – CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="e1a3f-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="e1a3f-143">Отмена назначения индивидуальной политики версий клиента</span><span class="sxs-lookup"><span data-stu-id="e1a3f-143">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="e1a3f-p106">Следующая команда отменяет любую индивидуальную политику версий клиента, ранее назначенную пользователю Ken Myer. После отмены назначения индивидуальной политики управление для пользователя Ken Myer автоматически осуществляется с использованием глобальной политики, локальной политики сайта (если она существует) или политикой уровня служб, назначенной его регистратору. Политика уровня служб преобладает над любой политикой сайта, а политика сайта преобладает над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="e1a3f-p106">The following command unassigns any per-user client version policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar. A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="e1a3f-147">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Grant – CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="e1a3f-147">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1a3f-148">См. также</span><span class="sxs-lookup"><span data-stu-id="e1a3f-148">See Also</span></span>


[<span data-ttu-id="e1a3f-149">Назначение политик для отдельных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1a3f-149">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="e1a3f-150">Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1a3f-150">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

