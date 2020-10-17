---
title: Технические требования к Lync Server 2013 для IPv6
description: Lync Server 2013 технические требования для IPv6.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c54dfbdba56c45f19e7664db075331591c8e87cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559465"
---
# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="fff47-103">Технические требования для IPv6 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fff47-103">Technical requirements for IPv6 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fff47-104">_**Последнее изменение темы:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="fff47-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="fff47-105">Если вы планируете настроить Lync Server 2013 для IPv6, учитывайте следующие требования:</span><span class="sxs-lookup"><span data-stu-id="fff47-105">If you plan to configure Lync Server 2013 for IPv6, keep the following requirements in mind:</span></span>

  - <span data-ttu-id="fff47-106">Чтобы использовать IPv6-адреса с сервером Lync Server, необходимо создать записи DNS для записей, которые должны быть обнаружены и разрешены в IPv6-адресе.</span><span class="sxs-lookup"><span data-stu-id="fff47-106">To use IPv6 addresses with Lync Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="fff47-107">Служба DNS для IPv6 использует записи узла AAAA (quad-A).</span><span class="sxs-lookup"><span data-stu-id="fff47-107">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="fff47-108">Если в развертывании используются IPv4 и IPv6, лучше всего настроить и поддерживать записи A узла для IPv4 и записи AAAA для IPv6.</span><span class="sxs-lookup"><span data-stu-id="fff47-108">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="fff47-109">Даже если полностью переводите развертывание на IPv6, вам по-прежнему могут потребоваться записи DNS для IPv4 для внешних пользователей, которые все еще применяют IPv4.</span><span class="sxs-lookup"><span data-stu-id="fff47-109">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="fff47-110">Можно развернуть записи узла DNS для IPv6 перед началом использования IPv6.</span><span class="sxs-lookup"><span data-stu-id="fff47-110">You can deploy IPv6 DNS host records before you start using IPv6.</span></span> <span data-ttu-id="fff47-111">Если клиент или сервер не используют IPv6, запись не будет указываться.</span><span class="sxs-lookup"><span data-stu-id="fff47-111">If the client or server doesn't use IPv6, the record will not be referenced.</span></span> <span data-ttu-id="fff47-112">Технологии туннелирования будут принимать решение относительно того, какую запись следует использовать, в зависимости от конфигурации технологии туннелирования и политик.</span><span class="sxs-lookup"><span data-stu-id="fff47-112">Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>

  - <span data-ttu-id="fff47-113">Каждый адрес IPv6 обладает определенной областью.</span><span class="sxs-lookup"><span data-stu-id="fff47-113">Each IPv6 address has a scope.</span></span> <span data-ttu-id="fff47-114">Три области, которые можно использовать для адресации IPv6, это глобальные IPv6-адреса (аналогичные общедоступным IPv4-адресам), уникальные локальные адреса IPv6 (аналогичные диапазонам частных IPv4-адресов) и IPv6-адреса локальной связи (аналогично автоматическим частным IP-адресам в Windows Server для IPv4).</span><span class="sxs-lookup"><span data-stu-id="fff47-114">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="fff47-115">Всем серверам в пуле должны быть назначены адреса IPv6, относящиеся к одной и той же области.</span><span class="sxs-lookup"><span data-stu-id="fff47-115">All the servers within a pool should have IPv6 addresses with the same scope.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fff47-116">IPv6 — это сложная тема, которая требует тщательного планирования с вашей командой сети и поставщиком услуг Интернета, чтобы убедиться в том, что адреса, назначенные на уровне Windows Server и на уровне сервера Lync Server 2013, работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="fff47-116">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Lync Server 2013 level work as expected.</span></span> <span data-ttu-id="fff47-117">Для получения доступа к дополнительным ресурсам, содержащим информацию о планировании и адресации IPv6, воспользуйтесь ссылками, приведенными в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="fff47-117">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fff47-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fff47-118">See Also</span></span>


[<span data-ttu-id="fff47-119">Архитектура адресации протокола IP версии 6</span><span class="sxs-lookup"><span data-stu-id="fff47-119">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="fff47-120">Глобальный одноадресный формат IPv6</span><span class="sxs-lookup"><span data-stu-id="fff47-120">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="fff47-121">Уникальные локальные адреса одноадресной рассылки IPv6</span><span class="sxs-lookup"><span data-stu-id="fff47-121">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

