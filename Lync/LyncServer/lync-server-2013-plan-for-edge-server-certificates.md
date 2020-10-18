---
title: 'Lync Server 2013: Планирование сертификатов пограничного сервера'
description: 'Lync Server 2013: Планирование сертификатов пограничного сервера.'
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
ms.openlocfilehash: 22ec3743256fe3e4c55dba0f6357a85b1ad81cd0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578195"
---
# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a><span data-ttu-id="04f6e-103">Планирование сертификатов пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04f6e-103">Plan for Edge Server certificates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04f6e-104">_**Последнее изменение темы:** 2012-11-05_</span><span class="sxs-lookup"><span data-stu-id="04f6e-104">_**Topic Last Modified:** 2012-11-05_</span></span>

<span data-ttu-id="04f6e-105">Создание сертификатов для Edge упрощено в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="04f6e-105">Certificate creation for Edge is simplified in Lync Server 2013.</span></span>

<span data-ttu-id="04f6e-106">**Сертификаты для пограничного сервера (блок-схема)**</span><span class="sxs-lookup"><span data-stu-id="04f6e-106">**Certificates Flow Chart for Edge Server**</span></span>

<span data-ttu-id="04f6e-107">![a5fc20db — 7ced – 4364 — b577 – 6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db — 7ced – 4364 — b577 – 6a709a8367cd")</span><span class="sxs-lookup"><span data-stu-id="04f6e-107">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span></span>

<span data-ttu-id="04f6e-108">Создайте единый общий сертификат, убедитесь в наличии экспортируемого частного ключа, определенного для сертификата, и назначьте его следующим внешним интерфейсам пограничного сервера с помощью мастера сертификатов:</span><span class="sxs-lookup"><span data-stu-id="04f6e-108">Create a single public certificate, ensure that you have an exportable private key defined for the certificate, and assign it to the following Edge Server external interfaces using the certificate wizard:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="04f6e-109">Сертификаты с подстановочными знаками не поддерживаются в Lync Server, за исключением случаев, где используется для суммирования простых URL-адресов через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="04f6e-109">Wildcard certificates are not supported in Lync Server, except where used to summarize the Simple URLs through the reverse proxy.</span></span> <span data-ttu-id="04f6e-110">Необходимо определить разные альтернативные имена субъектов (SAN) для каждого имени домена SIP, пограничной службы веб-конференций, пограничной службы аудио-и видеоданных и домена XMPP, предлагаемого развертыванием.</span><span class="sxs-lookup"><span data-stu-id="04f6e-110">You must define distinct subject alternate names (SANs) for each SIP domain name, Web Conferencing Edge service, A/V Edge service and XMPP domain offered by your deployment.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="04f6e-111">В Lync Server 2013 сертификаты проверки подлинности для промежуточного хранения аудио-и видеоданных в течение срока действия текущего сертификата требуют дополнительного планирования.</span><span class="sxs-lookup"><span data-stu-id="04f6e-111">Introduced in Lync Server 2013, staging Audio/Video Authentication certificates in advance of the expiration time of the current certificate requires some additional planning.</span></span> <span data-ttu-id="04f6e-112">Вместо одного сертификата с несколькими целями для внешнего пограничного интерфейса потребуется два сертификата, один из которых назначен службе пограничного сервера доступа и пограничной службе веб-конференций и один сертификат для пограничной службы аудио-и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="04f6e-112">Instead of one certificate with multiple purposes for the external Edge interface, you will require two certificates, one assigned to the Access Edge service and Web Conferencing Edge service, and one certificate for the A/V Edge service.</span></span> <span data-ttu-id="04f6e-113">Дополнительные сведения см. <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">промежуточные сертификаты протокола AV и OAuth в Lync Server 2013 using in Set — CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="04f6e-113">For additional details, see <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</A></span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="04f6e-114">В случае с пулом пограничных серверов вы экспортируете сертификат с закрытым ключом на каждый пограничный сервер и назначаете сертификат каждой службе пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="04f6e-114">In the event of a pool of Edge Servers, you export the certificate with the private key to each Edge Server and assign the certificate to each Edge Server service.</span></span> <span data-ttu-id="04f6e-115">Сделайте то же самое для внутреннего сертификата пограничного сервера, экспортируйте сертификат с закрытым ключом и присвойте каждому внутреннему интерфейсу пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="04f6e-115">Do the same for the internal Edge Server certificate, exporting the certificate with the private key and assigning to each internal Edge interface.</span></span>



</div>

  - <span data-ttu-id="04f6e-116">Убедитесь в наличии экспортируемого частного ключа, назначенного сертификату</span><span class="sxs-lookup"><span data-stu-id="04f6e-116">Ensure that you have an exportable private key assigned for the certificate</span></span>

  - <span data-ttu-id="04f6e-117">Пограничная служба доступа (в мастере сертификатов называется **внешним пограничным сервером доступа SIP** )</span><span class="sxs-lookup"><span data-stu-id="04f6e-117">Access Edge service (referred to as **SIP Access Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="04f6e-118">Пограничная служба веб-конференций (в мастере сертификатов называется **внешним пограничным сервером веб-конференций** )</span><span class="sxs-lookup"><span data-stu-id="04f6e-118">Web Conferencing Edge service (referred to as **Web Conferencing Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="04f6e-119">Служба проверки подлинности аудио/видео (в мастере сертификатов называется **внешней пограничной службой аудио/видео**)</span><span class="sxs-lookup"><span data-stu-id="04f6e-119">A/V Authentication service (referred to as **A/V Edge External** in the certificate wizard)</span></span>

<span data-ttu-id="04f6e-120">Создайте единый внутренний сертификат с экспортируемым закрытым ключом, скопируйте его и назначьте каждому внутреннему интерфейсу пограничного сервера:</span><span class="sxs-lookup"><span data-stu-id="04f6e-120">Create a single internal certificate with exportable private key, copy and assign it to each of the Edge Server internal interfaces:</span></span>

  - <span data-ttu-id="04f6e-121">Пограничный сервер (в мастере сертификатов называется **внутренним пограничным сервером**)</span><span class="sxs-lookup"><span data-stu-id="04f6e-121">Edge Server (referred to as **Edge Internal** in the certificate wizard)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="04f6e-122">Можно использовать отдельные и разные сертификаты для каждой службы пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="04f6e-122">It is possible to use separate and distinct certificates for each Edge Server service.</span></span> <span data-ttu-id="04f6e-123">Если вы хотите использовать новую функцию последовательного сертификата для сертификата пограничной службы аудио-и видеосвязи, рекомендуется выбрать отдельные сертификаты.</span><span class="sxs-lookup"><span data-stu-id="04f6e-123">A good reason to choose separate certificates is if you want to use the new rolling certificate feature for the A/V Edge service certificate.</span></span> <span data-ttu-id="04f6e-124">В этом случае рекомендуется отменять пограничный сертификат службы аудио-и видеоданных из службы пограничной службы доступа и пограничной службы веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="04f6e-124">In the case of this feature, decoupling the A/V Edge service certificate from the Access Edge service and Web Conferencing Edge service is recommended.</span></span> <span data-ttu-id="04f6e-125">Если вы решили запросить, присвоить и назначить отдельные сертификаты для каждой службы, необходимо запросить возможность экспорта закрытого ключа для пограничной службы аудио-и видеоданных (опять же, это на самом деле это служба проверки подлинности a/V) и назначить один сертификат внешнему интерфейсу пограничного сервера аудио-и видеоданных на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="04f6e-125">If you choose to request, acquire and assign separate certificates for each service, you must request that the private key be exportable for the A/V Edge service (again, this is in actuality the A/V Authentication service) and assign the same certificate to the A/V Edge External interface on each Edge Server.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="04f6e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="04f6e-126">See Also</span></span>


[<span data-ttu-id="04f6e-127">Промежуточные сертификаты AV и OAuth в Lync Server 2013 using in Set — CsCertificate</span><span class="sxs-lookup"><span data-stu-id="04f6e-127">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[<span data-ttu-id="04f6e-128">Изменения в Lync Server 2013, затрагивающие планирование пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="04f6e-128">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

