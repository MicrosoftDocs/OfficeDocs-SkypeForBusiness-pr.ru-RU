---
title: 'Lync Server 2013: требования к конфигурации для обратного прокси-сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0367ea79a0f3de6ad716f18aab980e9d9442e148
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="39000-102">Требования к конфигурации для обратного прокси-сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39000-102">Configuration requirements for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39000-103">_**Тема последнего изменения:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="39000-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="39000-104">Lync Server 2013 накладывает некоторые требования на обмен данными из внешнего клиента, которые затем передаются во внешние веб-службы, размещенные в директории, пуле, сервере переднего плана, внешнем и внешнем интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="39000-104">Lync Server 2013 imposes a few requirements on communications from the external client that are then passed on to the external Web services hosted on the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="39000-105">Обратный прокси-сервер также отвечает за публикацию сервера Office Web Apps, если вы предлагаете Конференц-связь с пользователями.</span><span class="sxs-lookup"><span data-stu-id="39000-105">The reverse proxy is also responsible for publishing the Office Web Apps Server, if you are offering conferencing to your users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="39000-106">Lync Server 2013 не указывает конкретный обратный прокси-сервер, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="39000-106">Lync Server 2013 does not specify a particular reverse proxy that you must use.</span></span> <span data-ttu-id="39000-107">Lync Server 2013 определяет операционные требования, которые должны быть доступны для обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="39000-107">Lync Server 2013 only defines operational requirements that the reverse proxy must be able to do.</span></span> <span data-ttu-id="39000-108">Обычно обратный прокси-сервер, который вы уже развернули в вашей инфраструктуре, может соответствовать требованиям.</span><span class="sxs-lookup"><span data-stu-id="39000-108">Typically, the reverse proxy that you already have deployed in your infrastructure may be able to meet the requirements.</span></span>



</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="39000-109">Обратные требования прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="39000-109">Reverse Proxy Requirements</span></span>

<span data-ttu-id="39000-110">Для выполнения функциональных операций, которые Lync Server 2013 ожидает обратного прокси-сервера, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="39000-110">The functional operations that Lync Server 2013 expect a reverse proxy to perform are:</span></span>

  - <span data-ttu-id="39000-111">Используйте протоколы SSL и TLS, реализованные с помощью сертификатов, полученных от общедоступного центра сертификации, для подключения к опубликованным внешним веб-службам директора, режиссерского пула, сервера переднего плана или пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="39000-111">Use secure socket layer (SSL) and transport layer security (TLS) implemented by using certificates acquired from a public certification authority to connect to the published external Web services of the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="39000-112">Руководитель и сервер переднего плана могут находиться в пуле с балансировкой нагрузки, используя балансировщик нагрузки оборудования.</span><span class="sxs-lookup"><span data-stu-id="39000-112">The Director and the Front End Server can be in a load-balanced pool by using hardware load balancers.</span></span>

  - <span data-ttu-id="39000-113">Возможность публиковать внутренние веб-сайты с помощью сертификатов для шифрования или публиковать их в незашифрованном виде, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="39000-113">Able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>

  - <span data-ttu-id="39000-114">Возможность публикации внутренних размещенных веб-сайтов извне с помощью полного доменного имени (FQDN).</span><span class="sxs-lookup"><span data-stu-id="39000-114">Able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>

  - <span data-ttu-id="39000-115">Возможность публикации всего содержимого размещенного веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="39000-115">Able to publish all contents of the hosted web site.</span></span> <span data-ttu-id="39000-116">По умолчанию \*\* / \*\* директива, которая распознается большинством веб-серверов, может означать "опубликовать все содержимое на веб-сервере".</span><span class="sxs-lookup"><span data-stu-id="39000-116">By default, you can use the **/\*** directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="39000-117">Вы также можете изменить директиву (например, **/увка/\***), что означает "опубликовать все содержимое в виртуальном каталоге Уква".</span><span class="sxs-lookup"><span data-stu-id="39000-117">You can also modify the directive—for example, **/Uwca/\***, which means "Publish all content under the virtual directory Ucwa."</span></span>

  - <span data-ttu-id="39000-118">Необходимо настроить для использования подключений SSL и TLS с клиентами, которые запрашивают контент с опубликованного веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="39000-118">Must be configurable to require Secure Sockets Layer (SSL) and/or Transport Layer Security (TLS) connections with clients that request content from a published website.</span></span>

  - <span data-ttu-id="39000-119">Необходимо сохранить сертификаты с записями в альтернативном имени субъекта (SAN).</span><span class="sxs-lookup"><span data-stu-id="39000-119">Must accept certificates with subject alternative name (SAN) entries.</span></span>

  - <span data-ttu-id="39000-120">Должна иметь возможность привязать сертификат к прослушивателю или интерфейсу, с помощью которого будет разрешено полное доменное имя внешней веб-службы.</span><span class="sxs-lookup"><span data-stu-id="39000-120">Must be able to allow binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="39000-121">Конфигурации с прослушивателями предпочтительнее конфигураций с интерфейсами.</span><span class="sxs-lookup"><span data-stu-id="39000-121">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="39000-122">Для одного интерфейса можно настроить несколько прослушивателей.</span><span class="sxs-lookup"><span data-stu-id="39000-122">Many listeners can be configured on a single interface.</span></span>

  - <span data-ttu-id="39000-123">Требуется разрешение на настройку обработки заголовков узлов.</span><span class="sxs-lookup"><span data-stu-id="39000-123">Must allow for the configuration of host header handling.</span></span> <span data-ttu-id="39000-124">Часто первоначальный заголовок узла, отправленный запрашивающим клиентом, должен быть передан прозрачным, а не изменен обратной прокси-сервером.</span><span class="sxs-lookup"><span data-stu-id="39000-124">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>

  - <span data-ttu-id="39000-125">Подмостировать трафик SSL и TLS от одного внешнего порта (например, TCP 443) к другому определенному порту (например, TCP 4443).</span><span class="sxs-lookup"><span data-stu-id="39000-125">Bridging of SSL and TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="39000-126">Обратный прокси-сервер может расшифровать полученный пакет и затем повторно зашифровать пакет при отправке.</span><span class="sxs-lookup"><span data-stu-id="39000-126">The reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>

  - <span data-ttu-id="39000-127">Обмен незашифрованным трафиком TCP от одного порта (например, TCP 80) к другому (например, TCP 8080).</span><span class="sxs-lookup"><span data-stu-id="39000-127">Bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>

  - <span data-ttu-id="39000-128">Разрешение проверки подлинности NTLM и проверки подлинности, а также сквозной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="39000-128">Allow configuration of, or accept, NTLM authentication, No authentication and Pass-through authentication.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

