---
title: 'Сводка DNS: интеграция расширяемого обмена сообщениями и протокола присутствия (КСМПП)'
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
ms.openlocfilehash: 941996ea1167cf9baeee05567a00c71ea5ed4baa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="99c04-102">Общие сведения о DNS — расширяемая Федерация протоколов обмена сообщениями и доступности КСМПП в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99c04-102">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99c04-103">_**Тема последнего изменения:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="99c04-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="99c04-104">Чтобы настроить расширенный протокол обмена сообщениями (КСМПП) для развертывания, вы создаете две записи DNS (Domain Name System) на внешнем DNS-сервере, который будет разрешать записи в службу Edge EDGE на пограничном сервере или пуле Edge.</span><span class="sxs-lookup"><span data-stu-id="99c04-104">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two Domain Name System (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="99c04-105">Сводка DNS по расширенному протоколу обмена сообщениями и присутствием</span><span class="sxs-lookup"><span data-stu-id="99c04-105">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99c04-106">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="99c04-106">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="99c04-107">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="99c04-107">FQDN</span></span></th>
<th><span data-ttu-id="99c04-108">IP-адрес или полное доменное имя записи узла</span><span class="sxs-lookup"><span data-stu-id="99c04-108">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="99c04-109">Карты и примечания</span><span class="sxs-lookup"><span data-stu-id="99c04-109">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99c04-110">Внешние DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="99c04-110">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="99c04-111">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="99c04-111">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="99c04-112">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="99c04-112">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="99c04-113">Внешний интерфейс КСМПП прокси-сервера в службе пограничного доступа или пуле Edge. При необходимости повторите эти действия для всех внутренних доменов SIP, в которых пользователи Lync поддерживают доступ к контактам с контактами КСМПП с помощью глобальной политики, политики сайта, в которой находится пользователь, или политики пользователя, примененной к Пользователь с поддержкой Lync.</span><span class="sxs-lookup"><span data-stu-id="99c04-113">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="99c04-114">Разрешенный домен КСМПП также должен быть настроен в политике федеративных партнеров КСМПП.</span><span class="sxs-lookup"><span data-stu-id="99c04-114">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="99c04-115">Дополнительные сведения <strong>можно</strong> найти в разделах.</span><span class="sxs-lookup"><span data-stu-id="99c04-115">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99c04-116">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="99c04-116">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="99c04-117">xmpp.contoso.com (например)</span><span class="sxs-lookup"><span data-stu-id="99c04-117">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="99c04-118">IP-адрес службы пограничного доступа на пограничном сервере или в пограничном пуле, где размещен прокси-сервер КСМПП</span><span class="sxs-lookup"><span data-stu-id="99c04-118">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="99c04-119">Указывает на службу пограничного доступа или пул EDGE, на котором размещена служба прокси КСМПП.</span><span class="sxs-lookup"><span data-stu-id="99c04-119">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="99c04-120">Как правило, создаваемая SRV-запись будет указывать на эту запись узла (A или AAAA).</span><span class="sxs-lookup"><span data-stu-id="99c04-120">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="99c04-121">См. также</span><span class="sxs-lookup"><span data-stu-id="99c04-121">See Also</span></span>


[<span data-ttu-id="99c04-122">Настройка федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99c04-122">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  


[<span data-ttu-id="99c04-123">Определение требований DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99c04-123">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

