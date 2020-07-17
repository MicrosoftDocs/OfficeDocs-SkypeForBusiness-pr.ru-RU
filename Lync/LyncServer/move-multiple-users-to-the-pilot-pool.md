---
title: Перемещение нескольких пользователей в пилотный пул
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a5a92b0438e72be0ecb5acaa1b8e1886768ad59
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="045d8-102">Перемещение нескольких пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="045d8-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="045d8-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="045d8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="045d8-104">Можно переместить несколько пользователей из пула Lync Server 2010 в пилотный пул Lync Server 2013 с помощью панели управления Lync Server 2013 или консоли управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="045d8-104">You can move multiple users from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="045d8-105">Перемещение нескольких пользователей с помощью панели управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="045d8-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="045d8-106">Откройте **Панель управления Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="045d8-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="045d8-107">Щелкните **Пользователи**, затем выберите поиск и нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="045d8-107">Click **Users**, click Search, and then click **Find**.</span></span>

3.  <span data-ttu-id="045d8-108">Выберите двух пользователей, которых нужно переместить в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="045d8-108">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="045d8-109">В этом примере мы переместим пользователей Chen Yang и Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="045d8-109">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="045d8-110">![Перемещение пользователей в определенный пул регистров](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Перемещение пользователей в определенный пул регистров")</span><span class="sxs-lookup"><span data-stu-id="045d8-110">![Move users to specific register pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Move users to specific register pool")</span></span>  

4.  <span data-ttu-id="045d8-111">В меню **Макрокоманда** выберите **Переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="045d8-111">From the **Action** menu, select **Move selected users to pool**.</span></span>

5.  <span data-ttu-id="045d8-112">В раскрывающемся списке выберите пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="045d8-112">From the drop-down list, select the Lync Server 2013 pool.</span></span>

6.  <span data-ttu-id="045d8-113">Щелкните **Макрокоманда** и затем выберите **Переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="045d8-113">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="045d8-114">Нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="045d8-114">Click OK.</span></span>
    
    <span data-ttu-id="045d8-115">![Диалоговое окно "перемещение пользователей" и "целевой пул регистратора"](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Диалоговое окно "перемещение пользователей" и "целевой пул регистратора"")</span><span class="sxs-lookup"><span data-stu-id="045d8-115">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

7.  <span data-ttu-id="045d8-116">Убедитесь, что столбец **пул регистратора** для пользователей теперь содержит пул Lync Server 2013, указывающий, что пользователи успешно перемещены.</span><span class="sxs-lookup"><span data-stu-id="045d8-116">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="045d8-117">Перемещение нескольких пользователей с помощью командной консоли Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="045d8-117">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="045d8-118">Откройте консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="045d8-118">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="045d8-119">В командной строке введите следующую команду и замените **Пользователь1** и **Пользователь2** на конкретные имена пользователей, которые требуется переместить и заменить \*\* \_ полным доменным именем пула\*\* на имя целевого пула.</span><span class="sxs-lookup"><span data-stu-id="045d8-119">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="045d8-120">В этом примере мы переместим пользователей Hao Chen и Katie Jordan.</span><span class="sxs-lookup"><span data-stu-id="045d8-120">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="045d8-121">![Пример командлета PowerShell Get — CsUser](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Пример командлета PowerShell Get — CsUser")</span><span class="sxs-lookup"><span data-stu-id="045d8-121">![Example of PowerShell Get-CsUser cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Example of PowerShell Get-CsUser cmdlet")</span></span>  

3.  <span data-ttu-id="045d8-122">В командной строке введите следующую команду</span><span class="sxs-lookup"><span data-stu-id="045d8-122">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="045d8-123">Теперь удостоверение **пула регистратора** должно указывать на пул, указанный в предыдущем шаге в качестве \*\* \_ полного доменного имени пула\*\* .</span><span class="sxs-lookup"><span data-stu-id="045d8-123">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="045d8-124">Присутствие этого удостоверения подтверждает, что пользователь успешно перемещен.</span><span class="sxs-lookup"><span data-stu-id="045d8-124">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="045d8-125">Повторите этот шаг, чтобы убедиться, что пользователь **User2** перемещен.</span><span class="sxs-lookup"><span data-stu-id="045d8-125">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="045d8-126">![Выходные данные командлета PowerShell Get – Усусер — Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Выходные данные командлета PowerShell Get – Усусер — Identity")</span><span class="sxs-lookup"><span data-stu-id="045d8-126">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="045d8-127">Перемещение всех пользователей одновременно с помощью командной консоли Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="045d8-127">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="045d8-128">В этом примере все пользователи возвращены в пул Lync Server 2010 (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="045d8-128">In this example, all users have been returned to the Lync Server 2010 pool (pool01.contoso.net).</span></span> <span data-ttu-id="045d8-129">С помощью командной консоли Lync Server 2013 мы одновременно перейдем всех пользователей в пул Lync Server 2013 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="045d8-129">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="045d8-130">Откройте **консоль управления Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="045d8-130">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="045d8-131">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="045d8-131">At the command line, type the following:</span></span>
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="045d8-132">![Командлет PowerShell и результаты в командной консоли](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "Командлет PowerShell и результаты в командной консоли")</span><span class="sxs-lookup"><span data-stu-id="045d8-132">![PowerShell cmdlet and results in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet and results in Management Shell")</span></span>  

3.  <span data-ttu-id="045d8-133">Затем выполните командлет **Get-CsUser** для одного из пробных пользователей.</span><span class="sxs-lookup"><span data-stu-id="045d8-133">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="045d8-134">Удостоверение **пула регистратора** для каждого пользователя теперь указывает на пул, указанный \_ в предыдущем шаге как "полное доменное имя пула".</span><span class="sxs-lookup"><span data-stu-id="045d8-134">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="045d8-135">Наличие этого идентификатора подтверждает успешное перемещение пользователя.</span><span class="sxs-lookup"><span data-stu-id="045d8-135">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="045d8-136">Кроме того, можно просмотреть список пользователей в панели управления Lync Server 2013 и проверить, что значение пула регистратора теперь указывает на пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="045d8-136">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="045d8-137">![Список пользователей в панели управления Lync Server 2013](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Список пользователей в панели управления Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="045d8-137">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

