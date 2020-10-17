---
title: 'Lync Server 2013: требования к конфигурации для обратного прокси-сервера'
description: 'Lync Server 2013: требования к конфигурации для обратного прокси-сервера.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75f3f5b9437ba4518e3feffc193853b446b702d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552145"
---
# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="3da0a-103">Требования к конфигурации для обратного прокси-сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3da0a-103">Configuration requirements for reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3da0a-104">_**Последнее изменение темы:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="3da0a-104">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="3da0a-105">Lync Server 2013 накладывает ряд требований к взаимодействию с внешними клиентами, которые затем передаются внешним веб-службам, размещенным на директоре, директоре пула, сервере переднего плана или интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="3da0a-105">Lync Server 2013 imposes a few requirements on communications from the external client that are then passed on to the external Web services hosted on the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="3da0a-106">Обратный прокси-сервер также отвечает за публикацию сервера Office Web Apps, если вы предлагаете Конференц-связь пользователям.</span><span class="sxs-lookup"><span data-stu-id="3da0a-106">The reverse proxy is also responsible for publishing the Office Web Apps Server, if you are offering conferencing to your users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3da0a-107">Lync Server 2013 не указывает конкретный обратный прокси, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="3da0a-107">Lync Server 2013 does not specify a particular reverse proxy that you must use.</span></span> <span data-ttu-id="3da0a-108">Lync Server 2013 определяет операционные требования, которые должны быть доступны для обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="3da0a-108">Lync Server 2013 only defines operational requirements that the reverse proxy must be able to do.</span></span> <span data-ttu-id="3da0a-109">Обычно обратный прокси-сервер, который уже был развернут в вашей инфраструктуре, может соответствовать требованиям.</span><span class="sxs-lookup"><span data-stu-id="3da0a-109">Typically, the reverse proxy that you already have deployed in your infrastructure may be able to meet the requirements.</span></span>



</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="3da0a-110">Требования к обратному прокси-серверу</span><span class="sxs-lookup"><span data-stu-id="3da0a-110">Reverse Proxy Requirements</span></span>

<span data-ttu-id="3da0a-111">Функциональные операции, которые Lync Server 2013 ожидает выполнения обратного прокси-сервера:</span><span class="sxs-lookup"><span data-stu-id="3da0a-111">The functional operations that Lync Server 2013 expect a reverse proxy to perform are:</span></span>

  - <span data-ttu-id="3da0a-112">Используйте протокол SSL и протокол TLS, реализованные с помощью сертификатов, полученных от общедоступного центра сертификации, для подключения к опубликованным внешним веб-службам директора, пула директоров, сервера переднего плана или пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="3da0a-112">Use secure socket layer (SSL) and transport layer security (TLS) implemented by using certificates acquired from a public certification authority to connect to the published external Web services of the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="3da0a-113">Директор и сервер переднего плана могут находиться в пуле с балансировкой нагрузки с помощью аппаратных подсистем балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="3da0a-113">The Director and the Front End Server can be in a load-balanced pool by using hardware load balancers.</span></span>

  - <span data-ttu-id="3da0a-114">Возможность публиковать внутренние веб-сайты с помощью сертификатов для шифрования или при необходимости публиковать их по незашифрованным средствам.</span><span class="sxs-lookup"><span data-stu-id="3da0a-114">Able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>

  - <span data-ttu-id="3da0a-115">Возможность внутренней публикации внутреннего размещенного веб-сайта с использованием полного доменного имени (FQDN).</span><span class="sxs-lookup"><span data-stu-id="3da0a-115">Able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>

  - <span data-ttu-id="3da0a-116">Возможность публикации всего содержимого размещенного веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="3da0a-116">Able to publish all contents of the hosted web site.</span></span> <span data-ttu-id="3da0a-117">По умолчанию **/\*** директиву, которая распознается большинством веб-серверов, можно использовать для обозначения "опубликовать все содержимое на веб-сервере".</span><span class="sxs-lookup"><span data-stu-id="3da0a-117">By default, you can use the **/\*** directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="3da0a-118">Кроме того, можно изменить директиву (например, \*\*/увка/ \* \*\*), что означает "опубликовать весь контент в виртуальном каталоге Ucwa".</span><span class="sxs-lookup"><span data-stu-id="3da0a-118">You can also modify the directive—for example, **/Uwca/\***, which means "Publish all content under the virtual directory Ucwa."</span></span>

  - <span data-ttu-id="3da0a-119">Необходимо настроить для использования подключений SSL и/или TLS с клиентами, которые запрашивают контент с опубликованного веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="3da0a-119">Must be configurable to require Secure Sockets Layer (SSL) and/or Transport Layer Security (TLS) connections with clients that request content from a published website.</span></span>

  - <span data-ttu-id="3da0a-120">Должны принимать сертификаты с записями альтернативного имени субъекта (SAN).</span><span class="sxs-lookup"><span data-stu-id="3da0a-120">Must accept certificates with subject alternative name (SAN) entries.</span></span>

  - <span data-ttu-id="3da0a-121">Должна иметь возможность разрешить привязку сертификата к прослушивателю или интерфейсу, через который будет разрешаться полное доменное имя внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="3da0a-121">Must be able to allow binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="3da0a-122">Конфигурации прослушивателя предпочтительны для интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="3da0a-122">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="3da0a-123">Для одного интерфейса можно настроить множество прослушивателей.</span><span class="sxs-lookup"><span data-stu-id="3da0a-123">Many listeners can be configured on a single interface.</span></span>

  - <span data-ttu-id="3da0a-124">Необходимо разрешить настройку обработки заголовков узлов.</span><span class="sxs-lookup"><span data-stu-id="3da0a-124">Must allow for the configuration of host header handling.</span></span> <span data-ttu-id="3da0a-125">Часто исходный заголовок узла, отправленный запрашивающим клиентом, необходимо передавать прозрачным, а не изменять обратном прокси-сервером.</span><span class="sxs-lookup"><span data-stu-id="3da0a-125">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>

  - <span data-ttu-id="3da0a-126">Помостить трафик SSL и TLS с одного порта, определенного извне (например, TCP 443), на другой определенный порт (например, TCP 4443).</span><span class="sxs-lookup"><span data-stu-id="3da0a-126">Bridging of SSL and TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="3da0a-127">Обратный прокси-сервер может расшифровать полученный пакет и затем повторно зашифровать пакет при отправке.</span><span class="sxs-lookup"><span data-stu-id="3da0a-127">The reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>

  - <span data-ttu-id="3da0a-128">Примостить незашифрованный TCP-трафик с одного порта (например, TCP 80) к другому (например, TCP 8080).</span><span class="sxs-lookup"><span data-stu-id="3da0a-128">Bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>

  - <span data-ttu-id="3da0a-129">Разрешите настройку, или принятие, проверку подлинности NTLM, без проверки подлинности и сквозной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="3da0a-129">Allow configuration of, or accept, NTLM authentication, No authentication and Pass-through authentication.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

