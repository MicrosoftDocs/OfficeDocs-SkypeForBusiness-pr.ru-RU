---
title: Подключение пилотного пула к старым пограничным серверам
description: Подключение пилотного пула к старым пограничным серверам.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ede2256efabf561be6b3f99543437087cb5c3890
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550275"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="eaf3d-103">Подключение пилотного пула к старым пограничным серверам</span><span class="sxs-lookup"><span data-stu-id="eaf3d-103">Connect pilot pool to legacy Edge Servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eaf3d-104">_**Последнее изменение темы:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="eaf3d-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="eaf3d-105">После развертывания Lync Server 2013 необходимо настроить маршрут Федерации для сайта.</span><span class="sxs-lookup"><span data-stu-id="eaf3d-105">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="eaf3d-106">Чтобы использовать федеративный маршрут, используемый Lync Server 2010, необходимо настроить Lync Server 2013 для использования этого маршрута.</span><span class="sxs-lookup"><span data-stu-id="eaf3d-106">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="eaf3d-107">Чтобы разрешить сайту Lync Server 2013 использовать директор и пограничный сервер развертывания Lync Server 2010, используйте построитель топологий для связи устаревшего пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="eaf3d-107">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="eaf3d-108">Связь устаревшего пограничного пула с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="eaf3d-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="eaf3d-109">Откройте **построитель топологий**.</span><span class="sxs-lookup"><span data-stu-id="eaf3d-109">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="eaf3d-110">Выберите свой сайт, который находится сразу под узлом **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="eaf3d-110">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="eaf3d-111">В меню **Actions** (Действия) выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="eaf3d-111">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="eaf3d-112">В левой области выберите **Федеративный маршрут**.</span><span class="sxs-lookup"><span data-stu-id="eaf3d-112">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="eaf3d-113">В разделе **назначение федеративного маршрута сайта**выберите **включить федерацию SIP**, а затем выберите режиссер Lync Server 2010 или пограничный сервер Lync Server 2010, если в списке нет директоров.</span><span class="sxs-lookup"><span data-stu-id="eaf3d-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="eaf3d-114">![Страница "изменить свойства", "маршрут Федерации"](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Страница "изменить свойства", "маршрут Федерации"")</span><span class="sxs-lookup"><span data-stu-id="eaf3d-114">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="eaf3d-115">Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**.</span><span class="sxs-lookup"><span data-stu-id="eaf3d-115">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="eaf3d-116">В построителе топологий разверните узел Lync Server 2013 и перейдите к пулам **переднего плана** **сервера Standard Edition** или Enterprise Edition, щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="eaf3d-116">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="eaf3d-117">В разделе **Associations** (Связи) установите флажок **Associate Edge pool (for media components)** (Связать пограничный пул (для компонентов медиа)).</span><span class="sxs-lookup"><span data-stu-id="eaf3d-117">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="eaf3d-118">Выберите в списке устаревший пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="eaf3d-118">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="eaf3d-119">![Диалоговое окно "изменение свойств" с выбором прежнего пограничного края](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Диалоговое окно "изменение свойств" с выбором прежнего пограничного края")</span><span class="sxs-lookup"><span data-stu-id="eaf3d-119">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="eaf3d-120">Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**.</span><span class="sxs-lookup"><span data-stu-id="eaf3d-120">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="eaf3d-121">В **построителе топологий** выберите самый верхний узел, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="eaf3d-121">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="eaf3d-122">В меню **Action** (Действие) выберите команду **Publish Topology** (Опубликовать топологию) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eaf3d-122">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="eaf3d-123">Когда **мастер публикации** завершит работу, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="eaf3d-123">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

