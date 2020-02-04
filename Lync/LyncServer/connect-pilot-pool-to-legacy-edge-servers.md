---
title: Подключение пилотного пула к старым пограничным серверам
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 447a0ead887b8283aa2701963a0107ef318bb312
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="db166-102">Подключение пилотного пула к старым пограничным серверам</span><span class="sxs-lookup"><span data-stu-id="db166-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db166-103">_**Тема последнего изменения:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="db166-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="db166-104">После развертывания Lync Server 2013 необходимо настроить маршрут Федерации для вашего сайта.</span><span class="sxs-lookup"><span data-stu-id="db166-104">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="db166-105">Чтобы использовать федеративный маршрут, который используется в Lync Server 2010, Lync Server 2013 необходимо настроить для использования этого маршрута.</span><span class="sxs-lookup"><span data-stu-id="db166-105">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="db166-106">Чтобы разрешить сайту Lync Server 2013 использовать режиссер и Edge-сервер для развертывания Lync Server 2010, используйте построитель топологии для связи с устаревшим пулом Edge.</span><span class="sxs-lookup"><span data-stu-id="db166-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="db166-107">Связывание устаревшего пула Edge с помощью построителя топологии</span><span class="sxs-lookup"><span data-stu-id="db166-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="db166-108">Открытие **построителя топологии**.</span><span class="sxs-lookup"><span data-stu-id="db166-108">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="db166-109">Выберите сайт, который находится непосредственно под узлом **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="db166-109">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="db166-110">В меню **действия** выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="db166-110">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="db166-111">На левой панели выберите **маршрут Федерации**.</span><span class="sxs-lookup"><span data-stu-id="db166-111">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="db166-112">В разделе **назначение маршрута Федерации сайтов**выберите **включить федерацию SIP**, а затем — режиссер сервера Lync Server 2010 или сервер Lync Server 2010 Edge Server, если в списке нет режиссера.</span><span class="sxs-lookup"><span data-stu-id="db166-112">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="db166-113">![Страница "изменение свойств", "маршрут Федерации"](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Страница "изменение свойств", "маршрут Федерации"")</span><span class="sxs-lookup"><span data-stu-id="db166-113">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="db166-114">Нажмите кнопку **ОК** , чтобы закрыть страницу **изменение свойств** .</span><span class="sxs-lookup"><span data-stu-id="db166-114">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="db166-115">В построителе топологии на узле Lync Server 2013 перейдите к пулам **стандартных серверных** **пулов или интерфейсов Enterprise Edition**, щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="db166-115">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="db166-116">В разделе **связи**установите флажок **связать пул граничного пула (для компонентов мультимедиа)**.</span><span class="sxs-lookup"><span data-stu-id="db166-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="db166-117">Выберите в списке старый сервер пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="db166-117">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="db166-118">![Диалоговое окно "изменение свойств" с выделенным старым краем](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Диалоговое окно "изменение свойств" с выделенным старым краем")</span><span class="sxs-lookup"><span data-stu-id="db166-118">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="db166-119">Нажмите кнопку **ОК** , чтобы закрыть страницу **изменение свойств** .</span><span class="sxs-lookup"><span data-stu-id="db166-119">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="db166-120">В **построителе топологии**выберите самый верхний узел, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="db166-120">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="db166-121">В меню **действие** выберите пункт **топология публикации**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="db166-121">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="db166-122">После завершения работы **мастера публикации** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="db166-122">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

