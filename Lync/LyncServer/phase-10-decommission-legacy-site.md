---
title: 'Этап 10: списание устаревшего сайта'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8110d41e5f6436bfdbecc64fe07d514b5d0538ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="71683-102">Этап 10: списание устаревшего сайта</span><span class="sxs-lookup"><span data-stu-id="71683-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71683-103">_**Тема последнего изменения:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="71683-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="71683-104">В следующих разделах приведены рекомендации по удалению пулов и отключению серверов и пулов из устаревшего развертывания Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="71683-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="71683-105">Не все процедуры, перечисленные в этом разделе, являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="71683-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="71683-106">Ознакомьтесь со сведениями в каждом из этих разделов, чтобы определить, какую процедуру списания следует использовать.</span><span class="sxs-lookup"><span data-stu-id="71683-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="71683-107">Если вы импортировали каталоги конференций для конференц-связи с телефонным подключением на Lync Server 2013, важно перейти в каталог конференции на Lync Server 2013, прежде чем приступить к списанию пулов.</span><span class="sxs-lookup"><span data-stu-id="71683-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="71683-108">Если вы списать пул без предварительного перехода в каталог конференц-связи, функция телефонного подключения для всех перенесенных собраний перестанет работать.</span><span class="sxs-lookup"><span data-stu-id="71683-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="71683-109">Вы должны выполнить шаг для смены владельца для каждой из каталогов конференции в пуле старого.</span><span class="sxs-lookup"><span data-stu-id="71683-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="71683-110">Сведения о переносе и обновлении приложений для управляемых API Microsoft Unified Communications (УКМА) перед списанием устаревшей среды можно найти в разделе<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="71683-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="71683-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="71683-111">In This Section</span></span>

  - [<span data-ttu-id="71683-112">Перемещение каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="71683-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="71683-113">Обновление записей DNS SRV</span><span class="sxs-lookup"><span data-stu-id="71683-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="71683-114">Списание серверов и групп</span><span class="sxs-lookup"><span data-stu-id="71683-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="71683-115">Удалить Бакккомпатсите</span><span class="sxs-lookup"><span data-stu-id="71683-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

