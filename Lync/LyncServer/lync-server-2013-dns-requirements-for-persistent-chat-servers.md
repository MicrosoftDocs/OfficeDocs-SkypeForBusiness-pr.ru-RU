---
title: 'Lync Server 2013: требования DNS для хранимых серверов чата'
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
ms.openlocfilehash: b97d3238c64173cb5f9bfcfc12dce40f987da123
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a><span data-ttu-id="cd746-102">Требования DNS к сохраняемым серверам чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd746-102">DNS requirements for Persistent Chat Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd746-103">_**Тема последнего изменения:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="cd746-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="cd746-104">В этом разделе описаны записи DNS, необходимые для развертывания сохраненных серверов чата.</span><span class="sxs-lookup"><span data-stu-id="cd746-104">This section describes the Domain Name System (DNS) records that are required for deployment of Persistent Chat Servers.</span></span>

<div>

## <a name="dns-records-for-persistent-chat-servers"></a><span data-ttu-id="cd746-105">Записи DNS для постоянных серверов чата</span><span class="sxs-lookup"><span data-stu-id="cd746-105">DNS Records for Persistent Chat Servers</span></span>

<span data-ttu-id="cd746-106">В приведенной ниже таблице указаны требования DNS для развертывания сервера для сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cd746-106">The following table specifies DNS requirements for Persistent Chat Server deployment.</span></span>

### <a name="dns-requirements-for-a-persistent-chat-server"></a><span data-ttu-id="cd746-107">Требования к DNS для сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="cd746-107">DNS Requirements for a Persistent Chat Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd746-108">Сценарий развертывания</span><span class="sxs-lookup"><span data-stu-id="cd746-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="cd746-109">Требование DNS</span><span class="sxs-lookup"><span data-stu-id="cd746-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd746-110">Один сервер сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="cd746-110">One Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="cd746-111">Внутренняя запись A, разрешающая полное доменное имя сервера в IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="cd746-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd746-112">Пул сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="cd746-112">Persistent Chat pool</span></span></p></td>
<td><p><span data-ttu-id="cd746-113">Внутренняя запись, разрешающая полное доменное имя (FQDN) серверов в свой IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="cd746-113">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="cd746-114"><strong>Пример</strong></span><span class="sxs-lookup"><span data-stu-id="cd746-114"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="cd746-115">PersistentChatServer01.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="cd746-115">PersistentChatServer01.contoso.com     10.10.10.1</span></span></p>
<p><span data-ttu-id="cd746-116">PersistentChatServer02.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="cd746-116">PersistentChatServer02.contoso.com     10.10.10.2</span></span></p>
<p><span data-ttu-id="cd746-117">Внутренняя запись, разрешающая полное доменное имя (FQDN) серверов в свой IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="cd746-117">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="cd746-118"><strong>Пример</strong></span><span class="sxs-lookup"><span data-stu-id="cd746-118"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="cd746-119">PersistentChatPool.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="cd746-119">PersistentChatPool.contoso.com    10.10.10.1</span></span></p>
<p><span data-ttu-id="cd746-120">PersistentChatPool.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="cd746-120">PersistentChatPool.contoso.com    10.10.10.2</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

