---
title: 'Lync Server 2013: перемещение пользователей в другой пул'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d2702e744fbadc5d51ea42095d7bd3d60f6f010
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a><span data-ttu-id="ca75e-102">Перемещение пользователей в другой пул в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca75e-102">Move users to another pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="ca75e-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="ca75e-103">

<span> </span></span></span>

<span data-ttu-id="ca75e-104">_**Последнее изменение темы:** 2018-02-09_</span><span class="sxs-lookup"><span data-stu-id="ca75e-104">_**Topic Last Modified:** 2018-02-09_</span></span>

<span data-ttu-id="ca75e-105">С помощью панели управления Lync Server можно назначать пользователей конкретному серверу или пулу.</span><span class="sxs-lookup"><span data-stu-id="ca75e-105">You can use Lync Server Control Panel to assign users to a specific server or pool.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="ca75e-106">Перемещение всех существующих пользователей из исходного пула, на котором работает Lync Server 2010 или более ранней версии, в пул назначения Lync Server 2013 в сложной среде Active Directory может привести к более медленной репликации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ca75e-106">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Lync Server 2013 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="ca75e-107">Чтобы избежать этого, можно использовать фильтры поиска для перемещения пользователей из пулов, работающих под управлением Lync Server 2010 или более ранних версий, а также с помощью командной консоли Lync Server для перемещения пользователей с помощью командлетов.</span><span class="sxs-lookup"><span data-stu-id="ca75e-107">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Lync Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="ca75e-108">Кроме того, функция фильтрации работает с пользователями Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca75e-108">Also, the filter functionality works with Lync Server 2013 users.</span></span>



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="ca75e-109">Перемещение выбранных пользователей на другой сервер или в другой пул</span><span class="sxs-lookup"><span data-stu-id="ca75e-109">To move selected users to a different server or pool</span></span>

1.  <span data-ttu-id="ca75e-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ca75e-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ca75e-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ca75e-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ca75e-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ca75e-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ca75e-113">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="ca75e-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="ca75e-114">В поле **Search users** (Поиск пользователей) полностью или частично введите полное имя, отображаемое имя, имя, фамилию, имя учетной записи диспетчера учетных записей безопасности,  SIP-адрес или универсальный код ресурса (URI) требуемой учетной записи пользователя, а затем нажмите кнопку **Find** (Найти).</span><span class="sxs-lookup"><span data-stu-id="ca75e-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="ca75e-115">В списке таблицы выберите одного или нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="ca75e-115">In the table, select a specific user or users in the list.</span></span>

6.  <span data-ttu-id="ca75e-116">В меню **Actions** (Действия) щелкните пункт **Move selected users to pool** (Переместить выбранных пользователей в пул).</span><span class="sxs-lookup"><span data-stu-id="ca75e-116">On the **Action** menu, click **Move selected users to pool**.</span></span>

7.  <span data-ttu-id="ca75e-117">В поле **Destination registrar pool** (Конечный пул регистратора) окна **Move Users** (Перемещение пользователей) выберите пул, в который необходимо переместить пользователей.</span><span class="sxs-lookup"><span data-stu-id="ca75e-117">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>

8.  <span data-ttu-id="ca75e-118">(Необязательно) Если конечный сервер или пул недоступен, установите флажок **Force** (Принудительно).</span><span class="sxs-lookup"><span data-stu-id="ca75e-118">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="ca75e-119">Если выбран параметр <STRONG>Force</STRONG>, учетная запись пользователя перемещается, но связанные данные пользователя, такие как запланированные конференции и контакты, не перемещаются.</span><span class="sxs-lookup"><span data-stu-id="ca75e-119">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="ca75e-120">Перемещение всех пользователей из одного сервера или пула на другой сервер или в другой пул</span><span class="sxs-lookup"><span data-stu-id="ca75e-120">To move all users from one server or pool to a different server or pool</span></span>

1.  <span data-ttu-id="ca75e-121">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ca75e-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ca75e-122">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ca75e-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ca75e-123">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ca75e-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ca75e-124">В левой панели навигации щелкните элемент **Users** (Пользователи).</span><span class="sxs-lookup"><span data-stu-id="ca75e-124">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="ca75e-125">В меню **Actions** (Действия) щелкните пункт **Move all users to pool** (Переместить всех пользователей в пул).</span><span class="sxs-lookup"><span data-stu-id="ca75e-125">On the **Action** menu, click **Move all users to pool**.</span></span>

5.  <span data-ttu-id="ca75e-126">В поле **Source registrar pool** (Исходный пул регистратора) окна **Move Users** (Перемещение пользователей) выберите пул, содержащий учетные записи пользователей, которые необходимо переместить.</span><span class="sxs-lookup"><span data-stu-id="ca75e-126">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

6.  <span data-ttu-id="ca75e-127">В поле **Destination registrar pool** (Конечный пул регистратора), выберите пул, в который необходимо переместить пользователей.</span><span class="sxs-lookup"><span data-stu-id="ca75e-127">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>

