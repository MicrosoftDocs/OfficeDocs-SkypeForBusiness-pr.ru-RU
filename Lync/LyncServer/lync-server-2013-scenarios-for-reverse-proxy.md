---
title: 'Lync Server 2013: сценарии для обратного прокси-сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1621e8bb0241e82f9f4678d4fe39a4f66f6bcf9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="4fdf8-102">Сценарии для обратного прокси-сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fdf8-102">Scenarios for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fdf8-103">_**Тема последнего изменения:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="4fdf8-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="4fdf8-104">Обратные прокси-серверы требуются в Lync Server 2013 для предоставления доступа к службам и ресурсам, таким как собрания и простые URL-адреса, адресная книга, содержимое собрания, расширение списка рассылки, Услуги мобильной связи и другие.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-104">Reverse proxies are required in Lync Server 2013 for providing access to services and resources such as the meeting and dial-in Simple URLs, address book, meeting content, distribution list expansion, mobility services, and others.</span></span> <span data-ttu-id="4fdf8-105">Типичный сценарий обратной связи в Lync Server 2013 состоит в том, чтобы разрешить внешним клиентам (например, клиенту для настольных систем или Lync Web App) доступ к внешним веб-службам режиссера или внешнего сервера.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-105">The typical reverse proxy scenario in Lync Server 2013 is to allow external clients (for example, the desktop client or Lync Web App client) access to the Director or Front End Server external Web Services.</span></span>

<span data-ttu-id="4fdf8-106">**Обратные прокси-и внешние веб-службы**</span><span class="sxs-lookup"><span data-stu-id="4fdf8-106">**Reverse proxy and external web services**</span></span>

<span data-ttu-id="4fdf8-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c] (images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="4fdf8-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>

<span data-ttu-id="4fdf8-108">На этапе планирования вы определяете требования для обратного прокси-сервера в развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-108">During the planning phase, you define the requirements for the reverse proxy in a Lync Server 2013 deployment.</span></span> <span data-ttu-id="4fdf8-109">Обратный прокси обеспечивает доступ к функциям для следующих внешних клиентов:</span><span class="sxs-lookup"><span data-stu-id="4fdf8-109">The reverse proxy enables access to features for the following external clients:</span></span>

  - <span data-ttu-id="4fdf8-110">Клиент Microsoft Lync 2013 для настольных компьютеров</span><span class="sxs-lookup"><span data-stu-id="4fdf8-110">Microsoft Lync 2013 desktop client</span></span>

  - <span data-ttu-id="4fdf8-111">Microsoft Lync Web App</span><span class="sxs-lookup"><span data-stu-id="4fdf8-111">Microsoft Lync Web App</span></span>

  - <span data-ttu-id="4fdf8-112">Microsoft Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="4fdf8-112">Microsoft Lync Mobile</span></span>

  - <span data-ttu-id="4fdf8-113">Магазина Lync Windows</span><span class="sxs-lookup"><span data-stu-id="4fdf8-113">Lync Windows Store app</span></span>

<span data-ttu-id="4fdf8-114">При планировании развертывания Lync Server 2013 вы сопоставляете фактические требования для Lync Server 2013 с обратной функциональностью прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-114">When planning your Lync Server 2013 deployment, you map the actual requirements for Lync Server 2013 to the reverse proxy features.</span></span>

1.  <span data-ttu-id="4fdf8-115">Внешние клиенты будут подключаться к обратному прокси-серверу порта TCP 443 и будут использовать протокол SSL или TLS.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-115">External clients will connect to the reverse proxy on port TCP 443 and will use secure socket layer (SSL) or transport layer security (TLS).</span></span> <span data-ttu-id="4fdf8-116">Мобильные клиенты Microsoft Lync могут подключаться к порту TCP 80, но только при первоначальном подключении к службам Lync Discover, если администратор настроил соответствующие записи CNAME (или псевдонима) DNS) и принимает этот связь не будет зашифрована.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-116">Microsoft Lync Mobile clients can connect on port TCP 80, but only when performing the initial connection to the Lync discover services and the administrator has configured the proper domain name system (DNS) CNAME (or alias) records, and accepts that this communication will not be encrypted.</span></span>

