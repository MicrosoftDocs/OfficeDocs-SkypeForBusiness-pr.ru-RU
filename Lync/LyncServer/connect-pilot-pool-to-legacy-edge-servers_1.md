---
title: Подключение пилотного пула к старым пограничным серверам
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40d54a7432451901a32cb8e31d201ef732a731bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="b0e57-102">Подключение пилотного пула к старым пограничным серверам</span><span class="sxs-lookup"><span data-stu-id="b0e57-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0e57-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b0e57-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b0e57-104">После развертывания Lync Server 2013 маршрут Федерации для этого сайта не настроен.</span><span class="sxs-lookup"><span data-stu-id="b0e57-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="b0e57-105">Чтобы использовать федеративный маршрут, который используется в Office Communications Server 2007 R2, Lync Server 2013 необходимо настроить для использования этого маршрута.</span><span class="sxs-lookup"><span data-stu-id="b0e57-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="b0e57-106">Чтобы разрешить сайту Lync Server 2013 использовать режиссер и Edge-сервер Бакккомпатсите, воспользуйтесь построителем топологии для связи с устаревшим пулом Edge.</span><span class="sxs-lookup"><span data-stu-id="b0e57-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="b0e57-107">Связывание устаревшего пула Edge с помощью построителя топологии</span><span class="sxs-lookup"><span data-stu-id="b0e57-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="b0e57-108">Откройте топологию пилотного пула в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="b0e57-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="b0e57-109">Выберите сайт Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b0e57-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="b0e57-110">В меню **действия** выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="b0e57-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="b0e57-111">В разделе **назначение маршрута Федерации сайтов**выберите **включить федерацию SIP**, а затем выберите Office Communications Server 2007 R2 или пограничный сервер Office Communications Server 2007 R2, если в списке нет режиссера.</span><span class="sxs-lookup"><span data-stu-id="b0e57-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="b0e57-112">![Диалоговое окно "изменение свойств", страница "маршрут Федерации] " (images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Диалоговое окно \"изменение свойств\", страница \"маршрут Федерации") "</span><span class="sxs-lookup"><span data-stu-id="b0e57-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="b0e57-113">Нажмите кнопку **ОК** , чтобы закрыть страницу **изменение свойств** .</span><span class="sxs-lookup"><span data-stu-id="b0e57-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="b0e57-114">В построителе топологии на узле Lync Server 2013 перейдите к пулам **стандартных серверных** **пулов или интерфейсов Enterprise Edition**, щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="b0e57-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="b0e57-115">В разделе **связи**установите флажок **связать пул граничного пула (для компонентов мультимедиа)**.</span><span class="sxs-lookup"><span data-stu-id="b0e57-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="b0e57-116">В списке выберите интерфейс пограничного сервера для Бакккомпатсите.</span><span class="sxs-lookup"><span data-stu-id="b0e57-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="b0e57-117">![Диалоговое окно "изменение свойств", страница "Общие] " (images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Диалоговое окно \"изменение свойств\", страница \"Общие") "</span><span class="sxs-lookup"><span data-stu-id="b0e57-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="b0e57-118">Нажмите кнопку **ОК** , чтобы закрыть страницу **изменение свойств** .</span><span class="sxs-lookup"><span data-stu-id="b0e57-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="b0e57-119">В **построителе топологии**выберите самый верхний узел, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b0e57-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="b0e57-120">В меню **действие** выберите пункт **топология публикации**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b0e57-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="b0e57-121">После завершения работы **мастера публикации** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="b0e57-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

