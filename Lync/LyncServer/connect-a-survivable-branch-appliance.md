---
title: Подключение Survivable Branch Appliance
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0fcba962129353ddeb5e5f4c77520cf6d127733
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="31f02-102">Подключение Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="31f02-102">Connect a Survivable Branch Appliance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31f02-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="31f02-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="31f02-104">Каждое устройство для обеспечения связи в филиалах (SBA) связано с пулом переднего плана, который выступает в качестве регистратора резервных копий для SBA.</span><span class="sxs-lookup"><span data-stu-id="31f02-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="31f02-105">Когда интерфейсный пул переносится на Lync Server 2013, SBA должен быть связан с интерфейсным пулом Lync Server 2010 при его обновлении, после переноса пула в Lync Server 2013, SBA может быть повторно связан с обновленным интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="31f02-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="31f02-106">Это включает удаление SBA из устаревшей топологии Lync Server 2010 в построителе топологий и добавление SBA в топологию Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="31f02-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="31f02-107">Пользователи, размещенные на старом сервере Lync 2010 SBA, необходимо сначала переместить в другой интерфейсный пул, прежде чем удалять SBA из топологии.</span><span class="sxs-lookup"><span data-stu-id="31f02-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="31f02-108">После добавления SBA в топологию Lync Server 2013 эти пользователи затем могут быть возвращены в SBA.</span><span class="sxs-lookup"><span data-stu-id="31f02-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="31f02-109">Эти действия приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="31f02-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="31f02-110">Переместите пользователей филиалов, размещенных на устаревшем SBA Lync Server 2010, в другой интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="31f02-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="31f02-111">Удалите SBA из устаревшей топологии Lync Server 2010, чтобы отключить существующий интерфейсный пул в качестве регистратора резервных копий.</span><span class="sxs-lookup"><span data-stu-id="31f02-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="31f02-112">Добавьте SBA в топологию Lync Server 2013 и настройте этот новый интерфейсный пул в качестве регистратора резервных копий.</span><span class="sxs-lookup"><span data-stu-id="31f02-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="31f02-113">Переместите пользователей филиала на новый Lync Server 2013 SBA.</span><span class="sxs-lookup"><span data-stu-id="31f02-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="31f02-114">**Добавление сайта филиала устройства для обеспечения связи в филиалах Lync Server 2010 в топологию**</span><span class="sxs-lookup"><span data-stu-id="31f02-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="31f02-115">Откройте **построитель топологий**.</span><span class="sxs-lookup"><span data-stu-id="31f02-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="31f02-116">В левой панели щелкните правой кнопкой мыши элемент **Сайты филиалов**, а затем выберите пункт **Создать сайт филиала**.</span><span class="sxs-lookup"><span data-stu-id="31f02-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="31f02-117">В диалоговом окне **Определение нового сайта филиала для сайта** щелкните элемент **Имя**, а затем введите имя сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="31f02-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="31f02-118">(Необязательно) Щелкните элемент **Описание**, а затем введите содержательное описание для сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="31f02-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="31f02-119">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="31f02-119">Click **Next**.</span></span>

6.  <span data-ttu-id="31f02-120">(Необязательно) В следующем диалоговом окне **Определение нового сайта филиала для сайта** выполните любое из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="31f02-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="31f02-121">Щелкните элемент **Город**, а затем введите название города, в котором расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="31f02-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="31f02-122">Щелкните элемент **Регион**, а затем введите название региона или области, где расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="31f02-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="31f02-123">Щелкните элемент **Код страны**, а затем введите двузначный вызывной код для страны/региона, где расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="31f02-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="31f02-124">Нажмите кнопку **Далее**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="31f02-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="31f02-p102">Если вы используете на этом сайте устройство или сервер для обеспечения связи в филиалах Lync 2010, обязательно снимите флажок **Открыть мастер создания устройства для обеспечения связи в филиалах после завершения работы этого мастера**. Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="31f02-p102">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option. Click **Finish**.</span></span>

8.  <span data-ttu-id="31f02-127">Сопоставление устаревшего сервера Lync Server 2010 SBA с интерфейсным пулом Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="31f02-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="31f02-128">Разверните созданный сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="31f02-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="31f02-129">Щелкните правой кнопкой мыши элемент **Lync Server 2010** и выберите пункт **Создать**.</span><span class="sxs-lookup"><span data-stu-id="31f02-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="31f02-130">Щелкните элемент **Устройство для обеспечения связи в филиалах…**</span><span class="sxs-lookup"><span data-stu-id="31f02-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="31f02-131">Следуйте указаниям открывшегося мастера.</span><span class="sxs-lookup"><span data-stu-id="31f02-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="31f02-132">Сведения об элементах мастера можно найти [в разделе Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="31f02-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31f02-133">Устройство для обеспечения связи в филиалах Lync Server 2010 может быть связано только с хранилищем мониторинга Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="31f02-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="31f02-134">Если вы не используете на этом сайте устройство или сервер для обеспечения связи в филиалах, снимите флажок **Открыть мастер создания устройства для обеспечения связи в филиалах после завершения работы этого мастера**. а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="31f02-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="31f02-135">Повторите перечисленные выше действия для каждого сайта филиала, который вы хотите добавить в топологию.</span><span class="sxs-lookup"><span data-stu-id="31f02-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

