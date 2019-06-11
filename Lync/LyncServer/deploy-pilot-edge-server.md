---
title: Развертывание пилотного пограничного сервера
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd8fddd611422562c9384a52748623623d4e6f68
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="305a9-102">Развертывание пилотного пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="305a9-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="305a9-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="305a9-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="305a9-104">В этом разделе описываются параметры конфигурации, которые следует знать перед развертыванием пограничного сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="305a9-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="305a9-105">Процессы развертывания и конфигурации для Lync Server 2013 очень похожи на Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="305a9-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="305a9-106">В этом разделе выделены только ключевые моменты, которые следует принимать во время развертывания пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="305a9-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="305a9-107">Подробные инструкции можно найти [в статье Развертывание внешних пользователей Access в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) в документации по развертыванию, в которой описан процесс развертывания, а также сведения о конфигурации для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="305a9-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="305a9-108">При переходе по экрану **Определение нового пула Edge** Просмотрите основные параметры конфигурации, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="305a9-108">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="305a9-109">Обратите внимание, что показаны только несколько страниц мастера **Определение нового пула Edge** .</span><span class="sxs-lookup"><span data-stu-id="305a9-109">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="305a9-110">**Определение пограничного пула**</span><span class="sxs-lookup"><span data-stu-id="305a9-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="305a9-111">Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="305a9-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="305a9-112">Перейдите на узел Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="305a9-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="305a9-113">Щелкните правой кнопкой мыши пункт **Пулы кромок**и выберите команду **создать пул пограничных серверов**.</span><span class="sxs-lookup"><span data-stu-id="305a9-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="305a9-114">![Диалоговое окно "определение нового пула Edge"] (images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Диалоговое окно \"определение нового пула Edge\"")</span><span class="sxs-lookup"><span data-stu-id="305a9-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="305a9-115">Граничный пул может представлять собой **несколько групп компьютеров** или **один пул компьютеров**.</span><span class="sxs-lookup"><span data-stu-id="305a9-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="305a9-116">![Диалоговое окно "Определение полного доменного имени" для пула Edge] (images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Диалоговое окно \"Определение полного доменного имени\" для пула Edge")</span><span class="sxs-lookup"><span data-stu-id="305a9-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="305a9-117">На странице **Выбор компонентов** не включайте Федерацию или КСМПП Федерация.</span><span class="sxs-lookup"><span data-stu-id="305a9-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="305a9-118">Федерация Федерации и КСМПП в настоящее время пересылается на сервере Lync Server 2010 Edge.</span><span class="sxs-lookup"><span data-stu-id="305a9-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="305a9-119">Эти функции будут настроены на более поздней стадии миграции.</span><span class="sxs-lookup"><span data-stu-id="305a9-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="305a9-120">![Диалоговое окно "Выбор компонентов"] (images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Диалоговое окно \"Выбор компонентов\"")</span><span class="sxs-lookup"><span data-stu-id="305a9-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="305a9-121">Затем продолжайте заполнить следующие страницы мастера: **Внешние полные доменные имена**, **Определите внутренний IP-адрес**и **укажите внешний IP-адрес**.</span><span class="sxs-lookup"><span data-stu-id="305a9-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="305a9-122">На странице **определение следующего прыжка** выберите режиссера для следующего прыжка пула Lync Server 2010 Edge.</span><span class="sxs-lookup"><span data-stu-id="305a9-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="305a9-123">![Диалоговое окно «Определение следующего прыжка»] (images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Диалоговое окно «Определение следующего прыжка»")</span><span class="sxs-lookup"><span data-stu-id="305a9-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="305a9-124">На странице " **сопоставление интерфейсов и пулов** ресурсов" не сопоставлены пул с этим пулом Edge.</span><span class="sxs-lookup"><span data-stu-id="305a9-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="305a9-125">Внешний трафик мультимедиа в настоящее время пересылается с помощью устаревшего сервера Lync Server 2010 Edge.</span><span class="sxs-lookup"><span data-stu-id="305a9-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="305a9-126">Этот параметр будет настроен на более поздней стадии миграции.</span><span class="sxs-lookup"><span data-stu-id="305a9-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="305a9-127">![Диалоговое окно «связывание внешних пулов»] (images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Диалоговое окно «связывание внешних пулов»")</span><span class="sxs-lookup"><span data-stu-id="305a9-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="305a9-128">Нажмите кнопку **Готово** , а затем **опубликуйте** топологию.</span><span class="sxs-lookup"><span data-stu-id="305a9-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="305a9-129">Следуйте указаниям, приведенным в статье [Установка пограничных серверов для Lync Server 2013](lync-server-2013-install-edge-servers.md) в документации по развертыванию, чтобы установить файлы на новый пограничный сервер, настроить сертификаты и запустить эти службы.</span><span class="sxs-lookup"><span data-stu-id="305a9-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="305a9-130">Очень важно следовать рекомендациям, изложенным в разделе [развертывание внешних пользователей Access в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="305a9-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="305a9-131">В этом разделе приведены рекомендации по настройке конфигурации при установке этих ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="305a9-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="305a9-132">Теперь у вас должен быть параллельный развертывание устаревшего пограничного сервера Lync Server 2010 с помощью развертывания Lync Server 2013 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="305a9-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="305a9-133">Убедитесь, что оба развертывания выполняются правильно, службы запущены и вы можете администрировать каждое развертывание перед переходом к следующему этапу.</span><span class="sxs-lookup"><span data-stu-id="305a9-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

