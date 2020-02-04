---
title: 'Lync Server 2013: отработка отказа для пограничного пула, используемого для федерации Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f144def3d3a8df9cc63221342a85666eb3c28913
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="33930-102">Отработка отказа для пограничного пула, используемого для федерации Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33930-102">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33930-103">_**Тема последнего изменения:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="33930-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="33930-104">Если пул пограничного пула, на котором настроена сервер Lync Server Federation, не работает, необходимо изменить Федерацию для использования другого пула Edge для работы Федерации.</span><span class="sxs-lookup"><span data-stu-id="33930-104">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="33930-105">Сбой в пуле EDGE, используемом для интеграции с Lync Server</span><span class="sxs-lookup"><span data-stu-id="33930-105">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="33930-106">На сервере переднего плана откройте окно Построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="33930-106">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="33930-107">Разверните узел **Edge**Pools, а затем щелкните правой кнопкой мыши граничный сервер пограничного сервера или пул пограничного сервера, настроенный на данный момент для Федерации.</span><span class="sxs-lookup"><span data-stu-id="33930-107">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="33930-108">Нажмите кнопку **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="33930-108">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="33930-109">В диалоговом окне **изменение свойств** в разделе **Общие**снимите флажок **включить федерацию для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="33930-109">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="33930-110">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="33930-110">Click **OK**.</span></span>

3.  <span data-ttu-id="33930-111">Разверните узел **Edge**Pools, а затем щелкните правой кнопкой мыши граничный сервер пограничного сервера или пул пограничного сервера, который вы хотите использовать для Федерации.</span><span class="sxs-lookup"><span data-stu-id="33930-111">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="33930-112">Нажмите кнопку **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="33930-112">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="33930-113">В диалоговом окне **изменение свойств** в разделе **Общие**установите флажок **включить федерацию для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="33930-113">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="33930-114">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="33930-114">Click **OK**.</span></span>

5.  <span data-ttu-id="33930-115">Нажмите кнопку **действие**, выберите пункт **топология**, нажмите кнопку **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="33930-115">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="33930-116">При появлении запроса на **публикацию топологии**нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="33930-116">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="33930-117">Завершив публикацию, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="33930-117">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="33930-118">На пограничном сервере откройте мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="33930-118">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="33930-119">Щелкните **Установка или обновление операционной системы Lync Server**, а затем нажмите кнопку **Настройка или удалите компоненты Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="33930-119">Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**.</span></span> <span data-ttu-id="33930-120">Нажмите кнопку **выполнить еще раз**.</span><span class="sxs-lookup"><span data-stu-id="33930-120">Click **Run Again**.</span></span>

7.  <span data-ttu-id="33930-121">В разделе Настройка серверных компонентов Lync нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="33930-121">At Setup Lync Server components, click **Next**.</span></span> <span data-ttu-id="33930-122">На экране сводки будут показаны действия по мере их выполнения.</span><span class="sxs-lookup"><span data-stu-id="33930-122">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="33930-123">После завершения развертывания щелкните **Просмотреть журнал** , чтобы просмотреть доступные файлы журнала.</span><span class="sxs-lookup"><span data-stu-id="33930-123">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="33930-124">Нажмите кнопку **Готово** , чтобы завершить развертывание.</span><span class="sxs-lookup"><span data-stu-id="33930-124">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="33930-125">Если сайт, содержащий неисправный пул, содержит серверы переднего плана, которые еще не запущены, для использования пула EDGE на удаленном сайте, который еще не работает, необходимо обновить службу веб-конференций и службу Конференции/V на этих интерфейсных пулах.</span><span class="sxs-lookup"><span data-stu-id="33930-125">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="33930-126">Дополнительные сведения можно найти [в разделе Изменение пула EDGE, связанного с пулом переднего плана в Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="33930-126">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33930-127">См. также</span><span class="sxs-lookup"><span data-stu-id="33930-127">See Also</span></span>


[<span data-ttu-id="33930-128">Отработка отказа для пограничного пула, используемого для федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33930-128">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="33930-129">Отработка отказа для пограничного пула, используемого для федерации Lync Server или федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33930-129">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="33930-130">Аварийное восстановление пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33930-130">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

