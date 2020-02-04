---
title: Подключение Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ef6294deba25998c5ad16254e464b6f682fa660
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="072d9-102">Подключение Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="072d9-102">Connect a Survivable Branch Appliance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="072d9-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="072d9-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="072d9-104">Каждое работающее устройство филиала (СБА) связано с пулом переднего плана, который выступает в качестве регистратора резервных копий для СБА.</span><span class="sxs-lookup"><span data-stu-id="072d9-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="072d9-105">Когда пул переднего плана переносится на Lync Server 2013, СБА должен быть сопоставлен с пулом внешних интерфейсов Lync Server 2010 при обновлении пула, после того как пул будет перенесен на Lync Server 2013, СБА может быть повторно связан с обновленным пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="072d9-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="072d9-106">Это связано с тем, что удаление СБА из старой топологии сервера Lync 2010 в построителе топологии и добавление СБА в топологию Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="072d9-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="072d9-107">Пользователи, расположенные на устаревшем Lync Server 2010 СБА, должны сначала переместиться в другой пул переднего плана, прежде чем удалять СБА из топологии.</span><span class="sxs-lookup"><span data-stu-id="072d9-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="072d9-108">После того как СБА добавляется в топологию Lync Server 2013, эти пользователи затем могут быть возвращены в СБА.</span><span class="sxs-lookup"><span data-stu-id="072d9-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="072d9-109">Эти действия описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="072d9-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="072d9-110">Переместить пользователей филиалов, расположенные на устаревшем СБА Lync Server 2010, в другой пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="072d9-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="072d9-111">Удалите СБА из устаревшей топологии Lync Server 2010, чтобы отключить существующий пул переднего плана в качестве регистратора резервных копий.</span><span class="sxs-lookup"><span data-stu-id="072d9-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="072d9-112">Добавьте СБА в топологию Lync Server 2013 и настройте этот новый пул переднего плана в качестве регистратора резервных копий.</span><span class="sxs-lookup"><span data-stu-id="072d9-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="072d9-113">Переместите пользователей филиалов на новый сервер Lync Server 2013 СБА.</span><span class="sxs-lookup"><span data-stu-id="072d9-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="072d9-114">**Добавление сайта ответвления Lync Server 2010 СБА в топологию**</span><span class="sxs-lookup"><span data-stu-id="072d9-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="072d9-115">Открытие **построителя топологии**.</span><span class="sxs-lookup"><span data-stu-id="072d9-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="072d9-116">На левой панели щелкните правой кнопкой мыши **узлы филиалов**и выберите команду **создать сайт филиала**.</span><span class="sxs-lookup"><span data-stu-id="072d9-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="072d9-117">В диалоговом окне **Определение нового сайта ветви** щелкните **имя**и введите имя сайта ветви.</span><span class="sxs-lookup"><span data-stu-id="072d9-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="072d9-118">Необязательно Нажмите кнопку **Описание**и введите понятное описание сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="072d9-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="072d9-119">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="072d9-119">Click **Next**.</span></span>

6.  <span data-ttu-id="072d9-120">Необязательно В диалоговом окне **Определение нового сайта ветви** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="072d9-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="072d9-121">Щелкните **город**и введите имя города, в котором находится сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="072d9-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="072d9-122">Щелкните область или **регион**, а затем введите имя состояния или региона, в котором находится сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="072d9-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="072d9-123">Щелкните **код страны**, а затем введите четырехзначный код звонка для страны или региона, в котором расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="072d9-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="072d9-124">Нажмите кнопку **Далее**, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="072d9-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="072d9-125">Если вы используете устройство с бесперебойной подразделением Lync 2010 или сервер на этом сайте, не забудьте снять флажок **открывать новый бесперебойный мастер, когда мастер закроет этот** параметр.</span><span class="sxs-lookup"><span data-stu-id="072d9-125">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option.</span></span> <span data-ttu-id="072d9-126">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="072d9-126">Click **Finish**.</span></span>

8.  <span data-ttu-id="072d9-127">Чтобы сопоставить старый сервер Lync Server 2010 СБА с пулом внешних интерфейсов Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="072d9-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="072d9-128">Разверните созданный сайт ветви.</span><span class="sxs-lookup"><span data-stu-id="072d9-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="072d9-129">Щелкните правой кнопкой мыши на **Lync Server 2010** и выберите команду **создать**.</span><span class="sxs-lookup"><span data-stu-id="072d9-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="072d9-130">Щелкните **устройство для бесперебойной ветви..** .</span><span class="sxs-lookup"><span data-stu-id="072d9-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="072d9-131">Следуйте указаниям в открывшемся мастере.</span><span class="sxs-lookup"><span data-stu-id="072d9-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="072d9-132">Сведения об элементах мастера можно найти [в разделе Определение работающего устройства филиала или сервера в Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="072d9-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="072d9-133">Бесперебойно работающее устройство филиалов Lync Server 2010 можно связать только с хранилищем мониторинга Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="072d9-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="072d9-134">Если вы не используете бесперебойно работающее устройство или сервер филиала на этом сайте, снимите флажок **открыть новый бесперебойный мастер, когда мастер закроется** , и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="072d9-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="072d9-135">Повторите описанные выше действия для всех сайтов филиалов, которые нужно добавить в топологию.</span><span class="sxs-lookup"><span data-stu-id="072d9-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

