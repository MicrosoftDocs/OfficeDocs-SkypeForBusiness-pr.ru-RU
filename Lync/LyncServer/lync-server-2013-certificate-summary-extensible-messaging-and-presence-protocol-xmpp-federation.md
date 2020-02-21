---
title: 'Lync Server 2013: сводка по сертификатам — Федерация XMPP (Extensible Messaging and Presence Protocol)'
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
ms.openlocfilehash: 45758175a04bad0cc673242087c0a4751c1b01bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="2d034-102">Сводка по сертификатам — Федерация протокола XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d034-102">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d034-103">_**Последнее изменение темы:** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="2d034-103">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="2d034-p101">В сертификатах, которые используются для обеспечения связи с партнерами XMPP, требуются дополнительные записи, содержащие сведения о доменах XMPP. Запись, включаемая в сертификат в виде альтернативного имени субъекта (SAN), содержит имя домена, который может участвовать в обмене данными по протоколу XMPP. Домен может представлять собой домен корневого уровня (например, contoso.com), если вы хотите включить протокол XMPP для всего домена, или набор дочерних доменов (например, corp.contoso.com, finance.contoso.com), если включаете протокол XMPP для подмножества пользователей.</span><span class="sxs-lookup"><span data-stu-id="2d034-p101">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains. The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications. The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="2d034-107">Требования к сертификатам для использования протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="2d034-107">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d034-108">Компонент</span><span class="sxs-lookup"><span data-stu-id="2d034-108">Component</span></span></th>
<th><span data-ttu-id="2d034-109">Имя субъекта</span><span class="sxs-lookup"><span data-stu-id="2d034-109">Subject name</span></span></th>
<th><span data-ttu-id="2d034-110">Альтернативные имена субъекта (SAN)/порядок</span><span class="sxs-lookup"><span data-stu-id="2d034-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="2d034-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2d034-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d034-112">Назначение доступа к пограничной службе пограничного сервера или пограничного пула</span><span class="sxs-lookup"><span data-stu-id="2d034-112">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="2d034-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d034-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2d034-114">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d034-114">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="2d034-115">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d034-115">sip.contoso.com</span></span></p>
<p><span data-ttu-id="2d034-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2d034-116">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="2d034-117">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d034-117">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2d034-118">Первые три записи SAN — это обычные записи SAN для полного пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="2d034-118">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="2d034-119">Contoso.com — это запись, необходимая для федерации с партнером XMPP на корневом уровне домена.</span><span class="sxs-lookup"><span data-stu-id="2d034-119">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="2d034-120">Эта запись позволит XMPP для всех доменов с суффиксом contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2d034-120">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2d034-121">См. также</span><span class="sxs-lookup"><span data-stu-id="2d034-121">See Also</span></span>


[<span data-ttu-id="2d034-122">Пример конфигурации XMPP в Lync Server 2013 – XMPP Федерация с Google говорите</span><span class="sxs-lookup"><span data-stu-id="2d034-122">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="2d034-123">Планирование сертификатов пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d034-123">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="2d034-124">Настройка пограничных сертификатов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d034-124">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="2d034-125">Request — CsCertificate</span><span class="sxs-lookup"><span data-stu-id="2d034-125">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="2d034-126">Set — CsCertificate</span><span class="sxs-lookup"><span data-stu-id="2d034-126">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

