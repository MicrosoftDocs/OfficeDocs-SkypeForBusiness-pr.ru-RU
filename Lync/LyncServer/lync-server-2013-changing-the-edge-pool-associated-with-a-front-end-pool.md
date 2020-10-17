---
title: 'Lync Server 2013: изменение пограничного пула, связанного с пулом переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32404f911766da3ea0f47b74011b4806edbca231
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517886"
---
# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="eaffb-102">Изменение пограничного пула, связанного с пулом переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eaffb-102">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eaffb-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="eaffb-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="eaffb-104">Если пограничный пул отключается, однако интерфейсный пул все еще работает, необходимо указать для интерфейсного пула использование пограничного пула в другом сайте, пока не будет восстановлена работоспособность сбойного пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="eaffb-104">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="eaffb-105">Изменение пограничного пула, связанного с интерфейсным пулом</span><span class="sxs-lookup"><span data-stu-id="eaffb-105">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="eaffb-106">В построителе топологий перейдите к имени интерфейсного пула, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="eaffb-106">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="eaffb-107">Щелкните правой кнопкой мыши соответствующий пул, а затем выберите **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="eaffb-107">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="eaffb-108">В разделе **Связи** под надписью **Сопоставить пограничный пул (для компонентов мультимедиа)** используйте раскрывающееся поле для выбора пограничного пула, с которым следует сопоставить интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="eaffb-108">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="eaffb-109">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eaffb-109">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eaffb-110">См. также</span><span class="sxs-lookup"><span data-stu-id="eaffb-110">See Also</span></span>


[<span data-ttu-id="eaffb-111">Аварийное восстановление пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eaffb-111">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

