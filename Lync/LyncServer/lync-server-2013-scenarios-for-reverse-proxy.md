---
title: 'Lync Server 2013: сценарии для обратного прокси-сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82d5874393e69083ee7058e4e737d21a2fe865ad
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="48479-102">Сценарии для обратного прокси-сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48479-102">Scenarios for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48479-103">_**Последнее изменение темы:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="48479-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="48479-104">Обратные прокси-серверы необходимы в Lync Server 2013 для предоставления доступа к службам и ресурсам, таким как простые URL-адреса собрания и телефонного подключения, адресная книга, содержимое собраний, расширение списка рассылки, службы Mobility Services и другие.</span><span class="sxs-lookup"><span data-stu-id="48479-104">Reverse proxies are required in Lync Server 2013 for providing access to services and resources such as the meeting and dial-in Simple URLs, address book, meeting content, distribution list expansion, mobility services, and others.</span></span> <span data-ttu-id="48479-105">Типичный сценарий обратного прокси-сервера в Lync Server 2013 состоит в том, чтобы разрешить внешним клиентам (например, клиенту для настольных компьютеров или Lync Web App) доступ к внешнему веб-службам директора или сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="48479-105">The typical reverse proxy scenario in Lync Server 2013 is to allow external clients (for example, the desktop client or Lync Web App client) access to the Director or Front End Server external Web Services.</span></span>

<span data-ttu-id="48479-106">**Обратные прокси-и внешние веб-службы**</span><span class="sxs-lookup"><span data-stu-id="48479-106">**Reverse proxy and external web services**</span></span>

