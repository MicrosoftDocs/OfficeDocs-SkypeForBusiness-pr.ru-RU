---
title: 'Этап 8: ликвидация старых пулов'
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 8: Decommission legacy pools'
ms:assetid: 1c68e5d8-fb5f-45e6-b6e3-27f5e830c966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204724(v=OCS.15)
ms:contentKeyID: 48183557
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c82bb7775c43c1bdbbf9ac9c3d788227f16cb76
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532916"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="c0e5d-102">Этап 8: ликвидация старых пулов</span><span class="sxs-lookup"><span data-stu-id="c0e5d-102">Phase 8: Decommission legacy pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0e5d-103">_**Последнее изменение темы:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="c0e5d-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="c0e5d-104">В следующих разделах представлены рекомендации по обновлению записей DNS, перемещению сервера управления контентом, развертыванию пулов, отключению и удалению серверов и пулов из устаревшего развертывания Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c0e5d-104">The following topic provides guidance in updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Lync Server 2010.</span></span> <span data-ttu-id="c0e5d-105">Не все процедуры, рассматриваемые в этом разделе, являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="c0e5d-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="c0e5d-106">Ознакомьтесь в документацией и определите, какую из процедур списания следует использовать.</span><span class="sxs-lookup"><span data-stu-id="c0e5d-106">Read the documentation and determine which decommissioning procedure to use.</span></span>

<span data-ttu-id="c0e5d-107">Для полного покрытия удаления серверов и ролей сервера Lync Server 2010 и пошагового руководства по списанию развертывания Lync Server 2010 обратитесь к разделу "удаление Microsoft Lync Server 2010 и удаление ролей сервера", которые можно скачать на сайте [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227) .</span><span class="sxs-lookup"><span data-stu-id="c0e5d-107">For exhaustive coverage of removing Lync Server 2010 servers and server roles, and a step-by-step guide to decommissioning a Lync Server 2010 deployment, see "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c0e5d-108">Сведения о переносе и обновлении приложений Microsoft Unified Communications Managed API (UCMA), предшествующих списанию устаревшей среды, приведены в разделе <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="c0e5d-108">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c0e5d-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="c0e5d-109">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="c0e5d-110">Обновление записей DNS SRV</span><span class="sxs-lookup"><span data-stu-id="c0e5d-110">Update DNS SRV records</span></span>](update-dns-srv-records.md)

  - <span></span>  
    [<span data-ttu-id="c0e5d-111">Перемещение сервера центрального управления Lync Server 2010 на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0e5d-111">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>](move-the-lync-server-2010-central-management-server-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="c0e5d-112">Перемещение каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="c0e5d-112">Move Conference Directories</span></span>](move-lync-server-2010-conference-directories-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="c0e5d-113">Удаление связи с сервером архивирования</span><span class="sxs-lookup"><span data-stu-id="c0e5d-113">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)

  - <span></span>  
    [<span data-ttu-id="c0e5d-114">Удаление связи с сервером мониторинга</span><span class="sxs-lookup"><span data-stu-id="c0e5d-114">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)

  - <span></span>  
    [<span data-ttu-id="c0e5d-115">Удаление сервера переднего плана Enterprise Edition или сервера переднего плана Standard Edition</span><span class="sxs-lookup"><span data-stu-id="c0e5d-115">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-enterprise-edition-front-end-server-or-standard-edition-front-end-server.md)

  - <span></span>  
    [<span data-ttu-id="c0e5d-116">Удаление экземпляров и баз данных SQL Server на внутреннем сервере</span><span class="sxs-lookup"><span data-stu-id="c0e5d-116">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

