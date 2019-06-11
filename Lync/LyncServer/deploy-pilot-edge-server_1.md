---
title: Развертывание пилотного пограничного сервера
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9cfe98069d3c90f4e021b34f6a7d31c583e7565
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="8956d-102">Развертывание пилотного пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8956d-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8956d-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8956d-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8956d-104">В этом разделе описываются параметры конфигурации, которые следует знать перед развертыванием пограничного сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8956d-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="8956d-105">В этом разделе выделены только ключевые моменты, которые следует принимать во внимание при развертывании пула пограничного Edge.</span><span class="sxs-lookup"><span data-stu-id="8956d-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="8956d-106">Подробные инструкции можно найти [в статье Развертывание внешних пользователей Access в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) в документации по развертыванию, в которой описан процесс развертывания, а также сведения о конфигурации для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="8956d-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="8956d-107">При переходе по экрану **Определение нового пула Edge** Просмотрите основные параметры конфигурации, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="8956d-107">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="8956d-108">Обратите внимание, что показаны только несколько страниц мастера **Определение нового пула Edge** .</span><span class="sxs-lookup"><span data-stu-id="8956d-108">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="8956d-109">**Определение пограничного пула**</span><span class="sxs-lookup"><span data-stu-id="8956d-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="8956d-110">Откройте топологию пула пилотных проектов с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="8956d-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="8956d-111">Перейдите на узел Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8956d-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="8956d-112">Щелкните правой кнопкой мыши пункт **Пулы кромок**и выберите команду **создать пул пограничных серверов**.</span><span class="sxs-lookup"><span data-stu-id="8956d-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="8956d-113">![Диалоговое окно "определение нового пула Edge"] (images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Диалоговое окно \"определение нового пула Edge\"")</span><span class="sxs-lookup"><span data-stu-id="8956d-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="8956d-114">Граничный пул может представлять собой **несколько групп компьютеров** или **один пул компьютеров**.</span><span class="sxs-lookup"><span data-stu-id="8956d-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="8956d-115">![Диалоговое окно "Определение полного доменного имени" для пула Edge] (images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Диалоговое окно \"Определение полного доменного имени\" для пула Edge")</span><span class="sxs-lookup"><span data-stu-id="8956d-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="8956d-116">На странице **Выбор компонентов** не включайте Федерацию или КСМПП Федерация.</span><span class="sxs-lookup"><span data-stu-id="8956d-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="8956d-117">Федерацию и Федерация КСМПП в настоящее время пересылаются через старый сервер Office Communications Server 2007 R2 Edge.</span><span class="sxs-lookup"><span data-stu-id="8956d-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="8956d-118">Эти функции будут настроены на более поздней стадии миграции.</span><span class="sxs-lookup"><span data-stu-id="8956d-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="8956d-119">![Диалоговое окно "Выбор компонентов"] (images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Диалоговое окно \"Выбор компонентов\"")</span><span class="sxs-lookup"><span data-stu-id="8956d-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="8956d-120">Затем продолжайте заполнить следующие страницы мастера: **выберите параметры IP**, **Внешние полные доменные имена**, **укажите внутренний IP-адрес**и **укажите внешний IP-адрес**.</span><span class="sxs-lookup"><span data-stu-id="8956d-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="8956d-121">На странице **определение следующего прыжка** выберите режиссера для следующего прыжка пула Lync Server 2013 Edge.</span><span class="sxs-lookup"><span data-stu-id="8956d-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="8956d-122">![Диалоговое окно определения нового пула EDGE, список пулов следующего прыжка] (images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Диалоговое окно определения нового пула EDGE, список пулов следующего прыжка")</span><span class="sxs-lookup"><span data-stu-id="8956d-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="8956d-123">На странице " **сопоставление пулов переднего плана** " не сопоставлены пул с этим пулом Edge.</span><span class="sxs-lookup"><span data-stu-id="8956d-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="8956d-124">Внешний трафик мультимедиа в настоящее время пересылается с помощью устаревшего пограничного сервера Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8956d-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="8956d-125">Этот параметр будет настроен на более поздней стадии миграции.</span><span class="sxs-lookup"><span data-stu-id="8956d-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="8956d-126">![Диалоговое окно определения нового пула Edge] (images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Диалоговое окно определения нового пула Edge")</span><span class="sxs-lookup"><span data-stu-id="8956d-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="8956d-127">Нажмите кнопку **Готово** , а затем **опубликуйте** топологию.</span><span class="sxs-lookup"><span data-stu-id="8956d-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="8956d-128">Следуйте указаниям, приведенным в статье [Установка пограничных серверов для Lync Server 2013](lync-server-2013-install-edge-servers.md) в документации по развертыванию, чтобы установить файлы на новый пограничный сервер, настроить сертификаты и запустить эти службы.</span><span class="sxs-lookup"><span data-stu-id="8956d-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="8956d-129">Очень важно следовать рекомендациям, изложенным в разделе [развертывание внешних пользователей Access в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="8956d-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="8956d-130">В этом разделе приведены рекомендации по настройке конфигурации при установке этих ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="8956d-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="8956d-131">Теперь у вас есть устаревшее развертывание Office Communications Server 2007 R2 Edge Server, которое обозначается наличием Бакккомпатсите, параллельно с развертыванием сервера Lync Server 2013 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="8956d-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="8956d-132">Федерация настроена на использование Office Communications Server 2007 R2 Director.</span><span class="sxs-lookup"><span data-stu-id="8956d-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="8956d-133">Убедитесь, что оба развертывания выполняются правильно, службы запущены и вы можете администрировать каждое развертывание перед переходом к следующему этапу.</span><span class="sxs-lookup"><span data-stu-id="8956d-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="8956d-134">![Построитель топологии, демонстрирующий пограничный сервер OCS] (images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Построитель топологии, демонстрирующий пограничный сервер OCS")</span><span class="sxs-lookup"><span data-stu-id="8956d-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

