---
title: 'Общие сведения о сертификате: SIP, Федерация КСМПП и общедоступная служба обмена мгновенными сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dccb46b9f2b6d934f1cd0960bb11a369fb585ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="7bbf4-102">Общие сведения о сертификате: SIP, Федерация КСМПП и общедоступная служба обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bbf4-102">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bbf4-103">_**Тема последнего изменения:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="7bbf4-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="7bbf4-104">Сертификаты, необходимые для Федерации с Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server, обычно удовлетворяют требованиям для настройки, запроса и назначения серверу пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="7bbf4-104">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="7bbf4-105">Требования к сертификатам для включения и установления связи с партнерами по протоколу расширенного обмена сообщениями (КСМПП) требуют добавления записей для доменов КСМПП.</span><span class="sxs-lookup"><span data-stu-id="7bbf4-105">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="7bbf4-106">Запись, включенная в сертификат в качестве дополнительного имени субъекта (SAN), будет являться доменом, который может принимать участие в КСМПП обмене сообщениями.</span><span class="sxs-lookup"><span data-stu-id="7bbf4-106">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="7bbf4-107">Домен может быть доменом корневого уровня (например, contoso.com), если вы хотите включить КСМПП для всего домена или выбрать его дочерние домены (например, corp.contoso.com, finance.contoso.com), если вы включаете КСМПП для подмножества пользователей.</span><span class="sxs-lookup"><span data-stu-id="7bbf4-107">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="7bbf4-108">Чтобы настроить сертификаты для общедоступной службы обмена мгновенными сообщениями, обратите внимание на то, что ничего не отличается от других типов Федерации SIP или даже стандартных сертификатов пограничного сервера, за исключением того, что для America Online (AOL) требуется сертификат или сертификаты (в корпус пограничного пула) также должен содержать клиентское EKU.</span><span class="sxs-lookup"><span data-stu-id="7bbf4-108">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="7bbf4-109">Клиентское EKU является дополнением к сертификату и является частью внешнего общедоступного сертификата, назначенного пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="7bbf4-109">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="7bbf4-110">Чтобы убедиться в том, что требования к сертификату для развертывания пограничного сервера выполнены правильно, ознакомьтесь с разделами, приведенными в разделе, озаглавленном **также**.</span><span class="sxs-lookup"><span data-stu-id="7bbf4-110">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

<div>



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7bbf4-111">Компонент</span><span class="sxs-lookup"><span data-stu-id="7bbf4-111">Component</span></span></th>
<th><span data-ttu-id="7bbf4-112">Имя субъекта</span><span class="sxs-lookup"><span data-stu-id="7bbf4-112">Subject name</span></span></th>
<th><span data-ttu-id="7bbf4-113">Дополнительные имена субъектов (SAN)</span><span class="sxs-lookup"><span data-stu-id="7bbf4-113">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="7bbf4-114">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7bbf4-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7bbf4-115">Внешний край и доступ</span><span class="sxs-lookup"><span data-stu-id="7bbf4-115">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="7bbf4-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7bbf4-116">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7bbf4-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7bbf4-117">sip.contoso.com</span></span></p>
<p><span data-ttu-id="7bbf4-118">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7bbf4-118">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="7bbf4-119">contoso.com</span><span class="sxs-lookup"><span data-stu-id="7bbf4-119">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="7bbf4-120">Поддержка пространства имен contoso.com КСМПП</span><span class="sxs-lookup"><span data-stu-id="7bbf4-120">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="7bbf4-121">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="7bbf4-121">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="7bbf4-122">Поддержка пространства имен SIP fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="7bbf4-122">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="7bbf4-123">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="7bbf4-123">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="7bbf4-124">Поддержка пространства имен fabrikam.com КСМПП</span><span class="sxs-lookup"><span data-stu-id="7bbf4-124">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="7bbf4-125">Сертификат должен находиться в общедоступном центре сертификации, а также в том случае, если вы разворачиваете общедоступную службу обмена мгновенными сообщениями с AOL, и у вас должен быть серверный EKU</span><span class="sxs-lookup"><span data-stu-id="7bbf4-125">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="7bbf4-126">Сертификат назначается внешним интерфейсам пограничного сервера для следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="7bbf4-126">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="7bbf4-127">доступа</span><span class="sxs-lookup"><span data-stu-id="7bbf4-127">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="7bbf4-128">веб-конференций</span><span class="sxs-lookup"><span data-stu-id="7bbf4-128">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="7bbf4-129">передачи аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="7bbf4-129">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="7bbf4-130">Технически сертификат не назначается для A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="7bbf4-130">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="7bbf4-131">Безопасная связь и проверка подлинности управляются службой проверки подлинности в Media Relay (МРАС).</span><span class="sxs-lookup"><span data-stu-id="7bbf4-131">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="7bbf4-132">МРАС использует сертификат, назначенный внутреннему интерфейсу пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="7bbf4-132">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="7bbf4-133">Обратите внимание, что сети SAN автоматически добавляются к сертификату на основе определений в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="7bbf4-133">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="7bbf4-134">Вы добавляете записи SAN по мере необходимости для дополнительных доменов SIP и других элементов, которые необходимо поддерживать.</span><span class="sxs-lookup"><span data-stu-id="7bbf4-134">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="7bbf4-135">Имя субъекта реплицируется в сети SAN и должно быть представлено для правильной работы.</span><span class="sxs-lookup"><span data-stu-id="7bbf4-135">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7bbf4-136">См. также</span><span class="sxs-lookup"><span data-stu-id="7bbf4-136">See Also</span></span>


[<span data-ttu-id="7bbf4-137">Пример конфигурации XMPP в Lync Server 2013 — федерация XMPP с Google Talk</span><span class="sxs-lookup"><span data-stu-id="7bbf4-137">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="7bbf4-138">Планирование сертификатов пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bbf4-138">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="7bbf4-139">Сводка по сертификатам — единая консолидированная пограничная топология с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bbf4-139">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="7bbf4-140">Сводка по сертификатам — единая консолидированная пограничная топология с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bbf4-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="7bbf4-141">Сводка по сертификатам — масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bbf4-141">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="7bbf4-142">Сводка по сертификатам — масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bbf4-142">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="7bbf4-143">Сводка по сертификатам — масштабируемая консолидированная пограничная топология с аппаратными балансировщиками нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bbf4-143">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

