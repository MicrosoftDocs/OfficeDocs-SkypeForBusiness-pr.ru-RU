---
title: 'Lync Server 2013: поддержка Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd35b9444f0ede4abc9b66ab6b5513d049df57ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a><span data-ttu-id="a8dd7-102">Поддержка Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8dd7-102">Active Directory support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8dd7-103">_**Тема последнего изменения:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="a8dd7-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="a8dd7-104">Локальные топологии доменных служб Active Directory, поддерживаемые Lync Server 2013, описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="a8dd7-104">The Active Directory Domain Services on-premises topologies that are supported by Lync Server 2013 are as follows:</span></span>

  - <span data-ttu-id="a8dd7-105">Один лес с одним доменом</span><span class="sxs-lookup"><span data-stu-id="a8dd7-105">Single forest with single domain</span></span>

  - <span data-ttu-id="a8dd7-106">Один лес с одним деревом и несколькими доменами</span><span class="sxs-lookup"><span data-stu-id="a8dd7-106">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="a8dd7-107">Один лес с несколькими деревьями и несвязанными пространствами имен</span><span class="sxs-lookup"><span data-stu-id="a8dd7-107">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="a8dd7-108">Несколько лесов в топологии с центральным лесом</span><span class="sxs-lookup"><span data-stu-id="a8dd7-108">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="a8dd7-109">Несколько лесов в топологии с лесом ресурсов</span><span class="sxs-lookup"><span data-stu-id="a8dd7-109">Multiple forests in a resource forest topology</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8dd7-110">Lync Server 2013 не поддерживает домены с одной меткой.</span><span class="sxs-lookup"><span data-stu-id="a8dd7-110">Lync Server 2013 does not support single-label domains.</span></span> <span data-ttu-id="a8dd7-111">Например, лес с корневым доменом с именем <STRONG>contoso. local</STRONG> поддерживается, но не поддерживается корневой домен с именем <STRONG>Local</STRONG> в одной метке.</span><span class="sxs-lookup"><span data-stu-id="a8dd7-111">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a single-label root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="a8dd7-112">Подробные сведения о том, как настроить Windows для доменов с DNS-именами, сопоставленными с одной меткой, можно найти в статье <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>300684 в Microsoft Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="a8dd7-112">For details, see Microsoft Knowledge Base article 300684, "Information about configuring Windows for domains with single-label DNS names," at <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a8dd7-113">Lync Server 2013 не поддерживает переименование доменов.</span><span class="sxs-lookup"><span data-stu-id="a8dd7-113">Lync Server 2013 does not support renaming domains.</span></span> <span data-ttu-id="a8dd7-114">Если необходимо переименовать домен, на котором развернут сервер Lync Server, сначала необходимо удалить Lync Server, затем переименовать домен, а затем повторно установить Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a8dd7-114">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

<span data-ttu-id="a8dd7-115">Для получения подробных сведений о поддерживаемых топологиях и требованиях для локальных развертываний просмотрите [требования к доменным службам Active Directory, поддержку и топологии в Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="a8dd7-115">For details about supported topologies and requirements for on-premises deployments, see [Active Directory Domain Services requirements, support, and topologies in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

