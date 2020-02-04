---
title: 'Lync Server 2013: Требования DNS для сервера Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ab4280ca3ed329d0dc926756f6bfd933595ca08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="7dfac-102">Требования DNS для сервера Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7dfac-102">DNS requirements for a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7dfac-103">_**Тема последнего изменения:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="7dfac-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="7dfac-104">В этом разделе описаны записи DNS, необходимые для развертывания стандартных серверов выпуска.</span><span class="sxs-lookup"><span data-stu-id="7dfac-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="7dfac-105">Записи DNS для серверов Standard Edition</span><span class="sxs-lookup"><span data-stu-id="7dfac-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="7dfac-106">В приведенной ниже таблице указаны требования к DNS для развертывания сервера Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7dfac-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7dfac-107">Сценарий развертывания</span><span class="sxs-lookup"><span data-stu-id="7dfac-107">Deployment scenario</span></span></th>
<th><span data-ttu-id="7dfac-108">Требование DNS</span><span class="sxs-lookup"><span data-stu-id="7dfac-108">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7dfac-109">Standard Edition</span><span class="sxs-lookup"><span data-stu-id="7dfac-109">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="7dfac-110">Внутренняя запись A, разрешающая полное доменное имя сервера в IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="7dfac-110">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dfac-111">Автоматический вход в учетную запись клиента</span><span class="sxs-lookup"><span data-stu-id="7dfac-111">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="7dfac-112">Для каждого поддерживаемого домена SIP — запись SRV для _sipinternaltls. _tcp. &lt;домен&gt; , поступающий на порт 5061 и соответствующий доменному имени сервера Standard Edition, который проверяет подлинность и перенаправляет запросы клиентов на вход.</span><span class="sxs-lookup"><span data-stu-id="7dfac-112">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="7dfac-113">Дополнительные сведения: <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">требования к DNS для автоматического входа на клиент в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7dfac-113">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dfac-114">Обнаружение веб-служб с помощью обновлений на устройствах с единым коммуникационным подключением (UC)</span><span class="sxs-lookup"><span data-stu-id="7dfac-114">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="7dfac-115">Внутренняя запись с именем укупдатес-R2. &lt;Домен&gt; SIP, который РАЗрешается в IP-адрес сервера Standard Edition, на котором размещена служба обновления устройств хостинга.</span><span class="sxs-lookup"><span data-stu-id="7dfac-115">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="7dfac-116">В ситуации, когда устройство для установления связи включено, но пользователь не вошел в систему, запись A позволяет устройству найти веб-службу обновления устройства, на которой размещен сервер, и получить обновления.</span><span class="sxs-lookup"><span data-stu-id="7dfac-116">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="7dfac-117">В противном случае устройство получает сведения о сервере посредством автоматической подготовки при первом входе пользователя.</span><span class="sxs-lookup"><span data-stu-id="7dfac-117">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span> <span data-ttu-id="7dfac-118">Подробные сведения об этом можно найти <a href="lync-server-2013-device-update-web-service.md">в разделе веб-служба обновления устройств в Lync Server 2013</a> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="7dfac-118">For details, see <a href="lync-server-2013-device-update-web-service.md">Device Update Web service in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dfac-119">Обратный прокси-сервер, поддерживающий трафик HTTP</span><span class="sxs-lookup"><span data-stu-id="7dfac-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="7dfac-120">Внешняя запись A, разрешающая полное доменное имя внешней веб-фермы на внешний IP-адрес обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="7dfac-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="7dfac-121">Клиенты и устройства UC используют эту запись для подключения к обратному прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="7dfac-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="7dfac-122">Подробности можно найти в разделе <a href="lync-server-2013-determine-dns-requirements.md">Определение требований DNS для Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="7dfac-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7dfac-123">См. также</span><span class="sxs-lookup"><span data-stu-id="7dfac-123">See Also</span></span>


[<span data-ttu-id="7dfac-124">Требования DNS для автоматического входа клиента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7dfac-124">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[<span data-ttu-id="7dfac-125">Определение требований DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7dfac-125">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="7dfac-126">Веб-служба обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7dfac-126">Device Update Web service in Lync Server 2013</span></span>](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

