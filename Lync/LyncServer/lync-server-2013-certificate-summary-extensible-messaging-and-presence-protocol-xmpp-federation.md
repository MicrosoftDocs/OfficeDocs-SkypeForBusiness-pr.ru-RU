---
title: 'Lync Server 2013: сводка по сертификатам — Федерация XMPP (Extensible Messaging and Presence Protocol)'
description: 'Lync Server 2013: сводка по сертификатам — расширяемая Федерация протокола обмена сообщениями и протокола присутствия (XMPP).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e2bb593d909c2eec6032dc89c07cc5f5b1a72db
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572345"
---
# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="eb76f-103">Сводка по сертификатам — Федерация протокола XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb76f-103">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb76f-104">_**Последнее изменение темы:** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="eb76f-104">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="eb76f-p101">В сертификатах, которые используются для обеспечения связи с партнерами XMPP, требуются дополнительные записи, содержащие сведения о доменах XMPP. Запись, включаемая в сертификат в виде альтернативного имени субъекта (SAN), содержит имя домена, который может участвовать в обмене данными по протоколу XMPP. Домен может представлять собой домен корневого уровня (например, contoso.com), если вы хотите включить протокол XMPP для всего домена, или набор дочерних доменов (например, corp.contoso.com, finance.contoso.com), если включаете протокол XMPP для подмножества пользователей.</span><span class="sxs-lookup"><span data-stu-id="eb76f-p101">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains. The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications. The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="eb76f-108">Требования к сертификатам для использования протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="eb76f-108">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb76f-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="eb76f-109">Component</span></span></th>
<th><span data-ttu-id="eb76f-110">Имя субъекта</span><span class="sxs-lookup"><span data-stu-id="eb76f-110">Subject name</span></span></th>
<th><span data-ttu-id="eb76f-111">Альтернативные имена субъекта (SAN)/порядок</span><span class="sxs-lookup"><span data-stu-id="eb76f-111">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="eb76f-112">Comments</span><span class="sxs-lookup"><span data-stu-id="eb76f-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb76f-113">Назначение доступа к пограничной службе пограничного сервера или пограничного пула</span><span class="sxs-lookup"><span data-stu-id="eb76f-113">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="eb76f-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb76f-114">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="eb76f-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb76f-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="eb76f-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb76f-116">sip.contoso.com</span></span></p>
<p><span data-ttu-id="eb76f-117">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="eb76f-117">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="eb76f-118">contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb76f-118">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="eb76f-119">Первые три записи SAN — это обычные записи SAN для полного пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="eb76f-119">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="eb76f-120">Contoso.com — это запись, необходимая для федерации с партнером XMPP на корневом уровне домена.</span><span class="sxs-lookup"><span data-stu-id="eb76f-120">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="eb76f-121">Эта запись позволит XMPP для всех доменов с суффиксом contoso.com.</span><span class="sxs-lookup"><span data-stu-id="eb76f-121">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eb76f-122">См. также</span><span class="sxs-lookup"><span data-stu-id="eb76f-122">See Also</span></span>


[<span data-ttu-id="eb76f-123">Пример конфигурации XMPP в Lync Server 2013 – XMPP Федерация с Google говорите</span><span class="sxs-lookup"><span data-stu-id="eb76f-123">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="eb76f-124">Планирование сертификатов пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb76f-124">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="eb76f-125">Настройка пограничных сертификатов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb76f-125">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="eb76f-126">Request — CsCertificate</span><span class="sxs-lookup"><span data-stu-id="eb76f-126">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="eb76f-127">Set — CsCertificate</span><span class="sxs-lookup"><span data-stu-id="eb76f-127">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