2.  <span data-ttu-id="4fdf8-117">Внешние веб-службы Lync Server 2013 (развернутые на сервере переднего плана и/или в директории) ожидают подключения через обратный прокси для порта TCP 4443 и ожидает, что соединение будет SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-117">Lync Server 2013 external web services (deployed on the Front End Server and/or the Director) expect a connection from a reverse proxy on port TCP 4443, and it expects that the connection will be SSL/TLS.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4fdf8-118">Предлагаемые по умолчанию порты прослушивания внешних веб-служб: TCP 8080 для HTTP и трафик TCP 4443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-118">The suggested default listening ports for the external web services are TCP 8080 for HTTP traffic, and TCP 4443 for HTTPS traffic.</span></span> <span data-ttu-id="4fdf8-119">В построителе топологии можно переопределить значения по умолчанию и определить собственные порты прослушивания для внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-119">Topology Builder provides an opportunity to override the defaults and define your own listening ports for the external web services.</span></span> <span data-ttu-id="4fdf8-120">Важно отметить, что обратный прокси-сервер взаимодействует с внешними веб-службами, и внешние клиенты взаимодействуют с обратным прокси.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-120">It’s important to note that the reverse proxy communicates with the external web services, and the external clients communicate with the reverse proxy.</span></span> <span data-ttu-id="4fdf8-121">Внешний клиент взаимодействует с обратным прокси-сервером по порту TCP 443, но вы можете переопределить порт, на который будет взаимодействовать обратное прокси-сервер с внешними веб-службами.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-121">The external client communicates with the reverse proxy on port TCP 443, but you can redefine what port the reverse proxy communicates with the external web services on.</span></span> <span data-ttu-id="4fdf8-122">Параметры в построителе топологии для переопределения портов прослушивания по умолчанию для веб-служб позволяют устранить конфликты с портом прослушивания, которые могут возникать в вашей инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-122">The options in Topology Builder to override the default listening ports for the web services allows you to resolve listening port conflicts that may arise in your infrastructure.</span></span>

    
    </div>

3.  <span data-ttu-id="4fdf8-123">Внешние веб-службы Lync Server 2013 для определения того, какая служба и каталог веб-сервера пытается использовать клиент, требуется неизмененный заголовок узла от клиента.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-123">Lync Server 2013 external web services expect an unmodified Host Header from the client to identify what service and web server directory the client is attempting to use.</span></span> <span data-ttu-id="4fdf8-124">Запросы должны выглядеть так, как если бы они были на обратном прокси</span><span class="sxs-lookup"><span data-stu-id="4fdf8-124">Requests should appear as if they came from the reverse proxy</span></span>