7.  <span data-ttu-id="ca75e-128">(Необязательно) Если конечный сервер или пул недоступен, установите флажок **Force** (Принудительно).</span><span class="sxs-lookup"><span data-stu-id="ca75e-128">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="ca75e-129">Если выбран параметр <STRONG>Force</STRONG>, учетная запись пользователя перемещается, но связанные данные пользователя, такие как запланированные конференции и контакты, не перемещаются.</span><span class="sxs-lookup"><span data-stu-id="ca75e-129">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="ca75e-130">Перемещение пользователей из одного пула в другой пул с использованием фильтра</span><span class="sxs-lookup"><span data-stu-id="ca75e-130">To move users from one pool to a different pool by using a filter</span></span>

1.  <span data-ttu-id="ca75e-131">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ca75e-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ca75e-132">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ca75e-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ca75e-133">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ca75e-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ca75e-134">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="ca75e-134">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="ca75e-135">В окне **Поиск пользователей**нажмите кнопку **Поиск**, а затем щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="ca75e-135">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>

5.  <span data-ttu-id="ca75e-136">В области условий поиска выберите **Registrar Pool** (Пул регистратора), **Equal to** (Равно), **Current Pool FQDN** (Текущее полное доменное имя пула) и затем нажмите кнопку **Find** (Найти).</span><span class="sxs-lookup"><span data-stu-id="ca75e-136">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>

6.  <span data-ttu-id="ca75e-137">В меню **Actions** (Действия) щелкните пункт **Move all users to pool** (Переместить всех пользователей в пул).</span><span class="sxs-lookup"><span data-stu-id="ca75e-137">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca75e-138">Если фильтр применяется к существующему набору пользователей, параметр <STRONG>переместить всех пользователей в пул</STRONG> — это контекст фильтрованного подмножества пользователей, а не <STRONG><EM>всех</EM></STRONG> возможных пользователей.</span><span class="sxs-lookup"><span data-stu-id="ca75e-138">When a filter is applied to an existing set of users, the option <STRONG>Move all users to pool</STRONG> is in the context of the filtered subset of users, not <STRONG><EM>all</EM></STRONG> possible users.</span></span>

    
    </div>

7.  <span data-ttu-id="ca75e-139">В поле **Source registrar pool** (Исходный пул регистратора) окна **Move Users** (Перемещение пользователей) выберите пул, содержащий учетные записи пользователей, которые необходимо переместить.</span><span class="sxs-lookup"><span data-stu-id="ca75e-139">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

8.  <span data-ttu-id="ca75e-140">В поле **Destination registrar pool** (Конечный пул регистратора), выберите пул, в который необходимо переместить пользователей.</span><span class="sxs-lookup"><span data-stu-id="ca75e-140">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>

9.  <span data-ttu-id="ca75e-141">(Необязательно) Если конечный сервер или пул недоступен, установите флажок **Force** (Принудительно).</span><span class="sxs-lookup"><span data-stu-id="ca75e-141">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="ca75e-142">Если выбран параметр <STRONG>Force</STRONG>, учетная запись пользователя перемещается, но связанные данные пользователя, такие как запланированные конференции и контакты, не перемещаются.</span><span class="sxs-lookup"><span data-stu-id="ca75e-142">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="ca75e-143">Перемещение пользователей из одного пула в другой с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca75e-143">To move users from one pool to another using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="ca75e-144">В зависимости от того, как выполняются команды Windows PowerShell (локально или удаленно), необходимо войти в систему в качестве члена правильной административной роли Lync Server 2013 следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ca75e-144">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Lync Server 2013 administrative roles as follows:</span></span>
    
    1.  <span data-ttu-id="ca75e-145">Если вы выполняете команды на локальном компьютере (например, входите прямо на сервер переднего плана): Войдите на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ca75e-145">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>
    
    2.  <span data-ttu-id="ca75e-146">Если вы выполняете команды удаленно на другом компьютере (например, входите на компьютер и выполняете команды удаленно на сервере переднего плана Standard Edition): от учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator роль Войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="ca75e-146">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ca75e-147">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ca75e-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ca75e-148">Для перемещения отдельных пользователей используйте командлет Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="ca75e-148">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    <span data-ttu-id="ca75e-149">Здесь пользователь Pilar Ackerman перемещается из назначенного в данный момент домашнего пула в пул pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="ca75e-149">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>

4.  <span data-ttu-id="ca75e-150">Для перемещения большого числа пользователей используйте фильтры совместно с командлетом **Get-CsUser** и передавайте полученный набор пользователей в командлет **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="ca75e-150">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    <span data-ttu-id="ca75e-151">Совмещение команд **Get-CsUser** и **Move-CsUser** может дать следующий результат:</span><span class="sxs-lookup"><span data-stu-id="ca75e-151">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca75e-152">См. также</span><span class="sxs-lookup"><span data-stu-id="ca75e-152">See Also</span></span>


[<span data-ttu-id="ca75e-153">Изменение свойств учетной записи пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca75e-153">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

<span data-ttu-id="ca75e-154"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="ca75e-154"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

