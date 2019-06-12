---
title: 'Lync Server 2013: технические требования к IPv6'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972b59ba2ea01f967d5cfb8a7767a4f322bcb2fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="b7dbf-102">Технические требования к IPv6 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7dbf-102">Technical requirements for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7dbf-103">_**Тема последнего изменения:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="b7dbf-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="b7dbf-104">Если вы планируете настроить Lync Server 2013 для IPv6, учитывайте указанные ниже требования.</span><span class="sxs-lookup"><span data-stu-id="b7dbf-104">If you plan to configure Lync Server 2013 for IPv6, keep the following requirements in mind:</span></span>

  - <span data-ttu-id="b7dbf-105">Чтобы использовать IPv6-адреса в Lync Server, вам нужно создать записи DNS для записей, которые должны быть обнаружены и разрешены в IPv6-адресе.</span><span class="sxs-lookup"><span data-stu-id="b7dbf-105">To use IPv6 addresses with Lync Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="b7dbf-106">Служба DNS для IPv6 использует записи узла AAAA (quad-A).</span><span class="sxs-lookup"><span data-stu-id="b7dbf-106">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="b7dbf-107">Если в развертывании используются IPv4 и IPv6, лучше всего настроить и поддерживать записи A узла для IPv4 и записи AAAA для IPv6.</span><span class="sxs-lookup"><span data-stu-id="b7dbf-107">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="b7dbf-108">Даже если полностью переводите развертывание на IPv6, вам по-прежнему могут потребоваться записи DNS для IPv4 для внешних пользователей, которые все еще применяют IPv4.</span><span class="sxs-lookup"><span data-stu-id="b7dbf-108">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="b7dbf-p102">Можно развернуть записи узла DNS для IPv6 перед началом использования IPv6. Если клиент или сервер не используют IPv6, запись не будет указываться. Технологии туннелирования будут принимать решение относительно того, какую запись следует использовать, в зависимости от конфигурации технологии туннелирования и политик.</span><span class="sxs-lookup"><span data-stu-id="b7dbf-p102">You can deploy IPv6 DNS host records before you start using IPv6. If the client or server doesn't use IPv6, the record will not be referenced. Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>

  - <span data-ttu-id="b7dbf-112">Каждый адрес IPv6 обладает определенной областью.</span><span class="sxs-lookup"><span data-stu-id="b7dbf-112">Each IPv6 address has a scope.</span></span> <span data-ttu-id="b7dbf-113">Три области, которые можно использовать для адресации IPv6, — это глобальные адреса IPv6 (такие как общедоступные IPv4-адреса), уникальные локальные адреса IPv6 (аналогичные диапазонам частных IPv4-адресов) и локальные адреса IPv6 (аналогично автоматическим частным Windows Server для IPv4).</span><span class="sxs-lookup"><span data-stu-id="b7dbf-113">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="b7dbf-114">Всем серверам в пуле должны быть назначены адреса IPv6, относящиеся к одной и той же области.</span><span class="sxs-lookup"><span data-stu-id="b7dbf-114">All the servers within a pool should have IPv6 addresses with the same scope.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b7dbf-115">Протокол IPv6 — это сложная тема, требующая тщательного планирования с помощью сетевой команды и поставщика услуг Интернета, чтобы убедиться в том, что адреса, назначенные на уровне Windows Server и на уровне Lync Server 2013, работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="b7dbf-115">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Lync Server 2013 level work as expected.</span></span> <span data-ttu-id="b7dbf-116">Для получения доступа к дополнительным ресурсам, содержащим информацию о планировании и адресации IPv6, воспользуйтесь ссылками, приведенными в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="b7dbf-116">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b7dbf-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b7dbf-117">See Also</span></span>


[<span data-ttu-id="b7dbf-118">Архитектура адресации протокола IP версии 6</span><span class="sxs-lookup"><span data-stu-id="b7dbf-118">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="b7dbf-119">Формат адреса глобального одноадресной рассылки IPv6</span><span class="sxs-lookup"><span data-stu-id="b7dbf-119">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="b7dbf-120">Уникальные локальные адреса одноадресной рассылки IPv6</span><span class="sxs-lookup"><span data-stu-id="b7dbf-120">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

