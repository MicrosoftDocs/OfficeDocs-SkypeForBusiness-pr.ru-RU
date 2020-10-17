---
title: Развертывание пилотного пограничного сервера
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27b7cf106cb8c65f01a1c1935ff98a8f9d428b27
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502936"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="bc15f-102">Развертывание пилотного пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="bc15f-102">Deploy pilot Edge Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc15f-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="bc15f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="bc15f-104">В этом разделе описываются параметры конфигурации, которые следует знать перед развертыванием пограничного сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc15f-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="bc15f-105">В этом разделе освещаются только ключевые моменты, которые следует проанализировать как часть развертывания пилотного пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="bc15f-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="bc15f-106">Подробное описание действий приведено в разделе [deploy User Access Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) в документации по развертыванию, в котором описывается процесс развертывания, а также сведения о конфигурации для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="bc15f-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="bc15f-p102">По мере перехода по страницам мастера **Определение нового пограничного пула** анализируйте основные параметры конфигурации, показанные на следующих шагах. Обратите внимание, что показано лишь несколько страниц мастера **Определение нового пограничного пула**.</span><span class="sxs-lookup"><span data-stu-id="bc15f-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="bc15f-109">**Определение пограничного пула**</span><span class="sxs-lookup"><span data-stu-id="bc15f-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="bc15f-110">Откройте топологию пилотного пула с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="bc15f-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="bc15f-111">Перейдите к узлу Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc15f-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="bc15f-112">Щелкните правой кнопкой мыши пункт **Пограничные пулы** и выберите в контекстном меню команду **Создать пограничный пул**.</span><span class="sxs-lookup"><span data-stu-id="bc15f-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="bc15f-113">![Диалоговое окно "определение нового пограничного пула"](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Диалоговое окно "определение нового пограничного пула"")</span><span class="sxs-lookup"><span data-stu-id="bc15f-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="bc15f-114">Пограничный пул может представлять собой **Пул нескольких компьютеров** или **Пул одиночного компьютера**.</span><span class="sxs-lookup"><span data-stu-id="bc15f-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="bc15f-115">![Диалоговое окно "Определение полного доменного имени пограничного пула"](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Диалоговое окно "Определение полного доменного имени пограничного пула"")</span><span class="sxs-lookup"><span data-stu-id="bc15f-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="bc15f-116">На странице **Выбор компонентов** не включайте ни федерацию, ни федерацию XMPP.</span><span class="sxs-lookup"><span data-stu-id="bc15f-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="bc15f-117">Федерации Федерации и XMPP в настоящее время направляются через устаревший пограничный сервер Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bc15f-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="bc15f-118">Эти компоненты настраиваются на более позднем этапе миграции.</span><span class="sxs-lookup"><span data-stu-id="bc15f-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="bc15f-119">![Диалоговое окно "Выбор компонентов"](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Диалоговое окно "Выбор компонентов"")</span><span class="sxs-lookup"><span data-stu-id="bc15f-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="bc15f-120">Далее продолжайте выполнять действия, описываемые на следующих страницах мастера: **Выбор IP-параметров**, **Внешние полные доменные имена**, **Определение внутреннего IP-адреса** и **Определение внешнего IP-адреса**.</span><span class="sxs-lookup"><span data-stu-id="bc15f-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="bc15f-121">На странице **определение следующего прыжка** выберите директор для следующего прыжка пограничного пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc15f-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="bc15f-122">![Диалоговое окно определения нового пограничного пула, список "пул следующего прыжка"](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Диалоговое окно определения нового пограничного пула, список "пул следующего прыжка"")</span><span class="sxs-lookup"><span data-stu-id="bc15f-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="bc15f-123">На странице " **сопоставление пулов переднего плана** " не связывайте пул с этим пограничным пулом в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="bc15f-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="bc15f-124">Внешний трафик мультимедиа в настоящее время направляется через устаревший пограничный сервер Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bc15f-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="bc15f-125">Этот параметр настраивается на более позднем этапе миграции.</span><span class="sxs-lookup"><span data-stu-id="bc15f-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="bc15f-126">![Диалоговое окно определения нового пограничного пула](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Диалоговое окно определения нового пограничного пула")</span><span class="sxs-lookup"><span data-stu-id="bc15f-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="bc15f-127">Нажмите кнопку **Готово**, а затем **Опубликуйте** топологию.</span><span class="sxs-lookup"><span data-stu-id="bc15f-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="bc15f-128">Выполните действия, описанные в статье [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) , в документации по развертыванию, чтобы установить файлы на новый пограничный сервер, настроить сертификаты и запустить службы.</span><span class="sxs-lookup"><span data-stu-id="bc15f-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="bc15f-129">Очень важно следовать рекомендациям, изложенным в разделах, посвященным [развертыванию внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) , в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="bc15f-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="bc15f-130">В этом разделе приводятся только некоторые указания по параметрам конфигурации при установке данных серверных ролей.</span><span class="sxs-lookup"><span data-stu-id="bc15f-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="bc15f-131">Теперь у вас будет устаревшее развертывание пограничного сервера Office Communications Server 2007 R2, которое обозначается присутствием BackCompatSite параллельно с развертыванием пограничного сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc15f-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="bc15f-132">Федерация настроена на использование Office Communications Server 2007 R2 Director.</span><span class="sxs-lookup"><span data-stu-id="bc15f-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="bc15f-133">До перехода на следующий этап проверьте, чтобы оба развертывания функционировали правильно, службы были запущены и чтобы можно было администрировать каждое развертывание.</span><span class="sxs-lookup"><span data-stu-id="bc15f-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="bc15f-134">![Построитель топологий, демонстрирующий пограничный сервер OCS](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Построитель топологий, демонстрирующий пограничный сервер OCS")</span><span class="sxs-lookup"><span data-stu-id="bc15f-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

