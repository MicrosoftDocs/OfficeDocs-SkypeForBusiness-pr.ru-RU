---
title: Перемещение нескольких пользователей в пилотный пул
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8e347658d73405d7125eb439daff7eeb84e6ea7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="53fb5-102">Перемещение нескольких пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="53fb5-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53fb5-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="53fb5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="53fb5-104">Вы можете переместить нескольких пользователей из пула Lync Server 2010 на сервер Lync Server 2013 для пилотного пула с помощью панели управления Lync Server 2013 или консоли управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53fb5-104">You can move multiple users from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="53fb5-105">Перемещение нескольких пользователей с помощью панели управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53fb5-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="53fb5-106">Откройте **Панель управления Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="53fb5-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="53fb5-107">Нажмите **Пользователи**, затем "Поиск" и **Найти**.</span><span class="sxs-lookup"><span data-stu-id="53fb5-107">Click **Users**, click Search, and then click **Find**.</span></span>

3.  <span data-ttu-id="53fb5-108">Выберите двух пользователей, которых вы хотите переместить в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53fb5-108">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="53fb5-109">В этом примере мы перейдем пользователей Чена Маслов и предложения Хансен.</span><span class="sxs-lookup"><span data-stu-id="53fb5-109">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="53fb5-110">![Перемещение пользователей в определенную группу регистров](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Перемещение пользователей в определенную группу регистров")</span><span class="sxs-lookup"><span data-stu-id="53fb5-110">![Move users to specific register pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Move users to specific register pool")</span></span>  

4.  <span data-ttu-id="53fb5-111">В меню **действия** выберите пункт **переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="53fb5-111">From the **Action** menu, select **Move selected users to pool**.</span></span>

5.  <span data-ttu-id="53fb5-112">В раскрывающемся списке выберите пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53fb5-112">From the drop-down list, select the Lync Server 2013 pool.</span></span>

6.  <span data-ttu-id="53fb5-113">Нажмите **Макрокоманда** и затем **Переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="53fb5-113">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="53fb5-114">Нажмите OK.</span><span class="sxs-lookup"><span data-stu-id="53fb5-114">Click OK.</span></span>
    
    <span data-ttu-id="53fb5-115">![Перемещение пользователей, диалоговое окно «пул конечных регистраторов»](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Перемещение пользователей, диалоговое окно «пул конечных регистраторов»")</span><span class="sxs-lookup"><span data-stu-id="53fb5-115">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

7.  <span data-ttu-id="53fb5-116">Убедитесь в том, что столбец **пула регистратора** для пользователей теперь содержит пул Lync Server 2013, указывающий на то, что пользователи успешно перемещены.</span><span class="sxs-lookup"><span data-stu-id="53fb5-116">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="53fb5-117">Перемещение нескольких пользователей с помощью управляющей оболочки Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53fb5-117">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="53fb5-118">Откройте консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53fb5-118">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="53fb5-119">В командной строке введите следующую команду и замените **Пользователь1** и **Пользователь2** именами пользователей, которым вы хотите переместить и заменить **FQDN пула\_** именем конечного пула.</span><span class="sxs-lookup"><span data-stu-id="53fb5-119">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="53fb5-120">В этом примере мы перейдем пользователей Хао Чен и Katie Иордания.</span><span class="sxs-lookup"><span data-stu-id="53fb5-120">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="53fb5-121">![Пример командлета Get-CsUser PowerShell](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Пример командлета Get-CsUser PowerShell")</span><span class="sxs-lookup"><span data-stu-id="53fb5-121">![Example of PowerShell Get-CsUser cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Example of PowerShell Get-CsUser cmdlet")</span></span>  

3.  <span data-ttu-id="53fb5-122">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="53fb5-122">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="53fb5-123">Удостоверение **пула регистратора** теперь должно указывать на пул, указанный в предыдущем шаге, в качестве **\_полного доменного имени пула** .</span><span class="sxs-lookup"><span data-stu-id="53fb5-123">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="53fb5-124">Присутствие этого удостоверения подтверждает, что пользователь успешно переместился.</span><span class="sxs-lookup"><span data-stu-id="53fb5-124">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="53fb5-125">Повторите действия, чтобы проверить, был ли перемещен **Пользователь2** .</span><span class="sxs-lookup"><span data-stu-id="53fb5-125">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="53fb5-126">![Вывод командлета PowerShell Get-Усусер-Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Вывод командлета PowerShell Get-Усусер-Identity")</span><span class="sxs-lookup"><span data-stu-id="53fb5-126">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="53fb5-127">Перемещение всех пользователей одновременно с помощью управляющей оболочки Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53fb5-127">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="53fb5-128">В этом примере все пользователи возвращены в пул Lync Server 2010 (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="53fb5-128">In this example, all users have been returned to the Lync Server 2010 pool (pool01.contoso.net).</span></span> <span data-ttu-id="53fb5-129">С помощью командной консоли Lync Server 2013 мы одновременно перейдем всех пользователей к группе Lync Server 2013 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="53fb5-129">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="53fb5-130">Откройте **консоль управления Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="53fb5-130">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="53fb5-131">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="53fb5-131">At the command line, type the following:</span></span>
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="53fb5-132">![Командлет PowerShell и результаты в командной консоли](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "Командлет PowerShell и результаты в командной консоли")</span><span class="sxs-lookup"><span data-stu-id="53fb5-132">![PowerShell cmdlet and results in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet and results in Management Shell")</span></span>  

3.  <span data-ttu-id="53fb5-133">Затем выполните **Get-CsUser** для одного из пилотных пользователей.</span><span class="sxs-lookup"><span data-stu-id="53fb5-133">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="53fb5-134">Удостоверение **пула регистраторов** для каждого пользователя теперь указывает на пул, указанный в предыдущем шаге\_в качестве полного доменного имени пула.</span><span class="sxs-lookup"><span data-stu-id="53fb5-134">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="53fb5-135">Присутствие этого удостоверения подтверждает, что пользователь успешно переместился.</span><span class="sxs-lookup"><span data-stu-id="53fb5-135">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="53fb5-136">Кроме того, вы можете просмотреть список пользователей на панели управления Lync Server 2013 и убедиться, что значение пула регистратора теперь указывает на пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53fb5-136">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="53fb5-137">![Список пользователей панели управления Lync Server 2013](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Список пользователей панели управления Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="53fb5-137">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

