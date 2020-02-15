---
title: Lync Server 2013 support Active Directory
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
ms.openlocfilehash: b3ded5de5500778559efe632c5272db50b0eadbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a><span data-ttu-id="ed7e9-102">Поддержка Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed7e9-102">Active Directory support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed7e9-103">_**Последнее изменение темы:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="ed7e9-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="ed7e9-104">Локальные топологии доменных служб Active Directory, поддерживаемые в Lync Server 2013, приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="ed7e9-104">The Active Directory Domain Services on-premises topologies that are supported by Lync Server 2013 are as follows:</span></span>

  - <span data-ttu-id="ed7e9-105">один лес с одним доменом;</span><span class="sxs-lookup"><span data-stu-id="ed7e9-105">Single forest with single domain</span></span>

  - <span data-ttu-id="ed7e9-106">один лес с одним деревом и несколькими доменами;</span><span class="sxs-lookup"><span data-stu-id="ed7e9-106">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="ed7e9-107">один лес с несколькими деревьями и несвязанными пространствами имен;</span><span class="sxs-lookup"><span data-stu-id="ed7e9-107">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="ed7e9-108">несколько лесов в топологии с центральным лесом;</span><span class="sxs-lookup"><span data-stu-id="ed7e9-108">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="ed7e9-109">несколько лесов в топологии с лесом ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ed7e9-109">Multiple forests in a resource forest topology</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ed7e9-110">Lync Server 2013 не поддерживает однокомпонентные домены.</span><span class="sxs-lookup"><span data-stu-id="ed7e9-110">Lync Server 2013 does not support single-label domains.</span></span> <span data-ttu-id="ed7e9-111">Например, лес с корневым доменом <STRONG>contoso.local</STRONG> поддерживается, а с однокомпонентным корневым доменом <STRONG>local</STRONG> — нет.</span><span class="sxs-lookup"><span data-stu-id="ed7e9-111">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a single-label root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="ed7e9-112">Дополнительные сведения см. в статье 300684 базы знаний Майкрософт "сведения о настройке Windows для доменов с DNS-именем, сопоставленными с <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>одной меткой" по адресу ".</span><span class="sxs-lookup"><span data-stu-id="ed7e9-112">For details, see Microsoft Knowledge Base article 300684, "Information about configuring Windows for domains with single-label DNS names," at <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ed7e9-113">Lync Server 2013 не поддерживает переименование доменов.</span><span class="sxs-lookup"><span data-stu-id="ed7e9-113">Lync Server 2013 does not support renaming domains.</span></span> <span data-ttu-id="ed7e9-114">Если требуется переименовать домен, на котором развернут Lync Server, сначала необходимо удалить Lync Server, затем переименовать домен, а затем переустановить Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed7e9-114">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

<span data-ttu-id="ed7e9-115">Подробные сведения о поддерживаемых топологиях и требованиях для локальных развертываний приведены в разделе [требования к доменным службам Active Directory, поддержке и топологий в Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="ed7e9-115">For details about supported topologies and requirements for on-premises deployments, see [Active Directory Domain Services requirements, support, and topologies in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

