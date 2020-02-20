---
title: 'Lync Server 2013: требования к DNS для сервера Standard Edition'
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
ms.openlocfilehash: 4cdd7a32519fe510819f82619c9086b22b820a52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="a98e7-102">Требования DNS для сервера Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a98e7-102">DNS requirements for a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a98e7-103">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="a98e7-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a98e7-104">В данном разделе описываются записи службы доменных имен (DNS), необходимые для развертывания серверов Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a98e7-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="a98e7-105">DNS-записи для серверов Standard Edition</span><span class="sxs-lookup"><span data-stu-id="a98e7-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="a98e7-106">В следующей таблице указаны требования к DNS для развертывания сервера Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a98e7-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a98e7-107">Сценарий развертывания</span><span class="sxs-lookup"><span data-stu-id="a98e7-107">Deployment scenario</span></span></th>
<th><span data-ttu-id="a98e7-108">Требование к DNS</span><span class="sxs-lookup"><span data-stu-id="a98e7-108">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a98e7-109">Сервер Standard Edition</span><span class="sxs-lookup"><span data-stu-id="a98e7-109">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="a98e7-110">Внутренняя запись A, которая разрешает полное доменное имя сервера в его IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="a98e7-110">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98e7-111">Автоматический вход клиентов</span><span class="sxs-lookup"><span data-stu-id="a98e7-111">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="a98e7-112">Для каждого поддерживаемого домена SIP запись SRV для _sipinternaltls. _tcp. &lt;домен&gt; через порт 5061, который соответствует полному доменному имени сервера Standard Edition, который выполняет проверку подлинности и перенаправляет запросы клиентов на вход.</span><span class="sxs-lookup"><span data-stu-id="a98e7-112">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="a98e7-113">Дополнительные сведения см. <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">в статье требования к DNS для автоматического входа клиентов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a98e7-113">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98e7-114">Обнаружение веб-службы обновления устройств устройствами объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="a98e7-114">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="a98e7-115">Внутренняя запись A с именем ucupdates – R2. &lt;Домен&gt; SIP, который разрешается в IP-адрес сервера Standard Edition, на котором размещается веб-служба обновления устройств.</span><span class="sxs-lookup"><span data-stu-id="a98e7-115">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="a98e7-116">В ситуации, когда устройство объединенных коммуникаций включено, но пользователь еще никогда не выполнял вход на него, запись A позволяет устройству обнаруживать сервер с веб-службой обновления устройств и получать обновления.</span><span class="sxs-lookup"><span data-stu-id="a98e7-116">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="a98e7-117">В противном случае устройство получает сведения о сервере посредством автоматической подготовки при первом входе пользователя.</span><span class="sxs-lookup"><span data-stu-id="a98e7-117">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span> <span data-ttu-id="a98e7-118">Сведения о <a href="lync-server-2013-device-update-web-service.md">веб-службе обновления устройств в Lync Server 2013</a> можно найти в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="a98e7-118">For details, see <a href="lync-server-2013-device-update-web-service.md">Device Update Web service in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98e7-119">Обратный прокси-сервер для поддержки трафика HTTP</span><span class="sxs-lookup"><span data-stu-id="a98e7-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="a98e7-120">Внешняя запись A, которая разрешает полное доменное имя внешней веб-фермы во внешний IP-адрес обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="a98e7-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="a98e7-121">Клиенты и устройства объединенных коммуникаций используют эту запись для подключения к обратному прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="a98e7-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="a98e7-122">Дополнительные сведения: <a href="lync-server-2013-determine-dns-requirements.md">Определение требований к DNS для Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="a98e7-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a98e7-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a98e7-123">See Also</span></span>


[<span data-ttu-id="a98e7-124">Требования DNS для автоматического входа клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a98e7-124">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[<span data-ttu-id="a98e7-125">Определение требований к DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a98e7-125">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="a98e7-126">Веб-служба обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a98e7-126">Device Update Web service in Lync Server 2013</span></span>](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

