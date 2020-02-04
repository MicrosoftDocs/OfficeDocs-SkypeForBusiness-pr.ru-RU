---
title: 'Lync Server 2013: удаление существующих маршрутов сетевого региона'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9f9ba7c20aff0bba3101edc9b04f3704314cfc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="0e44c-102">Удаление существующих маршрутов сетевого региона в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e44c-102">Deleting existing network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e44c-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0e44c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0e44c-104">Каждый регион в конфигурации управления допуском звонков (CAC) должен иметь какой-либо способ получить доступ ко всем остальным регионам.</span><span class="sxs-lookup"><span data-stu-id="0e44c-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="0e44c-105">Несмотря на то, что ссылки на области устанавливают ограничения пропускной способности для подключений между регионами и представляют собой физические ссылки, маршрут определяет связанный путь, который будет проходить соединение между двумя областями.</span><span class="sxs-lookup"><span data-stu-id="0e44c-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="0e44c-106">Вы можете настроить маршруты к сетевым регионам с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0e44c-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="0e44c-107">С помощью панели управления Lync Server вы можете создавать, изменять и удалять маршруты сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="0e44c-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="0e44c-108">Этот раздел используется для удаления существующих маршрутов сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="0e44c-108">Use this topic to delete existing network region routes.</span></span> <span data-ttu-id="0e44c-109">Дополнительные сведения о создании и изменении маршрутов сетевого региона можно найти [в разделе Создание и изменение маршрутов сетевого региона в Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="0e44c-109">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-delete-a-network-region-route"></a><span data-ttu-id="0e44c-110">Удаление маршрута сетевого региона</span><span class="sxs-lookup"><span data-stu-id="0e44c-110">To delete a network region route</span></span>

1.  <span data-ttu-id="0e44c-111">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0e44c-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0e44c-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0e44c-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0e44c-113">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0e44c-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0e44c-114">На панели навигации слева выберите пункт **Настройка сети** , а затем — пункт **путь к региону**.</span><span class="sxs-lookup"><span data-stu-id="0e44c-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="0e44c-115">На странице " **регион** " щелкните маршрут региона, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="0e44c-115">On the **Region Route** page, click the region route that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0e44c-116">За один раз можно удалить сразу несколько маршрутов.</span><span class="sxs-lookup"><span data-stu-id="0e44c-116">You can delete more than one region route at a time.</span></span> <span data-ttu-id="0e44c-117">Для этого нажмите клавишу CTRL и, удерживая нажатой клавишу CTRL, выберите один из нескольких маршрутов областей.</span><span class="sxs-lookup"><span data-stu-id="0e44c-117">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="0e44c-118">Кроме того, чтобы выделить все маршруты областей, в меню <STRONG>Правка</STRONG> выберите команду <STRONG>выделить все</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="0e44c-118">Or, to select all region routes, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="0e44c-119">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="0e44c-119">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="0e44c-120">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0e44c-120">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0e44c-121">См. также</span><span class="sxs-lookup"><span data-stu-id="0e44c-121">See Also</span></span>


[<span data-ttu-id="0e44c-122">Создание и изменение маршрутов сетевого региона в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e44c-122">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  


<span data-ttu-id="0e44c-123">[Настройка маршрута области сети](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="0e44c-123">[Configure a Network Region Route](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))</span></span>  


[<span data-ttu-id="0e44c-124">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="0e44c-124">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[<span data-ttu-id="0e44c-125">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="0e44c-125">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[<span data-ttu-id="0e44c-126">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="0e44c-126">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[<span data-ttu-id="0e44c-127">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="0e44c-127">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

