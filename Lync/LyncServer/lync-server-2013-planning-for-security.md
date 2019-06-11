---
title: 'Lync Server 2013: планирование безопасности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for security
ms:assetid: 17eeba87-cafa-4e9b-852d-c017a7d10d59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342827(v=OCS.15)
ms:contentKeyID: 56107267
ms.date: 06/22/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72563df128f86ae7d52d850dbe015e33c1552eed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-security-in-lync-server-2013"></a><span data-ttu-id="fc59d-102">Планирование безопасности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc59d-102">Planning for security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc59d-103">_**Тема последнего изменения:** 2016-06-22_</span><span class="sxs-lookup"><span data-stu-id="fc59d-103">_**Topic Last Modified:** 2016-06-22_</span></span>

<span data-ttu-id="fc59d-104">Этот раздел безопасности используется для оценки угроз безопасности развертывания Lync Server 2013 и управления ими.</span><span class="sxs-lookup"><span data-stu-id="fc59d-104">Use this security section to assess and manage security risks to your deployment of Lync Server 2013.</span></span>

<span data-ttu-id="fc59d-105">Даже если вы размещаете развертывание Lync Server 2013, возможно, у вас есть компоненты вашей сети, у которых есть своя документация по безопасности.</span><span class="sxs-lookup"><span data-stu-id="fc59d-105">Even if your Lync Server 2013 deployment is modest, you probably have components in your network that have their own security documentation.</span></span> <span data-ttu-id="fc59d-106">Таким образом, маловероятно, что в этом разделе описаны все аспекты безопасности для всех компонентов и областей, которые связаны с вашим развертыванием.</span><span class="sxs-lookup"><span data-stu-id="fc59d-106">Therefore, it is unlikely that this section covers all aspects of security for all components and areas that are pertinent to your deployment.</span></span>

<span data-ttu-id="fc59d-107">Используйте этот раздел в качестве отправной точки, чтобы устранить безопасность развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fc59d-107">Use this section as a starting point to address the security of your Lync Server 2013 deployment.</span></span> <span data-ttu-id="fc59d-108">Он содержит общие рекомендации и рекомендации по оценке и управлению наиболее распространенными угрозами безопасности.</span><span class="sxs-lookup"><span data-stu-id="fc59d-108">It provides general guidelines and best practices for assessing and managing the most common security risks.</span></span> <span data-ttu-id="fc59d-109">Дополнительные ресурсы о продукте и безопасности перечислены в конце каждой темы.</span><span class="sxs-lookup"><span data-stu-id="fc59d-109">Additional product and security resources are listed at the end of each topic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fc59d-110">Безопасность — это постоянно развивающаяся тема.</span><span class="sxs-lookup"><span data-stu-id="fc59d-110">Security is a constantly evolving topic.</span></span> <span data-ttu-id="fc59d-111">По мере возникновения новых угроз и решений старые документы, решения, методы и процедуры должны быть заменены на обновленный материал.</span><span class="sxs-lookup"><span data-stu-id="fc59d-111">As new threats and solutions arise, outdated documents, solutions, methods, and procedures should be replaced with up-to-date material.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fc59d-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="fc59d-112">In This Section</span></span>

  - [<span data-ttu-id="fc59d-113">Основные функции безопасности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc59d-113">Key security features in Lync Server 2013</span></span>](lync-server-2013-key-security-features.md)

  - [<span data-ttu-id="fc59d-114">Распространенные угрозы безопасности в современных повседневных системах</span><span class="sxs-lookup"><span data-stu-id="fc59d-114">Common security threats in modern day computing</span></span>](lync-server-2013-common-security-threats-in-modern-day-computing.md)

  - [<span data-ttu-id="fc59d-115">Исключения из антивирусной проверки для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc59d-115">Antivirus scanning exclusions for Lync Server 2013</span></span>](lync-server-2013-antivirus-scanning-exclusions.md)

  - [<span data-ttu-id="fc59d-116">Платформа безопасности для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc59d-116">Security framework for Lync Server 2013</span></span>](lync-server-2013-security-framework-for-lync-server.md)

  - [<span data-ttu-id="fc59d-117">Устранение угроз для базовой инфраструктуры для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc59d-117">Addressing threats to your core infrastructure for Lync Server 2013</span></span>](lync-server-2013-addressing-threats-to-your-core-infrastructure.md)

  - [<span data-ttu-id="fc59d-118">Развертывание нестандартного порта SQL Server и псевдонима в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc59d-118">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>](deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

