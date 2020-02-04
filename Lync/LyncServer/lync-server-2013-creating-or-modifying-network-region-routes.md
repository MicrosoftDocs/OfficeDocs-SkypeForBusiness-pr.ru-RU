---
title: 'Lync Server 2013: создание и изменение маршрутов сетевого региона'
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
ms.openlocfilehash: d877de116cc2cf3e0c3354bb6e53d69c211cb482
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="0a3cf-102">Создание и изменение маршрутов сетевого региона в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a3cf-102">Creating or modifying network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a3cf-103">_**Тема последнего изменения:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="0a3cf-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="0a3cf-104">Каждый регион в конфигурации управления допуском звонков (CAC) должен иметь какой-либо способ получить доступ ко всем остальным регионам.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="0a3cf-105">Несмотря на то, что ссылки на области устанавливают ограничения пропускной способности для подключений между регионами и представляют собой физические ссылки, маршрут определяет связанный путь, который будет проходить соединение между двумя областями.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="0a3cf-106">Вы можете настроить маршруты к сетевым регионам с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="0a3cf-107">С помощью панели управления Lync Server вы можете создавать, изменять и удалять маршруты сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="0a3cf-108">Этот раздел используется для создания и изменения маршрута сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-108">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="0a3cf-109">Дополнительные сведения об удалении существующих маршрутов сетевого региона можно найти [в разделе Удаление маршрутов сетевого региона в Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="0a3cf-109">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="0a3cf-110">Чтобы создать маршрут к сетевому региону</span><span class="sxs-lookup"><span data-stu-id="0a3cf-110">To create a network region route</span></span>

1.  <span data-ttu-id="0a3cf-111">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0a3cf-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0a3cf-113">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0a3cf-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0a3cf-114">На панели навигации слева выберите пункт **Настройка сети** , а затем — пункт **путь к региону**.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="0a3cf-115">На странице " **регион** " нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-115">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="0a3cf-116">В разделе **Новый маршрут**введите значение в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="0a3cf-116">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0a3cf-117">Это значение должно быть уникальным в рамках развертывания Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-117">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="0a3cf-118">В раскрывающемся списке **сетевой регион \#1** выберите один из двух областей, которые должны быть соединены этим маршрутом.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-118">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="0a3cf-119">В раскрывающемся списке **сетевой регион \#2** выберите другой регион для этого маршрута.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-119">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="0a3cf-120">Этот регион должен отличаться от региона, выбранного для сетевого региона \#1.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-120">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="0a3cf-121">С помощью списка " **сетевой регион** " можно добавить в маршрут ссылки на регион.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-121">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="0a3cf-122">Нажмите кнопку " **Добавить** ", чтобы открыть страницу **ссылки "регион** ".</span><span class="sxs-lookup"><span data-stu-id="0a3cf-122">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="0a3cf-123">Щелкните ссылку на регион, чтобы добавить в этот маршрут, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-123">Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0a3cf-124">Нажмите кнопку <STRONG>Добавить</STRONG> , чтобы добавить ссылки, или выберите ссылку, а затем нажмите кнопку <STRONG>Удалить</STRONG> , чтобы удалить ссылку.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-124">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="0a3cf-125">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="0a3cf-126">Изменение маршрута сетевого региона</span><span class="sxs-lookup"><span data-stu-id="0a3cf-126">To modify a network region route</span></span>

1.  <span data-ttu-id="0a3cf-127">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0a3cf-128">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0a3cf-129">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0a3cf-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0a3cf-130">На панели навигации слева выберите пункт **Настройка сети** , а затем — пункт **путь к региону**.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-130">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="0a3cf-131">На странице " **регион** " щелкните маршрут региона, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-131">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="0a3cf-132">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="0a3cf-133">В окне " **изменить маршрут области**" можно изменить регионы, Соединенные этим маршрутом, и ссылки на области, связанные с этим маршрутом.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-133">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="0a3cf-134">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="0a3cf-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0a3cf-135">См. также</span><span class="sxs-lookup"><span data-stu-id="0a3cf-135">See Also</span></span>


[<span data-ttu-id="0a3cf-136">Удаление существующих маршрутов сетевого региона в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a3cf-136">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

