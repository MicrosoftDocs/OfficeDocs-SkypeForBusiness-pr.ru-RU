---
title: 'Lync Server 2013: создание или изменение маршрутов областей сети'
description: 'Lync Server 2013: создание или изменение маршрутов областей сети.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89106c905419778776ea16341f247027d49f1195
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544095"
---
# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="33348-103">Создание или изменение маршрутов областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33348-103">Creating or modifying network region routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33348-104">_**Последнее изменение темы:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="33348-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="33348-105">Каждому региону в конфигурации контроля допуска звонков (CAC) необходимо предоставить возможность доступа к каждой другой области.</span><span class="sxs-lookup"><span data-stu-id="33348-105">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="33348-106">Связи между регионами накладывают определенные ограничения на пропускную способность, доступную подключениям между областями, и также представляют собой физические соединения; маршруты же определяют путь, который должны пройти подключения от одной области до другой.</span><span class="sxs-lookup"><span data-stu-id="33348-106">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="33348-107">Для настройки маршрутов областей сети можно использовать панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="33348-107">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="33348-108">С помощью панели управления Lync Server вы можете создать, изменить или удалить маршрут области сети.</span><span class="sxs-lookup"><span data-stu-id="33348-108">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="33348-109">Используйте этот раздел для создания или изменения маршрута маршрут между областями сети.</span><span class="sxs-lookup"><span data-stu-id="33348-109">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="33348-110">Сведения об удалении существующих маршрутов областей сети приведены [в статье Удаление существующих маршрутов областей сети в Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="33348-110">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="33348-111">Создание маршрута к регионами сети</span><span class="sxs-lookup"><span data-stu-id="33348-111">To create a network region route</span></span>

1.  <span data-ttu-id="33348-112">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="33348-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33348-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="33348-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="33348-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="33348-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="33348-115">На левой панели навигации щелкните **Конфигурация сети**, а затем щелкните **Маршрут к регионами**.</span><span class="sxs-lookup"><span data-stu-id="33348-115">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="33348-116">На странице **Маршрут к региону** щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="33348-116">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="33348-117">В области **Новый маршрут к региону** введите значение в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="33348-117">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33348-118">Это значение должно быть уникальным в пределах развертывания Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33348-118">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="33348-119">В раскрывающемся списке **область сети \# 1** выберите один из двух областей, которые должны быть соединены этим маршрутом.</span><span class="sxs-lookup"><span data-stu-id="33348-119">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="33348-120">В раскрывающемся списке **область сети \# 2** выберите другой регион для этого маршрута.</span><span class="sxs-lookup"><span data-stu-id="33348-120">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="33348-121">Этот регион должен отличаться от региона, выбранного для области сети \# 1.</span><span class="sxs-lookup"><span data-stu-id="33348-121">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="33348-p104">Используйте поле со списком **Связи регионов сети**, чтобы добавить в маршрут связи с регионами. Щелкните кнопку **Добавить** для отображения страницы **Связь с регионом**. Щелкните связь с регионом, чтобы добавить ее в маршрут, и щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="33348-p104">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33348-125">Нажимайте кнопку <STRONG>Добавить</STRONG>, чтобы добавить дополнительные связи, или выберите связь и щелкните <STRONG>Удалить</STRONG> для удаления соединения.</span><span class="sxs-lookup"><span data-stu-id="33348-125">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="33348-126">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="33348-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="33348-127">Изменение маршрута к региону сети</span><span class="sxs-lookup"><span data-stu-id="33348-127">To modify a network region route</span></span>

1.  <span data-ttu-id="33348-128">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="33348-128">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33348-129">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="33348-129">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="33348-130">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="33348-130">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="33348-131">На левой панели навигации щелкните **Конфигурация сети**, а затем щелкните **Маршрут к региону**.</span><span class="sxs-lookup"><span data-stu-id="33348-131">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="33348-132">На странице **Маршрут к региону** щелкните маршрут к региону, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="33348-132">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="33348-133">В меню **Правка** щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="33348-133">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="33348-134">В области **Изменить маршрут к региону** можно изменить регионы, соединенные этим маршрутом, и связи с регионами, назначенные маршруту.</span><span class="sxs-lookup"><span data-stu-id="33348-134">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="33348-135">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="33348-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33348-136">См. также</span><span class="sxs-lookup"><span data-stu-id="33348-136">See Also</span></span>


[<span data-ttu-id="33348-137">Удаление существующих маршрутов областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33348-137">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

