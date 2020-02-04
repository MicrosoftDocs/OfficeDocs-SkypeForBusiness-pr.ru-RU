---
title: 'Lync Server 2013: настройка полных доменных имен в веб-ферме'
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
ms.openlocfilehash: 4bd01b02cef8d806f390b6b700fa42acd37e27d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="62197-102">Настройка полных доменных имен в веб-ферме для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62197-102">Configure web farm FQDNs for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62197-103">_**Тема последнего изменения:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="62197-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="62197-104">При определении конфигурации стандартного сервера выпуска, пула доменных имен, режиссера или режиссера в построителе топологии вы настраиваете для внешней службы веб-служб полное имя домена (FQDN).</span><span class="sxs-lookup"><span data-stu-id="62197-104">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="62197-105">Во время входа в систему клиента, расположенного на стандартном сервере выпуска Standard Edition или в пуле внешних интерфейсов, настроенные полные доменные имена веб-служб отправляются с помощью встроенной возможности подготовки.</span><span class="sxs-lookup"><span data-stu-id="62197-105">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="62197-106">Если вам нужно добавить или изменить URL-адрес внешней веб-службы, вы можете настроить конфигурацию веб-служб с помощью Topology Builder, выполнив описанные в этой статье действия.</span><span class="sxs-lookup"><span data-stu-id="62197-106">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="62197-107">Настройка полного доменного имени внешнего пула для веб-служб</span><span class="sxs-lookup"><span data-stu-id="62197-107">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="62197-108">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="62197-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="62197-109">В построителе топологии в дереве консоли под заголовком " **стандартный выпуск**" переднего плана, а также **режиссеров** **Enterprise Edition**щелкните правой кнопкой мыши имя пула, которое нужно изменить, и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="62197-109">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="62197-110">В разделе **веб-службы** добавьте или измените **полное доменное имя внешней веб-службы**.</span><span class="sxs-lookup"><span data-stu-id="62197-110">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="62197-111">Проверьте и настройте **порты прослушивания** как для HTTP, так и для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="62197-111">Review and adjust the **Listening ports** for both HTTP and HTTPS.</span></span> <span data-ttu-id="62197-112">По умолчанию будут использоваться следующие значения:</span><span class="sxs-lookup"><span data-stu-id="62197-112">The defaults will be:</span></span>
    
      - <span data-ttu-id="62197-113">**Порты для прослушивания:** HTTP 8080, HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="62197-113">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="62197-114">**Опубликованные порты:** HTTP 80, HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="62197-114">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="62197-115">Где **порт прослушивания** — это порт, на котором внешние веб-службы будут настроены для получения запросов от обратного прокси-сервера, а **опубликованные порты** — это порты, которые были опубликованы извне обратно прокси-сервером и передаются клиентам во время подготовки по каналу.</span><span class="sxs-lookup"><span data-stu-id="62197-115">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="62197-116">Завершив добавление и обновление, нажмите кнопку **ОК** , чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="62197-116">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="62197-117">Щелкните правой кнопкой мыши **Lync Server 2013**и выберите команду **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="62197-117">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="62197-118">После успешного завершения публикации появляется ссылка, в которой сообщается о том, что нужно выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="62197-118">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="62197-119">Ссылка, если она была нажата, открывает список серверов, на которые влияет изменения, внесенные в построителе топологии, требующие повторного запуска мастера развертывания Lync Server на каждом из указанных серверов для обновления конфигурации для добавления, удаления или изменения компонентов.</span><span class="sxs-lookup"><span data-stu-id="62197-119">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="62197-120">Повторите эти действия для каждого стандартного сервера выпуска, пула, режиссера или режиссера в Организации.</span><span class="sxs-lookup"><span data-stu-id="62197-120">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

