---
title: Требования к инфраструктуре сертификатов Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dd1aa5bdde1c94e3d0558be14c67cf62ec8142a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="ffbdd-102">Требования к инфраструктуре сертификатов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffbdd-102">Certificate infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffbdd-103">_**Последнее изменение темы:** 2016-06-23_</span><span class="sxs-lookup"><span data-stu-id="ffbdd-103">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="ffbdd-104">Lync Server 2013 требует наличия инфраструктуры открытых ключей (PKI) для поддержки подключений TLS и взаимного TLS (MTLS).</span><span class="sxs-lookup"><span data-stu-id="ffbdd-104">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="ffbdd-105">Lync Server использует сертификаты для следующих целей:</span><span class="sxs-lookup"><span data-stu-id="ffbdd-105">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="ffbdd-106">для подключений TLS между клиентом и сервером;</span><span class="sxs-lookup"><span data-stu-id="ffbdd-106">TLS connections between client and server</span></span>

  - <span data-ttu-id="ffbdd-107">для подключений MTLS между серверами;</span><span class="sxs-lookup"><span data-stu-id="ffbdd-107">MTLS connections between servers</span></span>

  - <span data-ttu-id="ffbdd-108">для федерации с использованием автоматического обнаружения DNS партнеров;</span><span class="sxs-lookup"><span data-stu-id="ffbdd-108">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="ffbdd-109">для доступа удаленных пользователей к обмену мгновенными сообщениями;</span><span class="sxs-lookup"><span data-stu-id="ffbdd-109">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="ffbdd-110">для доступа внешних пользователей к сеансам аудио- и видеосвязи, к приложениям с общим доступом и к конференц-связи;</span><span class="sxs-lookup"><span data-stu-id="ffbdd-110">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="ffbdd-111">для мобильных запросов с использованием автоматического обнаружения веб-служб.</span><span class="sxs-lookup"><span data-stu-id="ffbdd-111">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="ffbdd-112">Для Lync Server применяются следующие общие требования:</span><span class="sxs-lookup"><span data-stu-id="ffbdd-112">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="ffbdd-113">Все сертификаты серверов должны поддерживать авторизацию сервера (EKU сервера).</span><span class="sxs-lookup"><span data-stu-id="ffbdd-113">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="ffbdd-114">Все сертификаты серверов должны содержать точку распространения списка отзыва сертификатов (CDP).</span><span class="sxs-lookup"><span data-stu-id="ffbdd-114">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="ffbdd-115">Все сертификаты должны быть подписаны с помощью алгоритма подписи, поддерживаемого операционной системой.</span><span class="sxs-lookup"><span data-stu-id="ffbdd-115">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="ffbdd-116">Lync Server 2013 поддерживает набор размеров дайджеста SHA-1 и SHA-2 (224, 256, 384 и 512), а также отвечает или превышает требования к операционной системе.</span><span class="sxs-lookup"><span data-stu-id="ffbdd-116">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="ffbdd-117">Сведения о поддержке операционной системы приведены [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002)в разделе.</span><span class="sxs-lookup"><span data-stu-id="ffbdd-117">For operating system support, see [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ffbdd-118">Использование алгоритма подписи RSASSA-PSS не поддерживается и может привести к ошибкам при входе в систему и переадресации вызовов, среди прочих проблем.</span><span class="sxs-lookup"><span data-stu-id="ffbdd-118">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="ffbdd-119">Автоматическая регистрация поддерживается для внутренних серверов, на которых работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ffbdd-119">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="ffbdd-120">Автоматическая регистрация не поддерживается для пограничных серверов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ffbdd-120">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="ffbdd-121">Запрос на сертификат через Интернет в центр сертификации Windows Server 2003 необходимо подавать с компьютера, работающего под управлением либо Windows Server 2003 с пакетом обновления 2 (SP2), либо Windows XP.</span><span class="sxs-lookup"><span data-stu-id="ffbdd-121">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="ffbdd-122">Следует отметить, что хотя в статье базы знаний KB922706 предоставляется поддержка для разрешения проблем с регистрацией сертификатов через Интернет с помощью служб сертификатов Windows Server 2003, она не делает возможным запрос сертификата в ЦС Windows Server 2003 с использованием Windows Server 2008, Windows Vista или Windows 7.</span><span class="sxs-lookup"><span data-stu-id="ffbdd-122">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="ffbdd-123">Поддерживаются длины ключей шифрования 1024, 2048 и 4096.</span><span class="sxs-lookup"><span data-stu-id="ffbdd-123">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="ffbdd-124">Рекомендуется использовать ключи длиной 2048 и выше.</span><span class="sxs-lookup"><span data-stu-id="ffbdd-124">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="ffbdd-125">Для дайджеста по умолчанию или хэш-подписи используется алгоритм RSA.</span><span class="sxs-lookup"><span data-stu-id="ffbdd-125">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="ffbdd-126">Также поддерживаются\_алгоритмы\_ECDH P256, ECDH\_P384 и ECDH P521.</span><span class="sxs-lookup"><span data-stu-id="ffbdd-126">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="ffbdd-127">Содержание</span><span class="sxs-lookup"><span data-stu-id="ffbdd-127">In This Section</span></span>

  - [<span data-ttu-id="ffbdd-128">Требования к сертификатам для внутренних серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffbdd-128">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="ffbdd-129">Требования к сертификатам для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffbdd-129">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="ffbdd-130">Требования к сертификатам для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffbdd-130">Certificate requirements for Persistent Chat server in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="ffbdd-131">Требования к сертификатам для мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffbdd-131">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

