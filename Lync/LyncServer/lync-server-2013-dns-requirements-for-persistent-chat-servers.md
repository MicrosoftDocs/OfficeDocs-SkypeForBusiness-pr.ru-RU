---
title: 'Lync Server 2013: требования к DNS для серверов сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Persistent Chat Servers
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205391(v=OCS.15)
ms:contentKeyID: 48185857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea581eb04f2899ecafd49364b38a1064303bdcdc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a><span data-ttu-id="7026b-102">Требования DNS для серверов сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7026b-102">DNS requirements for Persistent Chat Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7026b-103">_**Последнее изменение темы:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="7026b-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="7026b-104">В этом разделе описываются записи службы доменных имен (DNS), необходимые для развертывания серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="7026b-104">This section describes the Domain Name System (DNS) records that are required for deployment of Persistent Chat Servers.</span></span>

<div>

## <a name="dns-records-for-persistent-chat-servers"></a><span data-ttu-id="7026b-105">Записи DNS для серверов сохраняемых чатов</span><span class="sxs-lookup"><span data-stu-id="7026b-105">DNS Records for Persistent Chat Servers</span></span>

<span data-ttu-id="7026b-106">В следующей таблице указаны требования к DNS для развертывания сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="7026b-106">The following table specifies DNS requirements for Persistent Chat Server deployment.</span></span>

### <a name="dns-requirements-for-a-persistent-chat-server"></a><span data-ttu-id="7026b-107">Требования DNS для серверов сохраняемых чатов</span><span class="sxs-lookup"><span data-stu-id="7026b-107">DNS Requirements for a Persistent Chat Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7026b-108">Сценарий развертывания</span><span class="sxs-lookup"><span data-stu-id="7026b-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="7026b-109">Требование DNS</span><span class="sxs-lookup"><span data-stu-id="7026b-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7026b-110">Один сервер сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="7026b-110">One Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="7026b-111">Внутренняя запись A, разрешающая полное доменное имя сервера в IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="7026b-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7026b-112">Пул сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="7026b-112">Persistent Chat pool</span></span></p></td>
<td><p><span data-ttu-id="7026b-113">Внутренняя запись A, разрешающая полное доменное имя сервера в IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="7026b-113">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="7026b-114"><strong>Пример</strong></span><span class="sxs-lookup"><span data-stu-id="7026b-114"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="7026b-115">PersistentChatServer01.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="7026b-115">PersistentChatServer01.contoso.com     10.10.10.1</span></span></p>
<p><span data-ttu-id="7026b-116">PersistentChatServer02.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="7026b-116">PersistentChatServer02.contoso.com     10.10.10.2</span></span></p>
<p><span data-ttu-id="7026b-117">Внутренняя запись A, разрешающая полное доменное имя сервера в IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="7026b-117">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="7026b-118"><strong>Пример</strong></span><span class="sxs-lookup"><span data-stu-id="7026b-118"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="7026b-119">PersistentChatPool.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="7026b-119">PersistentChatPool.contoso.com    10.10.10.1</span></span></p>
<p><span data-ttu-id="7026b-120">PersistentChatPool.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="7026b-120">PersistentChatPool.contoso.com    10.10.10.2</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

