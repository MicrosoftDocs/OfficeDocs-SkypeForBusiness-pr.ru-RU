---
title: 'Lync Server 2013: планирование сертификатов пограничного сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faad6dba610df8033b75b0c87c52fbb065dc5dcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a><span data-ttu-id="5392b-102">Планирование сертификатов пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5392b-102">Plan for Edge Server certificates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5392b-103">_**Тема последнего изменения:** 2012-11-05_</span><span class="sxs-lookup"><span data-stu-id="5392b-103">_**Topic Last Modified:** 2012-11-05_</span></span>

<span data-ttu-id="5392b-104">Создание сертификатов для Edge упрощено в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5392b-104">Certificate creation for Edge is simplified in Lync Server 2013.</span></span>

<span data-ttu-id="5392b-105">**Блок-схема сертификации для пограничного сервера**</span><span class="sxs-lookup"><span data-stu-id="5392b-105">**Certificates Flow Chart for Edge Server**</span></span>

<span data-ttu-id="5392b-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span><span class="sxs-lookup"><span data-stu-id="5392b-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span></span>

<span data-ttu-id="5392b-107">Создание единого общедоступного сертификата убедитесь, что у вас есть закрытый ключ, определенный для этого сертификата, и назначьте его следующим внешним интерфейсам пограничного сервера с помощью мастера сертификатов.</span><span class="sxs-lookup"><span data-stu-id="5392b-107">Create a single public certificate, ensure that you have an exportable private key defined for the certificate, and assign it to the following Edge Server external interfaces using the certificate wizard:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5392b-108">Сертификаты с подстановочными знаками не поддерживаются в Lync Server, за исключением тех случаев, когда используются для суммирования простых URL-адресов с помощью обратного прокси.</span><span class="sxs-lookup"><span data-stu-id="5392b-108">Wildcard certificates are not supported in Lync Server, except where used to summarize the Simple URLs through the reverse proxy.</span></span> <span data-ttu-id="5392b-109">Для каждого доменного имени SIP, службы Edge для веб-конференций, службы Edge/V и КСМПП домена, предлагаемого вашим развертыванием, необходимо определить разные имена альтернативных субъектов (SAN).</span><span class="sxs-lookup"><span data-stu-id="5392b-109">You must define distinct subject alternate names (SANs) for each SIP domain name, Web Conferencing Edge service, A/V Edge service and XMPP domain offered by your deployment.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5392b-110">Впервые введены в Lync Server 2013, для хранения сертификатов проверки подлинности звука и видео в предварительной версии для текущего сертификата требуется дополнительное планирование.</span><span class="sxs-lookup"><span data-stu-id="5392b-110">Introduced in Lync Server 2013, staging Audio/Video Authentication certificates in advance of the expiration time of the current certificate requires some additional planning.</span></span> <span data-ttu-id="5392b-111">Вместо одного сертификата с несколькими целями доступа к внешнему интерфейсу Edge вам потребуется два сертификата, один из которых назначается службе Edge Access и служба Edge для веб-конференций, а также один сертификат для службы EDGE (/V).</span><span class="sxs-lookup"><span data-stu-id="5392b-111">Instead of one certificate with multiple purposes for the external Edge interface, you will require two certificates, one assigned to the Access Edge service and Web Conferencing Edge service, and one certificate for the A/V Edge service.</span></span> <span data-ttu-id="5392b-112">Дополнительные сведения можно найти в разделе " <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">промежуточный выпуск и сертификаты OAuth" в Lync Server 2013 с помощью Set-ксцертификате</A></span><span class="sxs-lookup"><span data-stu-id="5392b-112">For additional details, see <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</A></span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5392b-113">В случае с пулом пограничных серверов вы экспортируете сертификат с закрытым ключом на каждый пограничный сервер и назначаете этот сертификат для каждой службы пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5392b-113">In the event of a pool of Edge Servers, you export the certificate with the private key to each Edge Server and assign the certificate to each Edge Server service.</span></span> <span data-ttu-id="5392b-114">Сделайте то же самое для внутреннего сертификата пограничного сервера, экспортируйте сертификат с закрытым ключом и назначая каждый внутренний интерфейс EDGE.</span><span class="sxs-lookup"><span data-stu-id="5392b-114">Do the same for the internal Edge Server certificate, exporting the certificate with the private key and assigning to each internal Edge interface.</span></span>



