---
title: 'Lync Server 2013: назначение индивидуальной политики мобильности для пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1014bce74e0e7dcd789c9b2948c029f4b40ecb9a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030142"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="ea457-102">Назначение индивидуальной политики мобильности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea457-102">Assign a per-user mobility policy in Lync Server 2013</span></span>

 


<span data-ttu-id="ea457-103">Политика мобильности — это один из индивидуальных параметров учетной записи пользователя, который можно настроить в панели управления Lync Server или в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ea457-103">The mobility policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel or Lync Server Management Shell.</span></span>

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="ea457-104">Назначение политики мобильности на уровне пользователей с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="ea457-104">To assign a per-user mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ea457-105">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ea457-105">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ea457-106">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ea457-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ea457-107">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ea457-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ea457-108">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="ea457-108">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="ea457-109">Используйте один из следующих методов для поиска пользователя:</span><span class="sxs-lookup"><span data-stu-id="ea457-109">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="ea457-110">В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="ea457-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="ea457-111">Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="ea457-111">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="ea457-112">(Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:</span><span class="sxs-lookup"><span data-stu-id="ea457-112">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="ea457-113">Нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="ea457-113">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="ea457-114">Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="ea457-114">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="ea457-115">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="ea457-115">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="ea457-116">В зависимости от выбранного свойства пользователя введите критерии, которые необходимо использовать для фильтрации результатов поиска; для это введите его или щелкните стрелку в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="ea457-116">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="ea457-117">Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ea457-117">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="ea457-118">Нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="ea457-118">Click **Find**.</span></span>

6.  <span data-ttu-id="ea457-119">Выберите пользователя в списке результатов поиска, щелкните **Action** (Действие), а затем выберите **Assign policies** (Назначить политики).</span><span class="sxs-lookup"><span data-stu-id="ea457-119">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="ea457-120">Если необходимо, чтобы одна и та же политика мобильности применялась к нескольким пользователям, выберите нескольких пользователей в результатах поиска, затем щелкните <STRONG>Actions </STRONG> (Действия) и выберите <STRONG>Assign policies</STRONG> (Назначить политики).</span><span class="sxs-lookup"><span data-stu-id="ea457-120">If you want the same per-user mobility policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="ea457-121">В разделе **Assign Policies** (Назначить политики) выполните одно из следующих действий в области **Mobility policy** (Политика мобильности):</span><span class="sxs-lookup"><span data-stu-id="ea457-121">In **Assign Policies**, under **Mobility policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="ea457-122">Так как существует несколько политик, которые можно настроить в разделе <STRONG>назначение политик</STRONG>, <STRONG> &lt;&gt; </STRONG> по умолчанию для каждой политики в диалоговом окне выбран параметр Сохранить как.</span><span class="sxs-lookup"><span data-stu-id="ea457-122">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="ea457-123">Чтобы продолжить использование политики, назначенной пользователю ранее, не вносите никаких изменений в эти настройки.</span><span class="sxs-lookup"><span data-stu-id="ea457-123">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="ea457-124">Выберите \*\* \<автоматически\> \*\* , чтобы разрешить Lync Server 2013 автоматически выбрать политику глобального уровня или, если она определена, политику на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="ea457-124">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="ea457-125">Щелкните имя индивидуальной политики мобильности, заданной ранее на странице **Mobility Policy** (Политика мобильности).</span><span class="sxs-lookup"><span data-stu-id="ea457-125">Click the name of a per-user mobility policy you previously defined on the **Mobility Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="ea457-126">Чтобы определить, какую политику необходимо назначить, после выбора имени политики щелкните <STRONG>View</STRONG> (Просмотр) для просмотра прав и разрешений пользователя, заданных в политике.</span><span class="sxs-lookup"><span data-stu-id="ea457-126">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="ea457-127">По завершении нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ea457-127">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ea457-128">Назначение политики мобильности на уровне пользователя с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea457-128">Assigning a Per-User Mobility Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ea457-129">Вы можете назначать политики мобильности на уровне пользователей с помощью Windows PowerShell и командлета **Grant – CsMobilityPolicy** .</span><span class="sxs-lookup"><span data-stu-id="ea457-129">You can assign per-user mobility policies by using Windows PowerShell and the **Grant-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="ea457-130">Этот командлет можно выполнить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea457-130">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ea457-131">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="ea457-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a><span data-ttu-id="ea457-132">Назначение индивидуальной политики мобильности отдельному пользователю</span><span class="sxs-lookup"><span data-stu-id="ea457-132">To assign a per-user mobility policy to a single user</span></span>

  - <span data-ttu-id="ea457-133">Следующая команда позволяет назначить индивидуальную политику мобильности RedmondMobilityPolicy пользователю Кену Майеру.</span><span class="sxs-lookup"><span data-stu-id="ea457-133">The following command assigns the per-user mobility policy RedmondMobilityPolicy to the user Ken Myer.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a><span data-ttu-id="ea457-134">Назначение индивидуальной политики мобильности нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="ea457-134">To assign a per-user mobility policy to multiple users</span></span>

  - <span data-ttu-id="ea457-135">Следующая команда назначает политику мобильности "на пользователя" Редмондмобилитиполици всем пользователям, которым назначена политика Норсамерикамобилитиполици.</span><span class="sxs-lookup"><span data-stu-id="ea457-135">The following command assigns the per-user mobility policy RedmondMobilityPolicy to all the users who are currently assigned the policy NorthAmericaMobilityPolicy.</span></span> <span data-ttu-id="ea457-136">Сведения о параметре Filter, используемом в этой команде, приведены в разделе [Get – CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="ea457-136">For details about the Filter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a><span data-ttu-id="ea457-137">Отмена назначения индивидуальной политики мобильности</span><span class="sxs-lookup"><span data-stu-id="ea457-137">To unassign a per-user mobility policy</span></span>

  - <span data-ttu-id="ea457-p105">Следующая команда отменяет назначение каких-либо индивидуальных политик мобильности, ранее назначенных Кену Майеру. После отмены назначения для Кена Майера будет автоматически действовать глобальная политика или локальная политика сайта, если такая существует. Политика сайта имеет приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="ea457-p105">The following command unassigns any per-user mobility policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="ea457-141">Дополнительные сведения см. в разделе [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="ea457-141">For details, see [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="ea457-142">См. также</span><span class="sxs-lookup"><span data-stu-id="ea457-142">See Also</span></span>


[<span data-ttu-id="ea457-143">Настройка политики мобильности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea457-143">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

