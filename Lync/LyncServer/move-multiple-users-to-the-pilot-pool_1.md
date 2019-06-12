---
title: Перемещение нескольких пользователей в пилотный пул
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ffc3e01df30f4a8e1b9c9b9aeca2b2013003980
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="917f0-102">Перемещение нескольких пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="917f0-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="917f0-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="917f0-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="917f0-104">Вы можете переместить нескольких пользователей из пула Office Communications Server 2007 R2 на сервер Lync Server 2013 для пилотного пула с помощью панели управления Lync Server 2013 или консоли управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="917f0-104">You can move multiple users from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="917f0-105">Перемещение нескольких пользователей с помощью панели управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="917f0-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="917f0-106">Откройте **Панель управления Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="917f0-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="917f0-107">На вкладке **Поиск пользователя** нажмите кнопку **Поиск** .</span><span class="sxs-lookup"><span data-stu-id="917f0-107">From the **User Search** tab, click the **Search** button.</span></span>

3.  <span data-ttu-id="917f0-108">Затем нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="917f0-108">Next, click **Add Filter**.</span></span>

4.  <span data-ttu-id="917f0-109">Создайте фильтр, в котором **пользователь Office Communications Server** равен **true**.</span><span class="sxs-lookup"><span data-stu-id="917f0-109">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

5.  <span data-ttu-id="917f0-110">Нажмите кнопку **найти** , чтобы найти устаревших пользователей Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="917f0-110">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>

6.  <span data-ttu-id="917f0-111">Выберите двух пользователей, которых вы хотите переместить в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="917f0-111">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="917f0-112">В этом примере мы перейдем пользователей Чена Маслов и предложения Хансен.</span><span class="sxs-lookup"><span data-stu-id="917f0-112">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="917f0-113">![Список пользователей, отображаемый при поиске пользователей OCS] (images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Список пользователей, отображаемый при поиске пользователей OCS")</span><span class="sxs-lookup"><span data-stu-id="917f0-113">![User list displayed from searching for OCS users](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "User list displayed from searching for OCS users")</span></span>  

7.  <span data-ttu-id="917f0-114">В меню **действия** выберите пункт **переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="917f0-114">From the **Action** menu, select **Move selected users to pool**.</span></span>

8.  <span data-ttu-id="917f0-115">В раскрывающемся списке выберите пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="917f0-115">From the drop-down list, select the Lync Server 2013 pool.</span></span>

9.  <span data-ttu-id="917f0-116">Нажмите **Макрокоманда** и затем **Переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="917f0-116">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="917f0-117">Нажмите OK.</span><span class="sxs-lookup"><span data-stu-id="917f0-117">Click OK.</span></span>
    
    <span data-ttu-id="917f0-118">![Перемещение пользователей, диалоговое окно «пул конечных регистраторов] » (images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Перемещение пользователей, диалоговое окно «пул конечных регистраторов") »</span><span class="sxs-lookup"><span data-stu-id="917f0-118">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

10. <span data-ttu-id="917f0-119">Убедитесь в том, что столбец **пула регистратора** для пользователей теперь содержит пул Lync Server 2013, указывающий на то, что пользователи успешно перемещены.</span><span class="sxs-lookup"><span data-stu-id="917f0-119">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="917f0-120">Перемещение нескольких пользователей с помощью управляющей оболочки Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="917f0-120">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="917f0-121">Откройте консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="917f0-121">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="917f0-122">В командной строке введите следующую команду и замените **Пользователь1** и **Пользователь2** именами пользователей, которым вы хотите переместить и заменить **FQDN пула\_** именем конечного пула.</span><span class="sxs-lookup"><span data-stu-id="917f0-122">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="917f0-123">В этом примере мы перейдем пользователей Хао Чен и Katie Иордания.</span><span class="sxs-lookup"><span data-stu-id="917f0-123">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="917f0-124">![Пример командлета для перемещения устаревшего пользователя] (images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Пример командлета для перемещения устаревшего пользователя")</span><span class="sxs-lookup"><span data-stu-id="917f0-124">![Example cmdlet to move a legacy user](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Example cmdlet to move a legacy user")</span></span>  

3.  <span data-ttu-id="917f0-125">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="917f0-125">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="917f0-126">Удостоверение **пула регистратора** теперь должно указывать на пул, указанный в предыдущем шаге, в качестве **полного доменного имени пула\_** .</span><span class="sxs-lookup"><span data-stu-id="917f0-126">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="917f0-127">Присутствие этого удостоверения подтверждает, что пользователь успешно переместился.</span><span class="sxs-lookup"><span data-stu-id="917f0-127">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="917f0-128">Повторите действия, чтобы проверить, был ли перемещен **Пользователь2** .</span><span class="sxs-lookup"><span data-stu-id="917f0-128">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="917f0-129">![Вывод командлета PowerShell Get-усусер-Identity] (images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Вывод командлета PowerShell Get-усусер-Identity")</span><span class="sxs-lookup"><span data-stu-id="917f0-129">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="917f0-130">Перемещение всех пользователей одновременно с помощью управляющей оболочки Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="917f0-130">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="917f0-131">В этом примере все пользователи возвращены в пул Office Communications Server 2007 R2 (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="917f0-131">In this example, all users have been returned to the Office Communications Server 2007 R2 pool (pool01.contoso.net).</span></span> <span data-ttu-id="917f0-132">С помощью командной консоли Lync Server 2013 мы одновременно перейдем всех пользователей к группе Lync Server 2013 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="917f0-132">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="917f0-133">Откройте **консоль управления Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="917f0-133">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="917f0-134">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="917f0-134">At the command line, type the following:</span></span>
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="917f0-135">![Пример командлета для перемещения всех устаревших пользователей в пуле] (images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Пример командлета для перемещения всех устаревших пользователей в пуле")</span><span class="sxs-lookup"><span data-stu-id="917f0-135">![Example cmdlet to move all legacy users in a pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Example cmdlet to move all legacy users in a pool")</span></span>  

3.  <span data-ttu-id="917f0-136">Затем выполните **Get-CsUser** для одного из пилотных пользователей.</span><span class="sxs-lookup"><span data-stu-id="917f0-136">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="917f0-137">Удостоверение **пула регистраторов** для каждого пользователя теперь указывает на пул, указанный в предыдущем шаге\_в качестве полного доменного имени пула.</span><span class="sxs-lookup"><span data-stu-id="917f0-137">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="917f0-138">Присутствие этого удостоверения подтверждает, что пользователь успешно переместился.</span><span class="sxs-lookup"><span data-stu-id="917f0-138">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="917f0-139">Кроме того, вы можете просмотреть список пользователей на панели управления Lync Server 2013 и убедиться, что значение пула регистратора теперь указывает на пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="917f0-139">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="917f0-140">![Список пользователей панели управления Lync Server 2013] (images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Список пользователей панели управления Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="917f0-140">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