</div>

  - <span data-ttu-id="5392b-115">Убедитесь, что у вас есть закрытый ключ, назначаемый для экспорта сертификата.</span><span class="sxs-lookup"><span data-stu-id="5392b-115">Ensure that you have an exportable private key assigned for the certificate</span></span>

  - <span data-ttu-id="5392b-116">Служба пограничного доступа (в мастере сертификатов), называемая **внешним доступом к SIP Edge**</span><span class="sxs-lookup"><span data-stu-id="5392b-116">Access Edge service (referred to as **SIP Access Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="5392b-117">Служба веб-конференций EDGE (в мастере сертификатов), называемая **внешними веб-Конференцией** .</span><span class="sxs-lookup"><span data-stu-id="5392b-117">Web Conferencing Edge service (referred to as **Web Conferencing Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="5392b-118">Служба проверки подлинности (/V) (в мастере сертификатов она ссылается на **внешний край** )</span><span class="sxs-lookup"><span data-stu-id="5392b-118">A/V Authentication service (referred to as **A/V Edge External** in the certificate wizard)</span></span>

<span data-ttu-id="5392b-119">Создайте единый внутренний сертификат с экспортируемым закрытым ключом, скопируйте и назначьте его каждому из внутренних интерфейсов пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5392b-119">Create a single internal certificate with exportable private key, copy and assign it to each of the Edge Server internal interfaces:</span></span>

  - <span data-ttu-id="5392b-120">Пограничный сервер (в мастере сертификатов называемый **внутренним краем** )</span><span class="sxs-lookup"><span data-stu-id="5392b-120">Edge Server (referred to as **Edge Internal** in the certificate wizard)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5392b-121">Для каждой службы пограничного сервера можно использовать отдельные сертификаты.</span><span class="sxs-lookup"><span data-stu-id="5392b-121">It is possible to use separate and distinct certificates for each Edge Server service.</span></span> <span data-ttu-id="5392b-122">Правильная причина выбора разных сертификатов — если вы хотите использовать новую функцию многопроходного сертификата для сертификата службы Edge.</span><span class="sxs-lookup"><span data-stu-id="5392b-122">A good reason to choose separate certificates is if you want to use the new rolling certificate feature for the A/V Edge service certificate.</span></span> <span data-ttu-id="5392b-123">В случае использования этой функции рекомендуется установить связь с сертификатом службы EDGE в службе пограничного доступа и веб-конференции с пограничным соединением.</span><span class="sxs-lookup"><span data-stu-id="5392b-123">In the case of this feature, decoupling the A/V Edge service certificate from the Access Edge service and Web Conferencing Edge service is recommended.</span></span> <span data-ttu-id="5392b-124">Если вы решите запросить, получить и назначить отдельные сертификаты для каждой службы, вы должны запросить разрешение экспорта закрытого ключа для службы Edge/V (опять же, это является службой проверки подлинности) и назначить один и тот же сертификат внешнему интерфейсу A/V на пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="5392b-124">If you choose to request, acquire and assign separate certificates for each service, you must request that the private key be exportable for the A/V Edge service (again, this is in actuality the A/V Authentication service) and assign the same certificate to the A/V Edge External interface on each Edge Server.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5392b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="5392b-125">See Also</span></span>


[<span data-ttu-id="5392b-126">Промежуточный выпуск и сертификаты OAuth в Lync Server 2013 с помощью Set-Ксцертификате</span><span class="sxs-lookup"><span data-stu-id="5392b-126">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[<span data-ttu-id="5392b-127">Изменения Lync Server 2013, затрагивающие планирование пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="5392b-127">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

