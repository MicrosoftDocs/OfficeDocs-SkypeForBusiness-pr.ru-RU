---
title: 'Lync Server 2013: Общие сведения о портах — автообнаружение'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 945e3ed9d532f27676e250c29ab415646bd967ec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="627ef-102">Сводка порта: автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="627ef-102">Port summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="627ef-103">_**Тема последнего изменения:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="627ef-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="627ef-104">Служба автообнаружения Lync Server 2013 работает на серверах директоров и интерфейсов, а также при публикации в DNS с помощью `lyncdiscover.<domain>` записей `lyncdiscoverinternal.<domain>` Host и может использоваться клиентами для поиска возможностей Lync Server.</span><span class="sxs-lookup"><span data-stu-id="627ef-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="627ef-105">Чтобы использовать функцию автообнаружения на мобильных устройствах с Lync Mobile, вам может потребоваться изменить список альтернативных имен субъектов сертификата на любом из каталогов и на сервере переднего плана, на котором запущена служба автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="627ef-105">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="627ef-106">Кроме того, может потребоваться изменить список альтернативных имен субъектов в сертификатах, используемых для использования внешних правил публикации веб-службы на обратных прокси.</span><span class="sxs-lookup"><span data-stu-id="627ef-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="627ef-107">Решение о том, следует ли использовать списки альтернативных имен для субъектов в обратных прокси-серверах, зависит от того, публикуются ли служба автообнаружения для порта 80 или для порта 443:</span><span class="sxs-lookup"><span data-stu-id="627ef-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="627ef-108">**Опубликованные на порте 80**   для мобильных устройств, при возникновении начального запроса в службе автообнаружения на порте 80 не требуются изменения сертификата.</span><span class="sxs-lookup"><span data-stu-id="627ef-108">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="627ef-109">Это связано с тем, что мобильные устройства Lync будут получать доступ к обратному прокси-серверу на порте 80 извне, а затем перенаправляться на директорию или сервер переднего плана с помощью внутреннего порта 8080.</span><span class="sxs-lookup"><span data-stu-id="627ef-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="627ef-110">**Опубликовано на порте 443**   список альтернативных имен субъектов на сертификатах, используемых внешним правилом публикации веб-служб `lyncdiscover.<sipdomain>` , должен содержать запись для каждого домена SIP в Организации.</span><span class="sxs-lookup"><span data-stu-id="627ef-110">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="627ef-111">Для новых установок и обновлений с Lync Server 2010, в которых вы развернули мобильность, вы используете порт 80 для автообнаружения службы Mobility Service или повторно выдавал сертификаты с нужным именем субъекта и дополнительными именами для темы.</span><span class="sxs-lookup"><span data-stu-id="627ef-111">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="627ef-112">Проверьте сертификаты на своем режиссере и на сервере переднего плана, чтобы подтвердить, какой именно путь вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="627ef-112">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="627ef-113">Сведения о брандмауэре для обратного прокси-сервера: внешний интерфейс</span><span class="sxs-lookup"><span data-stu-id="627ef-113">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="627ef-114">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="627ef-114">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="627ef-115">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="627ef-115">Source IP Address</span></span></th>
<th><span data-ttu-id="627ef-116">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="627ef-116">Destination IP Address</span></span></th>
<th><span data-ttu-id="627ef-117">Notes</span><span class="sxs-lookup"><span data-stu-id="627ef-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="627ef-118">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="627ef-118">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="627ef-119">Любой</span><span class="sxs-lookup"><span data-stu-id="627ef-119">Any</span></span></p></td>
<td><p><span data-ttu-id="627ef-120">Обратный прослушиватель прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="627ef-120">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="627ef-121">Необязательно Перенаправление на HTTPS, если пользователь вводит http://&lt;публишедситефкдн&gt;.</span><span class="sxs-lookup"><span data-stu-id="627ef-121">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="627ef-122">Кроме того, если вы используете Office Web Apps для конференций и службу автообнаружения для мобильных устройств, работающих в Lync, в ситуациях, когда Организация не может изменить сертификат правила публикации внешней веб-службы.</span><span class="sxs-lookup"><span data-stu-id="627ef-122">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="627ef-123">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="627ef-123">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="627ef-124">Любой</span><span class="sxs-lookup"><span data-stu-id="627ef-124">Any</span></span></p></td>
<td><p><span data-ttu-id="627ef-125">Обратный прослушиватель прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="627ef-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="627ef-126">Загрузка записной книжки, служба веб-запросов к адресной книге, автоматическое обнаружение, обновление клиента, содержимое собрания, обновления устройства, развертывание групп, Office Web Apps для конференций, Конференц-связь с телефонным подключением и собраний.</span><span class="sxs-lookup"><span data-stu-id="627ef-126">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="627ef-127">Сведения о брандмауэре для обратного прокси-сервера: внутренний интерфейс</span><span class="sxs-lookup"><span data-stu-id="627ef-127">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="627ef-128">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="627ef-128">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="627ef-129">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="627ef-129">Source IP Address</span></span></th>
<th><span data-ttu-id="627ef-130">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="627ef-130">Destination IP Address</span></span></th>
<th><span data-ttu-id="627ef-131">Notes</span><span class="sxs-lookup"><span data-stu-id="627ef-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="627ef-132">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="627ef-132">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="627ef-133">Внутренний обратный интерфейс прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="627ef-133">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="627ef-134">Сервер переднего плана, пул переднего плана, режиссер, директор пула, Office Web Apps для конференций</span><span class="sxs-lookup"><span data-stu-id="627ef-134">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="627ef-135">Требуется при использовании службы автообнаружения для мобильных устройств, работающих с Lync, в ситуациях, когда Организация не может изменить сертификат правила публикации внешней веб-службы.</span><span class="sxs-lookup"><span data-stu-id="627ef-135">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="627ef-136">Трафик, отправленный на порт 80 на внешнем прокси-сервере, перенаправляется в пул на порте 8080 из внутреннего прокси-интерфейса, чтобы они могли отличать ее от внутреннего веб-трафика.</span><span class="sxs-lookup"><span data-stu-id="627ef-136">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="627ef-137">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="627ef-137">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="627ef-138">Внутренний обратный интерфейс прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="627ef-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="627ef-139">Сервер переднего плана, пул переднего плана, режиссер, директор пула, Office Web Apps для конференций</span><span class="sxs-lookup"><span data-stu-id="627ef-139">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="627ef-140">Трафик, отправленный на порт 443 на внешнем прокси-сервере, перенаправляется в пул на порте 4443 из внутреннего прокси-интерфейса, чтобы они могли отличать ее от внутреннего веб-трафика.</span><span class="sxs-lookup"><span data-stu-id="627ef-140">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

