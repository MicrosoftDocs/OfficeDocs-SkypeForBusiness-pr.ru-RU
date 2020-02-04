---
title: 'Lync Server 2013: сведения о сертификате — расширяемая Федерация протоколов обмена сообщениями и присутствия (КСМПП)'
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
ms.openlocfilehash: 7af2c226397c5225fc26f6dbdf40d12a4bdb1ca0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="8eb67-102">Сведения о сертификате — расширяемая Федерация протоколов обмена сообщениями и присутствия (КСМПП) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8eb67-102">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8eb67-103">_**Тема последнего изменения:** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="8eb67-103">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="8eb67-104">Требования к сертификатам для включения и установления связи с партнерами по протоколу расширенного обмена сообщениями (КСМПП) требуют дополнительной записи доменов КСМПП.</span><span class="sxs-lookup"><span data-stu-id="8eb67-104">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains.</span></span> <span data-ttu-id="8eb67-105">Запись, включенная в сертификат в качестве дополнительного имени субъекта (SAN), будет являться доменом, который может принимать участие в КСМПП обмене сообщениями.</span><span class="sxs-lookup"><span data-stu-id="8eb67-105">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="8eb67-106">Домен может быть доменом корневого уровня (например, contoso.com), если вы хотите включить КСМПП для всего домена или выбрать его дочерние домены (например, corp.contoso.com, finance.contoso.com), если вы включаете КСМПП для подмножества пользователей.</span><span class="sxs-lookup"><span data-stu-id="8eb67-106">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="8eb67-107">Сведения о сертификате для протокола расширенного обмена сообщениями и присутствия</span><span class="sxs-lookup"><span data-stu-id="8eb67-107">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8eb67-108">Компонент</span><span class="sxs-lookup"><span data-stu-id="8eb67-108">Component</span></span></th>
<th><span data-ttu-id="8eb67-109">Имя субъекта</span><span class="sxs-lookup"><span data-stu-id="8eb67-109">Subject name</span></span></th>
<th><span data-ttu-id="8eb67-110">Замещающий имена субъектов (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="8eb67-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="8eb67-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8eb67-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8eb67-112">Назначение доступа к службе Edge пограничного сервера или пограничного пула</span><span class="sxs-lookup"><span data-stu-id="8eb67-112">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="8eb67-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8eb67-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8eb67-114">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8eb67-114">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="8eb67-115">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8eb67-115">sip.contoso.com</span></span></p>
<p><span data-ttu-id="8eb67-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8eb67-116">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="8eb67-117">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8eb67-117">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8eb67-118">Первые три элемента сети SAN — это стандартные записи в сети SAN для полного пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8eb67-118">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="8eb67-119">Contoso.com — это запись, необходимая для Федерации с партнером КСМПП на уровне корневого домена.</span><span class="sxs-lookup"><span data-stu-id="8eb67-119">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="8eb67-120">Эта запись позволит КСМПП всем доменам с суффиксом contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8eb67-120">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8eb67-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8eb67-121">See Also</span></span>


[<span data-ttu-id="8eb67-122">Пример конфигурации XMPP в Lync Server 2013 — федерация XMPP с Google Talk</span><span class="sxs-lookup"><span data-stu-id="8eb67-122">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="8eb67-123">Планирование сертификатов пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8eb67-123">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="8eb67-124">Настройка сертификатов пограничного сервера для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8eb67-124">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="8eb67-125">Request-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="8eb67-125">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="8eb67-126">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="8eb67-126">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

