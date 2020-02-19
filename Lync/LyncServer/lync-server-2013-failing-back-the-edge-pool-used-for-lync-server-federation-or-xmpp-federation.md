---
title: Отработка отказа пограничного пула, используемого для Федерации Lync Server или Федерации XMPP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9001b3fd901888622aaf13922eb59c37e51e9936
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="b7230-102">Отработка отказа пограничного пула, используемого для Федерации Lync Server или Федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7230-102">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7230-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b7230-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b7230-104">После возврата пограничного пула, который используется для размещения федерации, в рабочий режим после сбоя используйте следующую процедуру для восстановления маршрутизации федерации сервера Lync Server и/или маршрутизации федерации XMPP, чтобы снова использовать этот восстановленный пограничный пул.</span><span class="sxs-lookup"><span data-stu-id="b7230-104">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="b7230-105">Восстановление федерации на восстановленном пограничном пуле</span><span class="sxs-lookup"><span data-stu-id="b7230-105">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="b7230-106">Запустите службы пограничного сервера на пограничном пуле, который снова доступен.</span><span class="sxs-lookup"><span data-stu-id="b7230-106">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="b7230-107">Если необходимо восстановить маршрутизацию федерации Lync Server для использования восстановленного пограничного сервера, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b7230-107">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="b7230-p101">На сервере переднего плана откройте построитель топологий. Разверните **пограничные пулы**, затем щелкните правой кнопкой пограничный сервер или пул пограничного сервера, который в настоящее время настроен для федерации. Выберите **Edit properties** (Изменить свойства).</span><span class="sxs-lookup"><span data-stu-id="b7230-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="b7230-p102">В поле **Edit Properties** (Изменить свойства) раздела **General** (Общие) снимите флажок **Enable federation for this Edge pool (Port 5061)** (Разрешить федерацию для этого пограничного пула (порт 506)). Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b7230-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="b7230-p103">Разверните **пограничные пулы**, затем щелкните правой кнопкой исходный пограничный сервер или пул пограничного сервера, который необходимо снова использовать для федерации. Выберите **Edit properties** (Изменить свойства).</span><span class="sxs-lookup"><span data-stu-id="b7230-p103">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="b7230-p104">В поле **Edit Properties** (Изменить свойства) раздела **General** (Общие) установите флажок **Enable federation for this Edge pool (Port 5061)** (Разрешить федерацию для этого пограничного пула (порт 506)). Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b7230-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="b7230-p105">Щелкните **Действие**, выберите **Топология**, затем **Опубликовать**. По запросу **Публикация топологии** нажмите кнопку **Далее**. При завершении публикации нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="b7230-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="b7230-p106">На пограничном сервере откройте мастер развертывания Lync Server. Щелкните **Установить или обновить систему Lync Server**, затем щелкните **Установить или удалить компоненты Lync Server**. Щелкните **Перезапуск**.</span><span class="sxs-lookup"><span data-stu-id="b7230-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>
    
      - <span data-ttu-id="b7230-p107">В разделе установки компонентов Lync Server щелкните **Next** (Далее). На экране сводных данных отображаются действия по мере их выполнения. По завершении развертывания щелкните **View Log** (Просмотреть журнал) для просмотра доступных файлов журнала. Щелкните **Finish** (Готово) для завершения развертывания.</span><span class="sxs-lookup"><span data-stu-id="b7230-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="b7230-127">Если необходимо восстановить маршрутизацию федерации XMPP для использования восстановленного пограничного сервера, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b7230-127">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="b7230-128">Выполните следующий командлет, чтобы повторно указать маршрут федерации XMPP к пограничному пулу, в котором теперь будет размещаться федерация XMPP (в данном примере — EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="b7230-128">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="b7230-129">В данном примере Site1 — это сайт, содержащий пограничный пул, в котором теперь размещается маршрут федерации XMPP, а EdgeServer1.contoso.com — это полное доменное имя пограничного сервера в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="b7230-129">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="b7230-p108">Если у вас пока нет записи DNS SRV для федерации XMPP, которая разрешается в пограничный пул, где будет размещаться федерация XMPP, вы должны добавить ее, как указано в следующем примере. Для этой записи SRV необходимо указать значение порта 5269.</span><span class="sxs-lookup"><span data-stu-id="b7230-p108">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="b7230-132">На внешнем DNS-сервере измените запись DNS A для федерации XMPP таким образом, чтобы она указывала на EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b7230-132">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="b7230-133">Убедитесь, что порт 5269 пограничного пула, в котором теперь будет размещаться федерация XMPP, открыт на внешнем уровне.</span><span class="sxs-lookup"><span data-stu-id="b7230-133">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="b7230-134">Если внешние пулы оставались на сайте, содержащем пограничный пул, который был неудачным и восстановлен, необходимо обновить службу веб-конференций и службу аудио-и видеоконференций на этих интерфейсных пулах, чтобы снова использовать их на локальном сайте.</span><span class="sxs-lookup"><span data-stu-id="b7230-134">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="b7230-135">Дополнительную информацию можно узнать [в статье изменение пограничного пула, связанного с пулом переднего плана в Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="b7230-135">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="b7230-136">Если происходит сбой пула переднего плана на том же сайте, где располагается отказавший пограничный пул, можно использовать Invoke–CsPoolFailback для восстановления пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b7230-136">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b7230-137">См. также</span><span class="sxs-lookup"><span data-stu-id="b7230-137">See Also</span></span>


[<span data-ttu-id="b7230-138">Отработка отказа для пограничного пула, используемого для Федерации Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7230-138">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="b7230-139">Отработка отказа для пограничного пула, используемого для Федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7230-139">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="b7230-140">Аварийное восстановление пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7230-140">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

