---
title: Отработка отказа для пограничного пула, используемого для федерации Lync Server или федерации XMPP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d75e4dbe8265050d30620b0ecbdd1992b480106e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="754ae-102">Отработка отказа для пограничного пула, используемого для федерации Lync Server или федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="754ae-102">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="754ae-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="754ae-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="754ae-104">После того как пул пограничного пула, который использовался для размещения Федерации, станет доступен в сети, выполните описанные ниже действия, чтобы восстановить маршрут Федерации Lync Server и/или КСМПП Федерации для повторного использования этого восстановленного пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="754ae-104">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="754ae-105">Сбой обратной интеграции в восстановленный пул Edge</span><span class="sxs-lookup"><span data-stu-id="754ae-105">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="754ae-106">В пуле EDGE, который теперь доступен еще раз, запустите службы Edge.</span><span class="sxs-lookup"><span data-stu-id="754ae-106">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="754ae-107">Если вы хотите вернуть маршрут Федерации Lync Server для использования восстановленного пограничного сервера, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="754ae-107">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="754ae-108">На сервере переднего плана откройте окно Построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="754ae-108">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="754ae-109">Разверните узел **Edge**Pools, а затем щелкните правой кнопкой мыши граничный сервер пограничного сервера или пул пограничного сервера, настроенный на данный момент для Федерации.</span><span class="sxs-lookup"><span data-stu-id="754ae-109">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="754ae-110">Нажмите кнопку **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="754ae-110">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="754ae-111">В диалоговом окне **изменение свойств** в разделе **Общие**снимите флажок **включить федерацию для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="754ae-111">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="754ae-112">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="754ae-112">Click **OK**.</span></span>
    
      - <span data-ttu-id="754ae-113">Разверните узел **Edge**Pools, а затем щелкните правой кнопкой мыши исходный сервер пограничного сервера или пул пограничного сервера, который вы снова хотите использовать для Федерации.</span><span class="sxs-lookup"><span data-stu-id="754ae-113">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="754ae-114">Нажмите кнопку **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="754ae-114">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="754ae-115">В диалоговом окне **изменение свойств** в разделе **Общие**установите флажок **включить федерацию для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="754ae-115">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="754ae-116">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="754ae-116">Click **OK**.</span></span>
    
      - <span data-ttu-id="754ae-117">Нажмите кнопку **действие**, выберите пункт **топология**, нажмите кнопку **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="754ae-117">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="754ae-118">При появлении запроса на **публикацию топологии**нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="754ae-118">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="754ae-119">Завершив публикацию, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="754ae-119">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="754ae-120">На пограничном сервере откройте мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="754ae-120">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="754ae-121">Щелкните **Установка или обновление операционной системы Lync Server**, а затем нажмите кнопку **Настройка или удалите компоненты Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="754ae-121">Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**.</span></span> <span data-ttu-id="754ae-122">Нажмите кнопку **выполнить еще раз**.</span><span class="sxs-lookup"><span data-stu-id="754ae-122">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="754ae-123">В разделе Настройка серверных компонентов Lync нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="754ae-123">At Setup Lync Server components, click **Next**.</span></span> <span data-ttu-id="754ae-124">На экране сводки будут показаны действия по мере их выполнения.</span><span class="sxs-lookup"><span data-stu-id="754ae-124">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="754ae-125">После завершения развертывания щелкните **Просмотреть журнал** , чтобы просмотреть доступные файлы журнала.</span><span class="sxs-lookup"><span data-stu-id="754ae-125">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="754ae-126">Нажмите кнопку **Готово** , чтобы завершить развертывание.</span><span class="sxs-lookup"><span data-stu-id="754ae-126">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="754ae-127">Если вы хотите восстановить маршрут Федерации КСМПП для использования восстановленного пограничного сервера, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="754ae-127">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="754ae-128">Запустите следующий командлет, чтобы перенаправить маршрут Федерации КСМПП на Граничный пул, который будет размещен КСМПП Federation (в этом примере — EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="754ae-128">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="754ae-129">В этом примере site1 — сайт с пулом EDGE, который теперь будет размещаться на маршруте Федерации КСМПП, а EdgeServer1.contoso.com — это полное доменное имя пограничного сервера в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="754ae-129">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="754ae-130">Если у вас еще нет DNS-записи SRV для Федерации КСМПП, которая разрешается в пул EDGE, который теперь будет размещаться в КСМПП Федерации, необходимо добавить его, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="754ae-130">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="754ae-131">Для этой записи SRV должно быть задано значение Port 5269.</span><span class="sxs-lookup"><span data-stu-id="754ae-131">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="754ae-132">На внешнем DNS-сервере измените запись DNS A для Федерации КСМПП, чтобы она указывала на EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="754ae-132">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="754ae-133">Убедитесь, что в пуле EDGE, на котором будет размещена КСМПП Федерация, есть порт 5269, Открытый извне.</span><span class="sxs-lookup"><span data-stu-id="754ae-133">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="754ae-134">Если на веб-сайте, содержащем пул пограничного сервера, не удалось выполнить все неудачные и восстановленные интерфейсы, следует обновить службу веб-конференций и службу Конференции/V на этих интерфейсных пулах с помощью пулов EDGE на своем локальном сайте.</span><span class="sxs-lookup"><span data-stu-id="754ae-134">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="754ae-135">Дополнительные сведения можно найти [в разделе Изменение пула EDGE, связанного с пулом переднего плана в Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="754ae-135">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="754ae-136">Если пул переднего плана на сайте, на котором произошла ошибка, также завершился сбоем, вы можете использовать Invoke – Кспулфаилбакк для возврата пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="754ae-136">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="754ae-137">См. также</span><span class="sxs-lookup"><span data-stu-id="754ae-137">See Also</span></span>


[<span data-ttu-id="754ae-138">Отработка отказа для пограничного пула, используемого для федерации Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="754ae-138">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="754ae-139">Отработка отказа для пограничного пула, используемого для федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="754ae-139">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="754ae-140">Аварийное восстановление пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="754ae-140">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

