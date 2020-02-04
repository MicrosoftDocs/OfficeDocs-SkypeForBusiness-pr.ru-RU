---
title: 'Этап 8: ликвидация старых пулов'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 8: Decommission legacy pools'
ms:assetid: 1c68e5d8-fb5f-45e6-b6e3-27f5e830c966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204724(v=OCS.15)
ms:contentKeyID: 48183557
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9c21aa29f2e98aacd3ec68076a21ba2b4d2a76e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="d710a-102">Этап 8: ликвидация старых пулов</span><span class="sxs-lookup"><span data-stu-id="d710a-102">Phase 8: Decommission legacy pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d710a-103">_**Тема последнего изменения:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="d710a-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="d710a-104">В следующих разделах приведены рекомендации по обновлению записей DNS, перемещению сервера управления контентом, удалении пулов и отключению серверов и пулов из устаревшего развертывания Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d710a-104">The following topic provides guidance in updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Lync Server 2010.</span></span> <span data-ttu-id="d710a-105">Не все процедуры, перечисленные в этом разделе, являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="d710a-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="d710a-106">Ознакомьтесь с документацией и определите, какую процедуру списания использовать.</span><span class="sxs-lookup"><span data-stu-id="d710a-106">Read the documentation and determine which decommissioning procedure to use.</span></span>

<span data-ttu-id="d710a-107">Для полного покрытия удаления серверов и ролей сервера Lync Server 2010 и пошагового руководства по списанию развертывания Lync Server 2010 ознакомьтесь со статьей удаление Microsoft Lync Server 2010 и отключение ролей сервера, которые можно скачать по адресу [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span><span class="sxs-lookup"><span data-stu-id="d710a-107">For exhaustive coverage of removing Lync Server 2010 servers and server roles, and a step-by-step guide to decommissioning a Lync Server 2010 deployment, see "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d710a-108">Сведения о переносе и обновлении приложений для управляемых API Microsoft Unified Communications (УКМА) перед списанием устаревшей среды можно найти в разделе<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="d710a-108">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d710a-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="d710a-109">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="d710a-110">Обновление записей DNS SRV</span><span class="sxs-lookup"><span data-stu-id="d710a-110">Update DNS SRV records</span></span>](update-dns-srv-records.md)

  - <span></span>  
    [<span data-ttu-id="d710a-111">Перемещение сервера Lync Server 2010 на центральный сервер SMS на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d710a-111">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>](move-the-lync-server-2010-central-management-server-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="d710a-112">Перемещение каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="d710a-112">Move Conference Directories</span></span>](move-lync-server-2010-conference-directories-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="d710a-113">Удаление связи с сервером архивирования</span><span class="sxs-lookup"><span data-stu-id="d710a-113">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)

  - <span></span>  
    [<span data-ttu-id="d710a-114">Удаление связи с сервером мониторинга</span><span class="sxs-lookup"><span data-stu-id="d710a-114">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)

  - <span></span>  
    [<span data-ttu-id="d710a-115">Удаление сервера переднего плана Enterprise Edition или стандартного выпуска Standard Edition</span><span class="sxs-lookup"><span data-stu-id="d710a-115">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-enterprise-edition-front-end-server-or-standard-edition-front-end-server.md)

  - <span></span>  
    [<span data-ttu-id="d710a-116">Удаление экземпляров и баз данных SQL Server на внутреннем сервере</span><span class="sxs-lookup"><span data-stu-id="d710a-116">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

