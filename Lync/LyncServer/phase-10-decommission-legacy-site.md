---
title: 'Этап 10: списание устаревшего сайта'
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d40c988822a27a34f148e4e1e7893a077965fcd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="41f03-102">Этап 10: списание устаревшего сайта</span><span class="sxs-lookup"><span data-stu-id="41f03-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41f03-103">_**Последнее изменение темы:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="41f03-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="41f03-104">В следующих разделах представлены рекомендации по списанию пулов, а также отключению и удалению серверов и пулов из устаревшего развертывания Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="41f03-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="41f03-105">Не требуется выполнять все процедуры, представленные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="41f03-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="41f03-106">Изучите информацию, представленную в каждом из разделов, чтобы определить, какие процедуры вывода из эксплуатации следует использовать.</span><span class="sxs-lookup"><span data-stu-id="41f03-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="41f03-107">Если вы импортировали каталоги конференций для конференц-связи с телефонным подключением в Lync Server 2013, перед началом списания пулов важно перевести его в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41f03-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="41f03-108">Если вы выводите пул из эксплуатации без предварительного переноса права владения, функция телефонного подключения для всех перенесенных собраний больше не будет работать.</span><span class="sxs-lookup"><span data-stu-id="41f03-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="41f03-109">Необходимо выполнять процедуру переноса прав владения однократно для каждого каталога конференц-связи в устаревшем пуле.</span><span class="sxs-lookup"><span data-stu-id="41f03-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="41f03-110">Сведения о переносе и обновлении приложений Microsoft Unified Communications Managed API (UCMA), предшествующих списанию устаревшей среды, приведены в разделе<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="41f03-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="41f03-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="41f03-111">In This Section</span></span>

  - [<span data-ttu-id="41f03-112">Перемещение каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="41f03-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="41f03-113">Обновление записей DNS SRV</span><span class="sxs-lookup"><span data-stu-id="41f03-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="41f03-114">Списание серверов и пулов</span><span class="sxs-lookup"><span data-stu-id="41f03-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="41f03-115">Удаление BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="41f03-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

