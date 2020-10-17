---
title: Сводка по DNS — Федерация расширенной службы обмена сообщениями и протокола присутствия (XMPP)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ac2e44382aa75b61ae4e2966b5ef87fd977e798
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532136"
---
# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="79af5-102">Сводка по DNS — Федерация XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79af5-102">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79af5-103">_**Последнее изменение темы:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="79af5-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="79af5-104">Чтобы настроить расширенный протокол обмена сообщениями (XMPP) для развертывания, создайте две записи службы доменных имен (DNS) на внешнем DNS-сервере, которые будут разрешать записи в пограничной службе доступа пограничного сервера или пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="79af5-104">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two Domain Name System (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="79af5-105">Сводка по DNS для расширяемого протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="79af5-105">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79af5-106">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="79af5-106">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="79af5-107">полное доменное имя;</span><span class="sxs-lookup"><span data-stu-id="79af5-107">FQDN</span></span></th>
<th><span data-ttu-id="79af5-108">IP-адрес/запись узла полного доменного имени</span><span class="sxs-lookup"><span data-stu-id="79af5-108">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="79af5-109">Сопоставление/комментарии</span><span class="sxs-lookup"><span data-stu-id="79af5-109">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79af5-110">Внешний DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="79af5-110">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="79af5-111">_xmpp-server._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="79af5-111">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="79af5-112">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79af5-112">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="79af5-113">Внешний интерфейс прокси-сервера XMPP в пограничной службе доступа или пограничном пуле. При необходимости повторите эти действия для всех внутренних доменов SIP с пользователями Lync, в которых доступ к контактам с контактами XMPP разрешен через конфигурацию политики внешнего доступа через глобальную политику, политику сайта, в которой находится пользователь, или политика пользователей, применяемая к пользователю с поддержкой Lync.</span><span class="sxs-lookup"><span data-stu-id="79af5-113">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="79af5-114">Разрешенный домен XMPP также должен быть настроен в политике федеративных партнеров XMPP.</span><span class="sxs-lookup"><span data-stu-id="79af5-114">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="79af5-115">Дополнительные сведения можно найти в разделах, <strong>приведенных в разделе</strong> .</span><span class="sxs-lookup"><span data-stu-id="79af5-115">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79af5-116">Внешний DNS/A</span><span class="sxs-lookup"><span data-stu-id="79af5-116">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="79af5-117">xmpp.contoso.com (пример)</span><span class="sxs-lookup"><span data-stu-id="79af5-117">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="79af5-118">IP-адрес пограничной службы доступа на пограничном сервере или пограничном пуле, где размещен прокси-сервер XMPP</span><span class="sxs-lookup"><span data-stu-id="79af5-118">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="79af5-119">Указывает на пограничный сервер доступа или пограничный пул, на котором размещается прокси-служба XMPP.</span><span class="sxs-lookup"><span data-stu-id="79af5-119">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="79af5-120">Как правило, созданная запись SRV указывает на эту запись узла (A или AAAA).</span><span class="sxs-lookup"><span data-stu-id="79af5-120">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="79af5-121">См. также</span><span class="sxs-lookup"><span data-stu-id="79af5-121">See Also</span></span>


[<span data-ttu-id="79af5-122">Настройка Федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79af5-122">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  


[<span data-ttu-id="79af5-123">Определение требований к DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79af5-123">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

