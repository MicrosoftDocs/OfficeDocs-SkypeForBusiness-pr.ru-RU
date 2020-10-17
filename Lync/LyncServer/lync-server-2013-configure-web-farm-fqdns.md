---
title: 'Lync Server 2013: Настройка полных доменных имен веб-ферм'
description: 'Lync Server 2013: Настройка полных доменных имен веб-фермы.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a07faac4d4809ffe10e7ca3699e7441e6dbcb7b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566665"
---
# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="f0dd4-103">Настройка полных доменных имен веб-ферм для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0dd4-103">Configure web farm FQDNs for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0dd4-104">_**Последнее изменение темы:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="f0dd4-104">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="f0dd4-105">При определении конфигурации сервера Standard Edition, интерфейсного пула, директора или пула директоров в построителе топологий необходимо настроить полное доменное имя внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="f0dd4-105">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="f0dd4-106">Во время процесса входа клиента, размещенного на сервере Standard Edition или интерфейсном пуле, настроенные полные доменные имена веб-служб отправляются с помощью встроенной подготовки.</span><span class="sxs-lookup"><span data-stu-id="f0dd4-106">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="f0dd4-107">Если необходимо добавить или изменить URL-адрес внешних веб-служб, используйте построитель топологий для настройки или повторной настройки конфигурации веб-служб с помощью процедуры, описанной в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="f0dd4-107">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="f0dd4-108">Настройка полного доменного имени внешнего пула для веб-служб</span><span class="sxs-lookup"><span data-stu-id="f0dd4-108">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="f0dd4-109">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f0dd4-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="f0dd4-110">В построителе топологий, в дереве консоли в разделе **передний план переднего плана выпуска**Enterprise Edition, на **серверах переднего плана Enterprise Edition**и **режиссерах**, щелкните правой кнопкой мыши имя пула, который необходимо изменить, а затем выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="f0dd4-110">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="f0dd4-111">В разделе**Веб-службы** добавьте или измените **полное доменное имя внешних веб-служб**.</span><span class="sxs-lookup"><span data-stu-id="f0dd4-111">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="f0dd4-p102">Изучите и измените **прослушиваемые порты** для HTTP и HTTPS. Значения по умолчанию будут следующими:</span><span class="sxs-lookup"><span data-stu-id="f0dd4-p102">Review and adjust the **Listening ports** for both HTTP and HTTPS. The defaults will be:</span></span>
    
      - <span data-ttu-id="f0dd4-114">\*\*Прослушиваемые порты: \*\* HTTP 8080, HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="f0dd4-114">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="f0dd4-115">\*\*Опубликованные порты: \*\* HTTP 80, HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="f0dd4-115">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="f0dd4-116">Где **Прослушиваемые порты** — это порты, на которых внешние веб-службы будут получать запросы от обратного прокси-сервера, а **Опубликованные порты** — это порты, которые публикуются внешне с помощью обратного прокси-сервера и передаются клиентам во время подготовки штатного канала.</span><span class="sxs-lookup"><span data-stu-id="f0dd4-116">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="f0dd4-117">После завершения изменений нажмите кнопку **ОК** для продолжения.</span><span class="sxs-lookup"><span data-stu-id="f0dd4-117">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="f0dd4-118">Щелкните правой кнопкой мыши **Lync Server 2013**и выберите команду **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="f0dd4-118">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f0dd4-119">После успешного завершения публикации может быть представлена ссылка, сообщающая о том, что необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="f0dd4-119">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="f0dd4-120">Если щелкнуть ссылку, откроется список серверов, на которые влияют изменения, внесенные в построителе топологий, для обновления конфигурации добавления, удаления или изменения компонентов необходимо повторно запустить мастер развертывания Lync Server на каждом указанном сервере.</span><span class="sxs-lookup"><span data-stu-id="f0dd4-120">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="f0dd4-121">Повторите эти действия для каждого сервера Standard Edition, интерфейсного пула, директора или пула директоров в Организации.</span><span class="sxs-lookup"><span data-stu-id="f0dd4-121">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

