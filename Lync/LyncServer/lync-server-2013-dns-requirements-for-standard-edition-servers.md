---
title: 'Lync Server 2013: требования к DNS для серверов Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2064181a7c4d60015905d5974ac01378b7d025e2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="c777e-102">Требования DNS для серверов Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c777e-102">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c777e-103">_**Последнее изменение темы:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="c777e-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="c777e-104">В данном разделе описываются записи службы доменных имен (DNS), необходимые для развертывания серверов Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c777e-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="c777e-105">DNS-записи для серверов Standard Edition</span><span class="sxs-lookup"><span data-stu-id="c777e-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="c777e-106">В следующей таблице указаны требования к DNS для развертывания сервера Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c777e-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>

### <a name="dns-requirements-for-a-standard-edition-server"></a><span data-ttu-id="c777e-107">Требования к DNS для сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="c777e-107">DNS Requirements for a Standard Edition Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c777e-108">Сценарий развертывания</span><span class="sxs-lookup"><span data-stu-id="c777e-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="c777e-109">Требование к DNS</span><span class="sxs-lookup"><span data-stu-id="c777e-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c777e-110">Сервер Standard Edition</span><span class="sxs-lookup"><span data-stu-id="c777e-110">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="c777e-111">Внутренняя запись A, которая разрешает полное доменное имя сервера в его IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="c777e-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c777e-112">Автоматический вход клиентов</span><span class="sxs-lookup"><span data-stu-id="c777e-112">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="c777e-113">Для каждого поддерживаемого домена SIP запись SRV для _sipinternaltls. _tcp. &lt;домен&gt; через порт 5061, который соответствует полному доменному имени сервера Standard Edition, который выполняет проверку подлинности и перенаправляет запросы клиентов на вход.</span><span class="sxs-lookup"><span data-stu-id="c777e-113">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="c777e-114">Дополнительные сведения см. <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">в статье требования к DNS для автоматического входа клиентов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c777e-114">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c777e-115">Обнаружение веб-службы обновления устройств устройствами объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="c777e-115">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="c777e-116">Внутренняя запись A с именем ucupdates – R2. &lt;Домен&gt; SIP, который разрешается в IP-адрес сервера Standard Edition, на котором размещается веб-служба обновления устройств.</span><span class="sxs-lookup"><span data-stu-id="c777e-116">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="c777e-117">В ситуации, когда устройство объединенных коммуникаций включено, но пользователь еще никогда не выполнял вход на него, запись A позволяет устройству обнаруживать сервер с веб-службой обновления устройств и получать обновления.</span><span class="sxs-lookup"><span data-stu-id="c777e-117">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="c777e-118">В противном случае устройство получает сведения о сервере посредством автоматической подготовки при первом входе пользователя.</span><span class="sxs-lookup"><span data-stu-id="c777e-118">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c777e-119">Обратный прокси-сервер для поддержки HTTP-трафика</span><span class="sxs-lookup"><span data-stu-id="c777e-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="c777e-120">Внешняя запись A, которая разрешает полное доменное имя внешней веб-фермы во внешний IP-адрес обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="c777e-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="c777e-121">Клиенты и устройства объединенных коммуникаций используют эту запись для подключения к обратному прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="c777e-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="c777e-122">Дополнительные сведения: <a href="lync-server-2013-determine-dns-requirements.md">Определение требований к DNS для Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="c777e-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

