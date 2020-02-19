---
title: 'Lync Server 2013: Настройка полных доменных имен веб-ферм'
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
ms.openlocfilehash: 50813855e4181add65ff279933a952116768dcec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="dea9c-102">Настройка полных доменных имен веб-ферм для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dea9c-102">Configure web farm FQDNs for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dea9c-103">_**Последнее изменение темы:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="dea9c-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="dea9c-104">При определении конфигурации сервера Standard Edition, интерфейсного пула, директора или пула директоров в построителе топологий необходимо настроить полное доменное имя внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="dea9c-104">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="dea9c-105">Во время процесса входа клиента, размещенного на сервере Standard Edition или интерфейсном пуле, настроенные полные доменные имена веб-служб отправляются с помощью встроенной подготовки.</span><span class="sxs-lookup"><span data-stu-id="dea9c-105">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="dea9c-106">Если необходимо добавить или изменить URL-адрес внешних веб-служб, используйте построитель топологий для настройки или повторной настройки конфигурации веб-служб с помощью процедуры, описанной в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="dea9c-106">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="dea9c-107">Настройка полного доменного имени внешнего пула для веб-служб</span><span class="sxs-lookup"><span data-stu-id="dea9c-107">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="dea9c-108">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dea9c-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="dea9c-109">В построителе топологий, в дереве консоли в разделе **передний план переднего плана выпуска**Enterprise Edition, на **серверах переднего плана Enterprise Edition**и **режиссерах**, щелкните правой кнопкой мыши имя пула, который необходимо изменить, а затем выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="dea9c-109">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="dea9c-110">В разделе**Веб-службы** добавьте или измените **полное доменное имя внешних веб-служб**.</span><span class="sxs-lookup"><span data-stu-id="dea9c-110">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="dea9c-p102">Изучите и измените **прослушиваемые порты** для HTTP и HTTPS. Значения по умолчанию будут следующими:</span><span class="sxs-lookup"><span data-stu-id="dea9c-p102">Review and adjust the **Listening ports** for both HTTP and HTTPS. The defaults will be:</span></span>
    
      - <span data-ttu-id="dea9c-113">\*\*Прослушиваемые порты: \*\* HTTP 8080, HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="dea9c-113">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="dea9c-114">\*\*Опубликованные порты: \*\* HTTP 80, HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="dea9c-114">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="dea9c-115">Где **Прослушиваемые порты** — это порты, на которых внешние веб-службы будут получать запросы от обратного прокси-сервера, а **Опубликованные порты** — это порты, которые публикуются внешне с помощью обратного прокси-сервера и передаются клиентам во время подготовки штатного канала.</span><span class="sxs-lookup"><span data-stu-id="dea9c-115">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="dea9c-116">После завершения изменений нажмите кнопку **ОК** для продолжения.</span><span class="sxs-lookup"><span data-stu-id="dea9c-116">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="dea9c-117">Щелкните правой кнопкой мыши **Lync Server 2013**и выберите команду **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="dea9c-117">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dea9c-118">После успешного завершения публикации может быть представлена ссылка, сообщающая о том, что необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="dea9c-118">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="dea9c-119">Если щелкнуть ссылку, откроется список серверов, на которые влияют изменения, внесенные в построителе топологий, для обновления конфигурации добавления, удаления или изменения компонентов необходимо повторно запустить мастер развертывания Lync Server на каждом указанном сервере.</span><span class="sxs-lookup"><span data-stu-id="dea9c-119">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="dea9c-120">Повторите эти действия для каждого сервера Standard Edition, интерфейсного пула, директора или пула директоров в Организации.</span><span class="sxs-lookup"><span data-stu-id="dea9c-120">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

