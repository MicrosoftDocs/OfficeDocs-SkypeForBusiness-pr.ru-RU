---
title: Развертывание пилотного пограничного сервера
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2227e4ca38039b60d9ef26c25bfe11c3cc7fff6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="24192-102">Развертывание пилотного пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="24192-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24192-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="24192-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="24192-104">В этом разделе описываются параметры конфигурации, которые следует знать перед развертыванием пограничного сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24192-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="24192-105">Процессы развертывания и настройки для Lync Server 2013 очень похожи на Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="24192-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="24192-106">В этом разделе рассматриваются только ключевые моменты, которые следует учитывать при развертывании пилотной версии пула.</span><span class="sxs-lookup"><span data-stu-id="24192-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="24192-107">Подробное описание действий приведено в разделе [deploy User Access Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) в документации по развертыванию, в котором описывается процесс развертывания, а также сведения о конфигурации для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="24192-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="24192-p102">По мере перехода по страницам мастера **Определение нового пограничного пула** анализируйте основные параметры конфигурации, показанные на следующих шагах. Обратите внимание, что показано лишь несколько страниц мастера **Определение нового пограничного пула**.</span><span class="sxs-lookup"><span data-stu-id="24192-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="24192-110">**Определение пограничного пула**</span><span class="sxs-lookup"><span data-stu-id="24192-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="24192-111">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="24192-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="24192-112">Перейдите к узлу Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24192-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="24192-113">Щелкните правой кнопкой мыши пункт **Пограничные пулы** и выберите в контекстном меню команду **Создать пограничный пул**.</span><span class="sxs-lookup"><span data-stu-id="24192-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="24192-114">![Диалоговое окно "определение нового пограничного пула"](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Диалоговое окно "определение нового пограничного пула"")</span><span class="sxs-lookup"><span data-stu-id="24192-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="24192-115">Пограничный пул может представлять собой **Пул нескольких компьютеров** или **Пул одиночного компьютера**.</span><span class="sxs-lookup"><span data-stu-id="24192-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="24192-116">![Диалоговое окно "Определение полного доменного имени пограничного пула"](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Диалоговое окно "Определение полного доменного имени пограничного пула"")</span><span class="sxs-lookup"><span data-stu-id="24192-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="24192-117">На странице **Выбор компонентов** не включайте ни федерацию, ни федерацию XMPP.</span><span class="sxs-lookup"><span data-stu-id="24192-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="24192-118">Федерации Федерации и XMPP в настоящее время направляются через пограничный сервер Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="24192-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="24192-119">Эти компоненты настраиваются на более позднем этапе миграции.</span><span class="sxs-lookup"><span data-stu-id="24192-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="24192-120">![Диалоговое окно "Выбор компонентов"](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Диалоговое окно "Выбор компонентов"")</span><span class="sxs-lookup"><span data-stu-id="24192-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="24192-121">Затем следуйте инструкциям, представленным на следующих страницах мастера: **External FQDNs** (Внешние полные доменные имена), **Define the internal IP address** (Задание внутреннего IP-адреса) и **Define the external IP address** (Задание внешнего IP-адреса).</span><span class="sxs-lookup"><span data-stu-id="24192-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="24192-122">На странице **определение следующего прыжка** выберите директор для следующего прыжка пограничного пула Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="24192-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="24192-123">![Диалоговое окно "определение следующего прыжка"](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Диалоговое окно "определение следующего прыжка"")</span><span class="sxs-lookup"><span data-stu-id="24192-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="24192-124">На странице " **сопоставление интерфейсных серверов или пулов-посредников** " не связывайте пул с этим пограничным пулом в данный момент.</span><span class="sxs-lookup"><span data-stu-id="24192-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="24192-125">Внешний трафик мультимедиа в настоящее время направляется через пограничный сервер Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="24192-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="24192-126">Этот параметр настраивается на более позднем этапе миграции.</span><span class="sxs-lookup"><span data-stu-id="24192-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="24192-127">![Диалоговое окно "Связывание интерфейсных пулов"](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Диалоговое окно "Связывание интерфейсных пулов"")</span><span class="sxs-lookup"><span data-stu-id="24192-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="24192-128">Нажмите кнопку **Готово**, а затем **Опубликуйте** топологию.</span><span class="sxs-lookup"><span data-stu-id="24192-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="24192-129">Выполните действия, описанные в статье [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) , в документации по развертыванию, чтобы установить файлы на новый пограничный сервер, настроить сертификаты и запустить службы.</span><span class="sxs-lookup"><span data-stu-id="24192-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="24192-130">Очень важно следовать рекомендациям, изложенным в разделах, посвященным [развертыванию внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) , в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="24192-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="24192-131">В этом разделе приводятся только некоторые указания по параметрам конфигурации при установке данных серверных ролей.</span><span class="sxs-lookup"><span data-stu-id="24192-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="24192-132">Теперь у вас должен быть параллельно развернут устаревший пограничный сервер Lync Server 2010 с развертыванием пограничного сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24192-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="24192-133">До перехода на следующий этап проверьте, чтобы оба развертывания функционировали правильно, службы были запущены и чтобы можно было администрировать каждое развертывание.</span><span class="sxs-lookup"><span data-stu-id="24192-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

