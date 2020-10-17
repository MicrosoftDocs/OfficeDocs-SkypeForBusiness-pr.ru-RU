---
title: 'Сводка по сертификатам: SIP, Федерация XMPP и общедоступная служба обмена мгновенными сообщениями'
description: 'Сводка по сертификатам: SIP, Федерация XMPP и общедоступные мгновенные сообщения.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 565d3b935d304aa09588688bd8d71948b1b3ec3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572145"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="3f030-103">Сводка по сертификатам: SIP, Федерация XMPP и общедоступные службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f030-103">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f030-104">_**Последнее изменение темы:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="3f030-104">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="3f030-105">Сертификаты, которые необходимы для Федерации с Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server, обычно соответствуют сертификатам, которые вы настраиваете, запрашиваете и назначаете пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="3f030-105">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="3f030-106">Требования к сертификатам для поддержки и установления связи с партнерами по протоколу XMPP (Extensible Messaging and Presence Protocol) требуют добавления записей для доменов XMPP.</span><span class="sxs-lookup"><span data-stu-id="3f030-106">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="3f030-107">Запись, включаемая в сертификат в виде альтернативного имени субъекта (SAN), содержит имя домена, который может участвовать в обмене данными по протоколу XMPP.</span><span class="sxs-lookup"><span data-stu-id="3f030-107">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="3f030-108">Домен может представлять собой домен корневого уровня (например, contoso.com), если вы хотите включить протокол XMPP для всего домена, или набор дочерних доменов (например, corp.contoso.com, finance.contoso.com), если включаете протокол XMPP для подмножества пользователей.</span><span class="sxs-lookup"><span data-stu-id="3f030-108">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="3f030-109">Чтобы настроить сертификаты для подключения к общедоступным службам обмена мгновенными сообщениями, обратите внимание на то, что ничто не отличается от других типов Федерации SIP или даже стандартных сертификатов пограничного сервера, за исключением того, что в America Online (AOL) требуется, чтобы сертификат или сертификаты (в случае пограничного пула) также содержали клиентское EKU.</span><span class="sxs-lookup"><span data-stu-id="3f030-109">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="3f030-110">Клиентское EKU является дополнением к сертификату и является частью внешнего общедоступного сертификата, назначенного пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="3f030-110">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="3f030-111">Чтобы убедиться в том, что соблюдены правильные требования к сертификатам для развертывания пограничного сервера, ознакомьтесь со статьями, приведенными в разделе, озаглавленном **также**.</span><span class="sxs-lookup"><span data-stu-id="3f030-111">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

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
<th><span data-ttu-id="3f030-112">Компонент</span><span class="sxs-lookup"><span data-stu-id="3f030-112">Component</span></span></th>
<th><span data-ttu-id="3f030-113">Имя субъекта</span><span class="sxs-lookup"><span data-stu-id="3f030-113">Subject name</span></span></th>
<th><span data-ttu-id="3f030-114">Альтернативные имена субъектов</span><span class="sxs-lookup"><span data-stu-id="3f030-114">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="3f030-115">Comments</span><span class="sxs-lookup"><span data-stu-id="3f030-115">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f030-116">Внешний/пограничный доступ</span><span class="sxs-lookup"><span data-stu-id="3f030-116">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="3f030-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3f030-117">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3f030-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3f030-118">sip.contoso.com</span></span></p>
<p><span data-ttu-id="3f030-119">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3f030-119">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="3f030-120">contoso.com</span><span class="sxs-lookup"><span data-stu-id="3f030-120">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="3f030-121">Поддержка пространства имен contoso.com XMPP</span><span class="sxs-lookup"><span data-stu-id="3f030-121">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="3f030-122">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3f030-122">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="3f030-123">Поддержка пространства имен SIP fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3f030-123">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="3f030-124">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3f030-124">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="3f030-125">Поддержка пространства имен fabrikam.com XMPP</span><span class="sxs-lookup"><span data-stu-id="3f030-125">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="3f030-126">Сертификат должен относиться к общедоступному центру сертификации и иметь EKU для сервера и клиента, если необходимо развернуть общедоступную службу обмена мгновенными сообщениями с AOL.</span><span class="sxs-lookup"><span data-stu-id="3f030-126">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="3f030-127">Сертификат назначается интерфейсам внешних пограничных серверов для:</span><span class="sxs-lookup"><span data-stu-id="3f030-127">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="3f030-128">Пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="3f030-128">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="3f030-129">Служба пограничного сервера веб-конференций</span><span class="sxs-lookup"><span data-stu-id="3f030-129">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="3f030-130">Пограничная служба аудио- и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="3f030-130">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="3f030-131">Технически сертификат не назначается для пограничного сервера аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="3f030-131">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="3f030-132">Безопасная связь и проверка подлинности управляются службой проверки подлинности Media Relay (MRAS).</span><span class="sxs-lookup"><span data-stu-id="3f030-132">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="3f030-133">MRAS использует сертификат, назначенный внутреннему интерфейсу пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="3f030-133">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="3f030-p105">Обратите внимание, что альтернативные имена субъекта автоматически добавляются в сертификат на основе определений в построителе топологий. Записи альтернативных имен необходимы для дополнительных доменов SIP и прочих записей, которые должны поддерживаться. Имя субъекта копируется в одно из альтернативных имен, что необходимо для правильного выполнения операций.</span><span class="sxs-lookup"><span data-stu-id="3f030-p105">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3f030-137">См. также</span><span class="sxs-lookup"><span data-stu-id="3f030-137">See Also</span></span>


[<span data-ttu-id="3f030-138">Пример конфигурации XMPP в Lync Server 2013 – XMPP Федерация с Google говорите</span><span class="sxs-lookup"><span data-stu-id="3f030-138">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="3f030-139">Планирование сертификатов пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f030-139">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="3f030-140">Сводка по сертификатам — единая консолидированная пограничная с частными IP-адресами с использованием NAT в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f030-140">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="3f030-141">Сводка по сертификатам — единая Объединенная пограничная с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f030-141">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="3f030-142">Сводка по сертификатам — масштабируемый консолидированный край, балансировка нагрузки на DNS с частными IP-адресами с использованием NAT в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f030-142">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[<span data-ttu-id="3f030-143">Сводка по сертификатам — масштабируемый консолидированный край, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f030-143">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="3f030-144">Сводка по сертификатам — масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f030-144">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

