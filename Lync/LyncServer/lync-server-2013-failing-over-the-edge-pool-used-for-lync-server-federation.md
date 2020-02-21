---
title: 'Lync Server 2013: отработка отказа для пограничного пула, используемого для Федерации Lync Server'
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
ms.openlocfilehash: 1589fe63c41cb2c4cbff9b72f42a3cc06b43e5d3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="a4120-102">Отработка отказа для пограничного пула, используемого для Федерации Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4120-102">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4120-103">_**Последнее изменение темы:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="a4120-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="a4120-104">Если пограничный пол, на котором настроена федерация Lync Server, перестает работать, необходимо изменить федерацию для использования другого пограничного пула, что восстановит работу федерации.</span><span class="sxs-lookup"><span data-stu-id="a4120-104">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="a4120-105">Отработка отказа пограничного пула, используемого для федерации Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4120-105">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="a4120-p101">На интерфейсном сервере откройте построитель топологий. Разверните узел **Пограничные пулы**, затем щелкните правой кнопкой мыши пограничный сервер или пул пограничных серверов, настроенный в настоящее время для федерации. Выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="a4120-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>

2.  <span data-ttu-id="a4120-p102">В разделе **Общие** области **Изменение свойств** снимите флажок **Включение федерации для этого пограничного пула (порт 5061)**. Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a4120-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

3.  <span data-ttu-id="a4120-p103">Разверните узел **Пограничные пулы**, затем щелкните правой кнопкой мыши пограничный сервер или пул пограничных серверов, который следует использовать для федерации. Выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="a4120-p103">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation. Select **Edit properties**.</span></span>

4.  <span data-ttu-id="a4120-p104">В разделе **Общие** области **Изменение свойств** установите флажок **Включение федерации для этого пограничного пула (порт 5061)**. Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a4120-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="a4120-p105">Щелкните **Действие**, выберите **Топология**, затем **Опубликовать**. По запросу **Публикация топологии** нажмите кнопку **Далее**. При завершении публикации нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a4120-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="a4120-p106">На пограничном сервере откройте мастер развертывания Lync Server. Щелкните **Установить или обновить систему Lync Server**, затем щелкните **Установить или удалить компоненты Lync Server**. Щелкните **Перезапуск**.</span><span class="sxs-lookup"><span data-stu-id="a4120-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>

7.  <span data-ttu-id="a4120-p107">На экране установке компонентов Lync Server нажмите кнопку **Далее**. На экране сводки будут отображаться действия по мере их выполнения. После завершения развертывания щелкните **Просмотреть журнал** для просмотра доступных файлов журнала. Нажмите кнопку **Готово**, чтобы завершить развертывание.</span><span class="sxs-lookup"><span data-stu-id="a4120-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="a4120-125">Если сайт, содержащий неработающий пограничный пул, содержит интерфейсные серверы, которые все еще продолжают работать, необходимо обновить службу веб-конференций и службу аудио- и видеоконференций на этих интерфейсных пулах для использования работоспособного пограничного пула, расположенного на удаленном сайте.</span><span class="sxs-lookup"><span data-stu-id="a4120-125">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="a4120-126">Дополнительную информацию можно узнать [в статье изменение пограничного пула, связанного с пулом переднего плана в Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="a4120-126">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a4120-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a4120-127">See Also</span></span>


[<span data-ttu-id="a4120-128">Отработка отказа для пограничного пула, используемого для Федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4120-128">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="a4120-129">Отработка отказа пограничного пула, используемого для Федерации Lync Server или Федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4120-129">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="a4120-130">Аварийное восстановление пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4120-130">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

