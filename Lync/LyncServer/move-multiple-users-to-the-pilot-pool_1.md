---
title: Перемещение нескольких пользователей в пилотный пул
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffd0fbebffea5553cc461f71cf67843dae0a8ae6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500226"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="7a105-102">Перемещение нескольких пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="7a105-102">Move multiple users to the pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a105-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7a105-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7a105-104">Можно переместить несколько пользователей из пула Office Communications Server 2007 R2 в пилотный пул Lync Server 2013 с помощью панели управления Lync Server 2013 или консоли управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a105-104">You can move multiple users from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="7a105-105">Перемещение нескольких пользователей с помощью панели управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a105-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="7a105-106">Откройте **Панель управления Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7a105-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="7a105-107">На вкладке **Поиск пользователей** щелкните кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="7a105-107">From the **User Search** tab, click the **Search** button.</span></span>

3.  <span data-ttu-id="7a105-108">Затем щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="7a105-108">Next, click **Add Filter**.</span></span>

4.  <span data-ttu-id="7a105-109">Создайте фильтр, в котором для параметра **Пользователь Office Communications Server** установлено значение **True**.</span><span class="sxs-lookup"><span data-stu-id="7a105-109">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

5.  <span data-ttu-id="7a105-110">Нажмите кнопку **найти** , чтобы найти устаревших пользователей Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7a105-110">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>

6.  <span data-ttu-id="7a105-111">Выберите двух пользователей, которых нужно переместить в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a105-111">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="7a105-112">В этом примере мы переместим пользователей Chen Yang и Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="7a105-112">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="7a105-113">![Список пользователей, отображаемый при поиске пользователей OCS](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Список пользователей, отображаемый при поиске пользователей OCS")</span><span class="sxs-lookup"><span data-stu-id="7a105-113">![User list displayed from searching for OCS users](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "User list displayed from searching for OCS users")</span></span>  

7.  <span data-ttu-id="7a105-114">В меню **Макрокоманда** выберите **Переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="7a105-114">From the **Action** menu, select **Move selected users to pool**.</span></span>

8.  <span data-ttu-id="7a105-115">В раскрывающемся списке выберите пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a105-115">From the drop-down list, select the Lync Server 2013 pool.</span></span>

9.  <span data-ttu-id="7a105-116">Щелкните **Макрокоманда** и затем выберите **Переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="7a105-116">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="7a105-117">Нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="7a105-117">Click OK.</span></span>
    
    <span data-ttu-id="7a105-118">![Диалоговое окно "перемещение пользователей" и "целевой пул регистратора"](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Диалоговое окно "перемещение пользователей" и "целевой пул регистратора"")</span><span class="sxs-lookup"><span data-stu-id="7a105-118">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

10. <span data-ttu-id="7a105-119">Убедитесь, что столбец **пул регистратора** для пользователей теперь содержит пул Lync Server 2013, указывающий, что пользователи успешно перемещены.</span><span class="sxs-lookup"><span data-stu-id="7a105-119">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="7a105-120">Перемещение нескольких пользователей с помощью командной консоли Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a105-120">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="7a105-121">Откройте консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a105-121">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="7a105-122">В командной строке введите следующую команду и замените **Пользователь1** и **Пользователь2** на конкретные имена пользователей, которые требуется переместить и заменить \*\* \_ полным доменным именем пула\*\* на имя целевого пула.</span><span class="sxs-lookup"><span data-stu-id="7a105-122">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="7a105-123">В этом примере мы переместим пользователей Hao Chen и Katie Jordan.</span><span class="sxs-lookup"><span data-stu-id="7a105-123">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="7a105-124">![Пример командлета для перемещения устаревшего пользователя](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Пример командлета для перемещения устаревшего пользователя")</span><span class="sxs-lookup"><span data-stu-id="7a105-124">![Example cmdlet to move a legacy user](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Example cmdlet to move a legacy user")</span></span>  

3.  <span data-ttu-id="7a105-125">В командной строке введите следующую команду</span><span class="sxs-lookup"><span data-stu-id="7a105-125">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="7a105-126">Теперь удостоверение **пула регистратора** должно указывать на пул, указанный в предыдущем шаге в качестве \*\* \_ полного доменного имени пула\*\* .</span><span class="sxs-lookup"><span data-stu-id="7a105-126">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="7a105-127">Присутствие этого удостоверения подтверждает, что пользователь успешно перемещен.</span><span class="sxs-lookup"><span data-stu-id="7a105-127">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="7a105-128">Повторите этот шаг, чтобы убедиться, что пользователь **User2** перемещен.</span><span class="sxs-lookup"><span data-stu-id="7a105-128">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="7a105-129">![Выходные данные командлета PowerShell Get-UsUser — Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Выходные данные командлета PowerShell Get-UsUser — Identity")</span><span class="sxs-lookup"><span data-stu-id="7a105-129">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="7a105-130">Перемещение всех пользователей одновременно с помощью командной консоли Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a105-130">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="7a105-131">В этом примере все пользователи возвращены в пул Office Communications Server 2007 R2 (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="7a105-131">In this example, all users have been returned to the Office Communications Server 2007 R2 pool (pool01.contoso.net).</span></span> <span data-ttu-id="7a105-132">С помощью командной консоли Lync Server 2013 мы одновременно перейдем всех пользователей в пул Lync Server 2013 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="7a105-132">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="7a105-133">Откройте **консоль управления Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="7a105-133">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="7a105-134">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7a105-134">At the command line, type the following:</span></span>
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="7a105-135">![Пример командлета для перемещения всех пользователей прежних версий в пул](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Пример командлета для перемещения всех пользователей прежних версий в пул")</span><span class="sxs-lookup"><span data-stu-id="7a105-135">![Example cmdlet to move all legacy users in a pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Example cmdlet to move all legacy users in a pool")</span></span>  

3.  <span data-ttu-id="7a105-136">Затем выполните командлет **Get-CsUser** для одного из пробных пользователей.</span><span class="sxs-lookup"><span data-stu-id="7a105-136">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="7a105-137">Удостоверение **пула регистратора** для каждого пользователя теперь указывает на пул, указанный \_ в предыдущем шаге как "полное доменное имя пула".</span><span class="sxs-lookup"><span data-stu-id="7a105-137">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="7a105-138">Наличие этого идентификатора подтверждает успешное перемещение пользователя.</span><span class="sxs-lookup"><span data-stu-id="7a105-138">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="7a105-139">Кроме того, можно просмотреть список пользователей в панели управления Lync Server 2013 и проверить, что значение пула регистратора теперь указывает на пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a105-139">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="7a105-140">![Список пользователей в панели управления Lync Server 2013](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Список пользователей в панели управления Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="7a105-140">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