4.  <span data-ttu-id="4fdf8-125">Внешние веб-службы используют определенные виртуальные каталоги веб-сервера (Вдир), предоставляющие услуги, предоставляемые клиентам.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-125">The external web services use defined web server virtual directories (vDir) that provide the services offered to clients.</span></span> <span data-ttu-id="4fdf8-126">Ниже указаны специальные веб-службы с внешними идентификациями.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-126">Specific externally identifiable web services are:</span></span>
    
      - <span data-ttu-id="4fdf8-127">"Встреча" Вдир для собраний веб-конференций</span><span class="sxs-lookup"><span data-stu-id="4fdf8-127">The “Meet” vDir for web conference meetings</span></span>
    
      - <span data-ttu-id="4fdf8-128">"Dial-in Вдир для телефонного доступа и телефонной конференции"</span><span class="sxs-lookup"><span data-stu-id="4fdf8-128">The “Dialin” vDir for phone access and phone conferencing</span></span>
    
      - <span data-ttu-id="4fdf8-129">"Автообнаружения" Вдир для приложения Lync из Магазина Windows, Lync Mobile и настольного клиента Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-129">The “Autodiscover” vDir for Lync Windows Store app, Lync Mobile, and the desktop client Lync 2013.</span></span> <span data-ttu-id="4fdf8-130">Служба автообнаружения в Lync Server 2013 известна под DNS-именем "lyncdiscover"</span><span class="sxs-lookup"><span data-stu-id="4fdf8-130">Autodiscover in Lync Server 2013 is known by the DNS name “lyncdiscover”</span></span>
    
      - <span data-ttu-id="4fdf8-131">Внешние клиенты получают доступ к неопределенным службам через прямые звонки на внешние веб-службы.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-131">Services not defined are accessed by the external client by direct calls to the external web services.</span></span> <span data-ttu-id="4fdf8-132">Например, разворачивание группы рассылки (ДЛКС) и обращение к службе адресной книги (ABS) осуществляется прямым звонком на внешние веб-службы и связанные Вдирс.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-132">For example, distribution group expansion (DLX) and the address book service (ABS) are accessed by direct calls to the external web services and associated vDirs.</span></span> <span data-ttu-id="4fdf8-133">Клиент знает фактический путь к Вдир и конструирует URL-адрес на основе этих данных.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-133">The client knows the actual path to the vDir and constructs a uniform record locator (URL) based on this information.</span></span> <span data-ttu-id="4fdf8-134">Клиент попытается получить доступ к службе адресной книги, используя URL-адрес, похожий на`https://externalweb.contoso.com/abs/handler`</span><span class="sxs-lookup"><span data-stu-id="4fdf8-134">The client would access the address book service using a URL similar to `https://externalweb.contoso.com/abs/handler`</span></span>
    
      - <span data-ttu-id="4fdf8-135">Сервер Office Web Apps, на котором определена и настроена конференция в рамках топологии сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-135">The Office Web Apps Server when conferencing is defined and configured as part of the Lync Server topology</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="4fdf8-136">Сервер Office Web Apps — это отдельный сервер ролей, который не настроен как часть внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-136">The Office Web Apps Server is a separate role server and is not configured as part of the external web services.</span></span> <span data-ttu-id="4fdf8-137">Этот сервер опубликован отдельно для клиентского доступа.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-137">This server is separately published for client access.</span></span>

        
        </div>

5.  <span data-ttu-id="4fdf8-138">Определите мост SSL для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-138">Define SSL bridging for each service.</span></span> <span data-ttu-id="4fdf8-139">Внешний порт TCP 443 сопоставлен с портом внешней веб-службы TCP 4443.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-139">The external port TCP 443 is mapped to the external web services port of TCP 4443.</span></span> <span data-ttu-id="4fdf8-140">Для незашифрованного HTTP порт TCP 80 сопоставлен с портом внешней веб-службы TCP 8080</span><span class="sxs-lookup"><span data-stu-id="4fdf8-140">For unencrypted HTTP, port TCP 80 is mapped to the external web services port TCP 8080</span></span>

6.  <span data-ttu-id="4fdf8-141">Планирование обратного прокси-прослушивателей для публикации ресурсов веб-сервера</span><span class="sxs-lookup"><span data-stu-id="4fdf8-141">Plan for reverse proxy listeners to publish web server resources</span></span>

7.  <span data-ttu-id="4fdf8-142">Запросите и настройте сертификат для обратного прокси-сервера в соответствии со службами, которые будут предложены.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-142">Request and configure the certificate for the reverse proxy based on the services that will be offered.</span></span> <span data-ttu-id="4fdf8-143">Если параметр настроен с правильными альтернативными именами субъектов, этот сертификат может быть общим для всех настроенных прослушивателей на обратном прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-143">If configured with the correct subject alternative names, this certificate can be shared by all configured listeners on the reverse proxy server</span></span>

<span data-ttu-id="4fdf8-144">Ресурсы, доступные для планирования обратной конфигурации прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-144">Resources available for planning your reverse proxy deployment:</span></span>

  - [<span data-ttu-id="4fdf8-145">Сбор данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fdf8-145">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="4fdf8-146">Сводка по сертификатам — обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fdf8-146">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="4fdf8-147">Сводка по портам — обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fdf8-147">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="4fdf8-148">Сводка по DNS — обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fdf8-148">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