<span data-ttu-id="48479-107">![13142405 — d5c9 — 45b7 — a8b7 – a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405 — d5c9 — 45b7 — a8b7 – a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="48479-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>

<span data-ttu-id="48479-108">На этапе планирования вы определяете требования для обратного прокси-сервера в развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48479-108">During the planning phase, you define the requirements for the reverse proxy in a Lync Server 2013 deployment.</span></span> <span data-ttu-id="48479-109">Обратный прокси-сервер обеспечивает доступ к функциям для следующих внешних клиентов:</span><span class="sxs-lookup"><span data-stu-id="48479-109">The reverse proxy enables access to features for the following external clients:</span></span>

  - <span data-ttu-id="48479-110">Клиент Microsoft Lync 2013 для настольных ПК</span><span class="sxs-lookup"><span data-stu-id="48479-110">Microsoft Lync 2013 desktop client</span></span>

  - <span data-ttu-id="48479-111">Microsoft Lync Web App</span><span class="sxs-lookup"><span data-stu-id="48479-111">Microsoft Lync Web App</span></span>

  - <span data-ttu-id="48479-112">Microsoft Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="48479-112">Microsoft Lync Mobile</span></span>

  - <span data-ttu-id="48479-113">Приложение Lync для Магазина Windows</span><span class="sxs-lookup"><span data-stu-id="48479-113">Lync Windows Store app</span></span>

<span data-ttu-id="48479-114">При планировании развертывания Lync Server 2013 вы можете сопоставить фактические требования для Lync Server 2013 с функциями обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="48479-114">When planning your Lync Server 2013 deployment, you map the actual requirements for Lync Server 2013 to the reverse proxy features.</span></span>

1.  <span data-ttu-id="48479-115">Внешние клиенты будут подключаться к обратному прокси-серверу через порт TCP 443 и будут использовать протокол SSL или протокол TLS.</span><span class="sxs-lookup"><span data-stu-id="48479-115">External clients will connect to the reverse proxy on port TCP 443 and will use secure socket layer (SSL) or transport layer security (TLS).</span></span> <span data-ttu-id="48479-116">Клиенты Microsoft Lync Mobile могут подключаться через порт TCP 80, но только при выполнении первоначального подключения к службам Lync Discover и если администратор настроил правильные записи CNAME (или псевдонима) DNS, и принимает этот связь не будет зашифрована.</span><span class="sxs-lookup"><span data-stu-id="48479-116">Microsoft Lync Mobile clients can connect on port TCP 80, but only when performing the initial connection to the Lync discover services and the administrator has configured the proper domain name system (DNS) CNAME (or alias) records, and accepts that this communication will not be encrypted.</span></span>

2.  <span data-ttu-id="48479-117">Lync Server 2013 внешние веб-службы (развернутые на сервере переднего плана и/или в директоре) ожидают подключения через обратный прокси-сервер через порт TCP 4443 и ожидает, что подключение будет SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="48479-117">Lync Server 2013 external web services (deployed on the Front End Server and/or the Director) expect a connection from a reverse proxy on port TCP 4443, and it expects that the connection will be SSL/TLS.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="48479-118">Предлагаемые по умолчанию порты прослушивания для внешних веб-служб — TCP 8080 для трафика HTTP и TCP 4443 для трафика HTTPS.</span><span class="sxs-lookup"><span data-stu-id="48479-118">The suggested default listening ports for the external web services are TCP 8080 for HTTP traffic, and TCP 4443 for HTTPS traffic.</span></span> <span data-ttu-id="48479-119">Построитель топологий позволяет переопределять значения по умолчанию и определять собственные порты прослушивания для внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="48479-119">Topology Builder provides an opportunity to override the defaults and define your own listening ports for the external web services.</span></span> <span data-ttu-id="48479-120">Важно отметить, что обратный прокси-сервер взаимодействовал с внешними веб-службами, а внешние клиенты взаимодействуют с обратным прокси-сервером.</span><span class="sxs-lookup"><span data-stu-id="48479-120">It’s important to note that the reverse proxy communicates with the external web services, and the external clients communicate with the reverse proxy.</span></span> <span data-ttu-id="48479-121">Внешний клиент взаимодействовал с обратным прокси-сервером через порт TCP 443, но вы можете переопределить порт, с которого взаимодействуют обратные прокси-сервера с внешними веб-службами.</span><span class="sxs-lookup"><span data-stu-id="48479-121">The external client communicates with the reverse proxy on port TCP 443, but you can redefine what port the reverse proxy communicates with the external web services on.</span></span> <span data-ttu-id="48479-122">Параметры в построителе топологий для переопределения портов прослушивания по умолчанию для веб-служб позволяют разрешить конфликты прослушиваемых портов, которые могут возникать в вашей инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="48479-122">The options in Topology Builder to override the default listening ports for the web services allows you to resolve listening port conflicts that may arise in your infrastructure.</span></span>

    
    </div>

3.  <span data-ttu-id="48479-123">Lync Server 2013 внешние веб-службы ожидают от клиента неизмененного заголовка узла, чтобы определить, какую службу и каталог веб-сервера пытается использовать клиент.</span><span class="sxs-lookup"><span data-stu-id="48479-123">Lync Server 2013 external web services expect an unmodified Host Header from the client to identify what service and web server directory the client is attempting to use.</span></span> <span data-ttu-id="48479-124">Запросы должны выглядеть так, как если бы они были из обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="48479-124">Requests should appear as if they came from the reverse proxy</span></span>

4.  <span data-ttu-id="48479-125">Внешние веб-службы используют определенные виртуальные каталоги веб-сервера (Вдир), предоставляющие службы, предлагаемые клиентам.</span><span class="sxs-lookup"><span data-stu-id="48479-125">The external web services use defined web server virtual directories (vDir) that provide the services offered to clients.</span></span> <span data-ttu-id="48479-126">Веб-службы с определенным внешним идентификацией:</span><span class="sxs-lookup"><span data-stu-id="48479-126">Specific externally identifiable web services are:</span></span>
    
      - <span data-ttu-id="48479-127">"Встреча" Вдир для собраний по веб-конференциям</span><span class="sxs-lookup"><span data-stu-id="48479-127">The “Meet” vDir for web conference meetings</span></span>
    
      - <span data-ttu-id="48479-128">"Dial-in" Вдир для телефонного доступа и телефонной конференции</span><span class="sxs-lookup"><span data-stu-id="48479-128">The “Dialin” vDir for phone access and phone conferencing</span></span>
    
      - <span data-ttu-id="48479-129">"Автообнаружение" Вдир для приложения Магазина Windows для Lync, Lync Mobile и настольный клиент Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="48479-129">The “Autodiscover” vDir for Lync Windows Store app, Lync Mobile, and the desktop client Lync 2013.</span></span> <span data-ttu-id="48479-130">Служба автообнаружения в Lync Server 2013 известна как DNS-имя "lyncdiscover"</span><span class="sxs-lookup"><span data-stu-id="48479-130">Autodiscover in Lync Server 2013 is known by the DNS name “lyncdiscover”</span></span>
    
      - <span data-ttu-id="48479-131">Внешние клиенты получают доступ к неопределенным службам путем прямого вызова внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="48479-131">Services not defined are accessed by the external client by direct calls to the external web services.</span></span> <span data-ttu-id="48479-132">Например, для расширения группы рассылки (ДЛКС) и службы адресной книги (ABS) доступны прямые звонки на внешние веб-службы и связанные Вдирс.</span><span class="sxs-lookup"><span data-stu-id="48479-132">For example, distribution group expansion (DLX) and the address book service (ABS) are accessed by direct calls to the external web services and associated vDirs.</span></span> <span data-ttu-id="48479-133">Клиент знает фактический путь к Вдир и создает унифицированный указатель записи (URL-адрес) на основе этих сведений.</span><span class="sxs-lookup"><span data-stu-id="48479-133">The client knows the actual path to the vDir and constructs a uniform record locator (URL) based on this information.</span></span> <span data-ttu-id="48479-134">Клиент будет получать доступ к службе адресной книги, используя URL-адрес, похожий на`https://externalweb.contoso.com/abs/handler`</span><span class="sxs-lookup"><span data-stu-id="48479-134">The client would access the address book service using a URL similar to `https://externalweb.contoso.com/abs/handler`</span></span>
    
      - <span data-ttu-id="48479-135">Сервер Office Web Apps при определении и настройке конференций в составе топологии Lync Server</span><span class="sxs-lookup"><span data-stu-id="48479-135">The Office Web Apps Server when conferencing is defined and configured as part of the Lync Server topology</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="48479-136">Сервер Office Web Apps — это отдельный сервер ролей, который не настроен как часть внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="48479-136">The Office Web Apps Server is a separate role server and is not configured as part of the external web services.</span></span> <span data-ttu-id="48479-137">Этот сервер отдельно опубликован для клиентского доступа.</span><span class="sxs-lookup"><span data-stu-id="48479-137">This server is separately published for client access.</span></span>

        
        </div>

5.  <span data-ttu-id="48479-138">Определите мост SSL для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="48479-138">Define SSL bridging for each service.</span></span> <span data-ttu-id="48479-139">Внешний порт TCP 443 сопоставлен с портом внешней веб-службы TCP 4443.</span><span class="sxs-lookup"><span data-stu-id="48479-139">The external port TCP 443 is mapped to the external web services port of TCP 4443.</span></span> <span data-ttu-id="48479-140">Для незашифрованного HTTP порт TCP 80 сопоставляется с портом внешних веб-служб TCP 8080</span><span class="sxs-lookup"><span data-stu-id="48479-140">For unencrypted HTTP, port TCP 80 is mapped to the external web services port TCP 8080</span></span>

6.  <span data-ttu-id="48479-141">Планирование прослушивателей обратного прокси-сервера для публикации ресурсов веб-сервера</span><span class="sxs-lookup"><span data-stu-id="48479-141">Plan for reverse proxy listeners to publish web server resources</span></span>

7.  <span data-ttu-id="48479-142">Запросите и настройте сертификат для обратного прокси-сервера в соответствии со службами, которые будут предложены.</span><span class="sxs-lookup"><span data-stu-id="48479-142">Request and configure the certificate for the reverse proxy based on the services that will be offered.</span></span> <span data-ttu-id="48479-143">Если заданы правильные альтернативные имена субъектов, этот сертификат может совместно использоваться всеми настроенными прослушивателями на обратном прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="48479-143">If configured with the correct subject alternative names, this certificate can be shared by all configured listeners on the reverse proxy server</span></span>

<span data-ttu-id="48479-144">Ресурсы, доступные для планирования развертывания обратного прокси-сервера:</span><span class="sxs-lookup"><span data-stu-id="48479-144">Resources available for planning your reverse proxy deployment:</span></span>

  - [<span data-ttu-id="48479-145">Сбор данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48479-145">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="48479-146">Сводка по сертификатам — обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48479-146">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="48479-147">Сводка по портам — обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48479-147">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="48479-148">Сводка по DNS — обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48479-148">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

