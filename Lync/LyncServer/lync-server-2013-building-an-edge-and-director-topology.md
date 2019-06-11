---
title: 'Lync Server 2013: создание топологии пограничных серверов и директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Building an edge and Director topology
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48183451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae45053e8d9c01cd484da8a052304712f04a06fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="8c0e7-102">Создание топологии пограничных серверов и директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c0e7-102">Building an edge and Director topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c0e7-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="8c0e7-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="8c0e7-104">Построение топологии включает следующие задачи планирования и развертывания.</span><span class="sxs-lookup"><span data-stu-id="8c0e7-104">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="8c0e7-105">**Планирование**   необходимо определить подходящую топологию для Организации и определить компоненты, необходимые для ее развертывания.</span><span class="sxs-lookup"><span data-stu-id="8c0e7-105">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="8c0e7-106">Это стандартные действия, которые можно выполнить в процессе планирования.</span><span class="sxs-lookup"><span data-stu-id="8c0e7-106">These are standard steps in the planning process.</span></span> <span data-ttu-id="8c0e7-107">Microsoft Lync Server 2013, средство планирования, предоставленное в Lync Server 2013, упрощает процесс планирования, а также позволяет легко вносить изменения при завершении требований и планов.</span><span class="sxs-lookup"><span data-stu-id="8c0e7-107">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="8c0e7-108">**Развертывание**   . топология, определенная с помощью Topology Builder, очень важна для развертывания любого сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c0e7-108">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="8c0e7-109">Если вы не закончите определение и публикацию топологии с помощью построителя топологии в ходе планирования, необходимо завершить ее и опубликовать топологию перед развертыванием пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="8c0e7-109">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="8c0e7-110">Вы не можете развертывать компоненты пограничного сервера, пока не разворачиваете по крайней мере один внутренний пул, и вам необходимо установить построитель топологии, чтобы развернуть внутренний пул.</span><span class="sxs-lookup"><span data-stu-id="8c0e7-110">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="8c0e7-111">В этом разделе не рассматривается установка Topology Builder, так как это является частью процесса установки внутреннего пула.</span><span class="sxs-lookup"><span data-stu-id="8c0e7-111">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="8c0e7-112">Подробнее об этих средствах см. [в разделе Контрольный список развертывания для внешних пользователей Access в Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8c0e7-112">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8c0e7-113">Если вы ранее использовали Topology Builder, чтобы определить полную топологию, включая топологию EDGE, вы можете пропустить <A href="lync-server-2013-define-your-edge-topology.md">Определение пограничного топологии в Lync server 2013</A> и <A href="lync-server-2013-publish-your-topology.md">опубликовать свою топологию в Lync Server 2013</A> задачи в этом разделе, но вам понадобятся чтобы завершить <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Экспорт топологии сервера Lync Server 2013 и скопировать ее на внешние носители для установки пограничного компьютера</A> , выполните указанные выше операции.</span><span class="sxs-lookup"><span data-stu-id="8c0e7-113">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8c0e7-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="8c0e7-114">In This Section</span></span>

  - [<span data-ttu-id="8c0e7-115">Определение пограничной топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c0e7-115">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="8c0e7-116">Определение дополнительных топологий директоров в топологии для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c0e7-116">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="8c0e7-117">Публикация топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c0e7-117">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="8c0e7-118">Экспорт топологии Lync Server 2013 и ее копирование на внешние носители для установки в пограничной топологии</span><span class="sxs-lookup"><span data-stu-id="8c0e7-118">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

