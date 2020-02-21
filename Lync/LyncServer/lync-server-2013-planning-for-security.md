---
title: 'Lync Server 2013: планирование безопасности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for security
ms:assetid: 17eeba87-cafa-4e9b-852d-c017a7d10d59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342827(v=OCS.15)
ms:contentKeyID: 56107267
ms.date: 06/22/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db9ec867032875484c6bab3db3c433716fa7c889
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-security-in-lync-server-2013"></a><span data-ttu-id="df7c7-102">Планирование безопасности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7c7-102">Planning for security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df7c7-103">_**Последнее изменение темы:** 2016-06-22_</span><span class="sxs-lookup"><span data-stu-id="df7c7-103">_**Topic Last Modified:** 2016-06-22_</span></span>

<span data-ttu-id="df7c7-104">Этот раздел безопасности используется для оценки угроз безопасности развертывания Lync Server 2013 и управления ими.</span><span class="sxs-lookup"><span data-stu-id="df7c7-104">Use this security section to assess and manage security risks to your deployment of Lync Server 2013.</span></span>

<span data-ttu-id="df7c7-105">Даже если развертывание Lync Server 2013 практически не требуется, у вас могут быть компоненты в вашей сети, у которых есть собственная документация по безопасности.</span><span class="sxs-lookup"><span data-stu-id="df7c7-105">Even if your Lync Server 2013 deployment is modest, you probably have components in your network that have their own security documentation.</span></span> <span data-ttu-id="df7c7-106">Таким образом, маловероятно, что в этом разделе рассматриваются все аспекты безопасности для всех компонентов и областей, которые относятся к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="df7c7-106">Therefore, it is unlikely that this section covers all aspects of security for all components and areas that are pertinent to your deployment.</span></span>

<span data-ttu-id="df7c7-107">Используйте этот раздел в качестве отправной точки, чтобы решить безопасность развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df7c7-107">Use this section as a starting point to address the security of your Lync Server 2013 deployment.</span></span> <span data-ttu-id="df7c7-108">В нем представлены общие рекомендации и рекомендации по оценке и управлению наиболее распространенными угрозами безопасности.</span><span class="sxs-lookup"><span data-stu-id="df7c7-108">It provides general guidelines and best practices for assessing and managing the most common security risks.</span></span> <span data-ttu-id="df7c7-109">Дополнительные ресурсы по продукту и безопасности перечислены в конце каждого раздела.</span><span class="sxs-lookup"><span data-stu-id="df7c7-109">Additional product and security resources are listed at the end of each topic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="df7c7-110">Безопасность — это постоянно развивающийся раздел.</span><span class="sxs-lookup"><span data-stu-id="df7c7-110">Security is a constantly evolving topic.</span></span> <span data-ttu-id="df7c7-111">По мере возникновения новых угроз и решений устаревшие документы, решения, методы и процедуры следует заменять на обновленный материал.</span><span class="sxs-lookup"><span data-stu-id="df7c7-111">As new threats and solutions arise, outdated documents, solutions, methods, and procedures should be replaced with up-to-date material.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="df7c7-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="df7c7-112">In This Section</span></span>

  - [<span data-ttu-id="df7c7-113">Ключевые функции безопасности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7c7-113">Key security features in Lync Server 2013</span></span>](lync-server-2013-key-security-features.md)

  - [<span data-ttu-id="df7c7-114">Распространенные угрозы безопасности в современных повседневных вычислениях</span><span class="sxs-lookup"><span data-stu-id="df7c7-114">Common security threats in modern day computing</span></span>](lync-server-2013-common-security-threats-in-modern-day-computing.md)

  - [<span data-ttu-id="df7c7-115">Исключения антивирусной проверки для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7c7-115">Antivirus scanning exclusions for Lync Server 2013</span></span>](lync-server-2013-antivirus-scanning-exclusions.md)

  - [<span data-ttu-id="df7c7-116">Инфраструктура безопасности для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7c7-116">Security framework for Lync Server 2013</span></span>](lync-server-2013-security-framework-for-lync-server.md)

  - [<span data-ttu-id="df7c7-117">Устранение угроз для основной инфраструктуры для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7c7-117">Addressing threats to your core infrastructure for Lync Server 2013</span></span>](lync-server-2013-addressing-threats-to-your-core-infrastructure.md)

  - [<span data-ttu-id="df7c7-118">Развертывание нестандартного порта и псевдонима SQL Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7c7-118">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>](deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

