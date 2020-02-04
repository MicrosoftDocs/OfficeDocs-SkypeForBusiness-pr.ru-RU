---
title: 'Lync Server 2013: требования инфраструктуры сертификатов'
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
ms.openlocfilehash: 61205cf4ecdac8eac78820442264286f414095ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="8cef2-102">Требования инфраструктуры сертификатов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cef2-102">Certificate infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cef2-103">_**Тема последнего изменения:** 2016-06-23_</span><span class="sxs-lookup"><span data-stu-id="8cef2-103">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="8cef2-104">Lync Server 2013 требует наличия инфраструктуры открытых ключей (PKI) для поддержки TLS и взаимного TLS-соединения (MTLS).</span><span class="sxs-lookup"><span data-stu-id="8cef2-104">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="8cef2-105">Lync Server использует сертификаты для следующих целей:</span><span class="sxs-lookup"><span data-stu-id="8cef2-105">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="8cef2-106">TLS соединения между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="8cef2-106">TLS connections between client and server</span></span>

  - <span data-ttu-id="8cef2-107">для подключений MTLS между серверами;</span><span class="sxs-lookup"><span data-stu-id="8cef2-107">MTLS connections between servers</span></span>

  - <span data-ttu-id="8cef2-108">для федерации с использованием автоматического обнаружения DNS партнеров;</span><span class="sxs-lookup"><span data-stu-id="8cef2-108">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="8cef2-109">для доступа удаленных пользователей к обмену мгновенными сообщениями;</span><span class="sxs-lookup"><span data-stu-id="8cef2-109">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="8cef2-110">Доступ внешних пользователей к сеансам аудио-и видеосвязи, совместному использованию приложений и конференции</span><span class="sxs-lookup"><span data-stu-id="8cef2-110">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="8cef2-111">Мобильные запросы с автоматическим обнаружением веб-служб</span><span class="sxs-lookup"><span data-stu-id="8cef2-111">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="8cef2-112">Для Lync Server применяются следующие общие требования:</span><span class="sxs-lookup"><span data-stu-id="8cef2-112">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="8cef2-113">Все сертификаты серверов должны поддерживать авторизацию сервера (EKU сервера).</span><span class="sxs-lookup"><span data-stu-id="8cef2-113">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="8cef2-114">Все сертификаты серверов должны содержать точку распространения списка отзыва сертификатов (CDP).</span><span class="sxs-lookup"><span data-stu-id="8cef2-114">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="8cef2-115">Все сертификаты должны быть подписаны с помощью алгоритма подписывания, поддерживаемого операционной системой.</span><span class="sxs-lookup"><span data-stu-id="8cef2-115">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="8cef2-116">Lync Server 2013 поддерживает наборы "SHA-1" и "SHA-2" уровней дайджеста (224, 256, 384 и 512), а также удовлетворяют требованиям или превышает требования к операционной системе.</span><span class="sxs-lookup"><span data-stu-id="8cef2-116">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="8cef2-117">Сведения о поддержке операционной системы можно [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)найти в разделе.</span><span class="sxs-lookup"><span data-stu-id="8cef2-117">For operating system support, see [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8cef2-118">Использование алгоритма подписи RSASSA-PSS не поддерживается и может привести к ошибкам при входе в систему, проблемам с переадресацией звонков и другим неполадкам.</span><span class="sxs-lookup"><span data-stu-id="8cef2-118">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="8cef2-119">Автоматическая подача заявки поддерживается для внутренних серверов, на которых работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8cef2-119">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="8cef2-120">Автоматическая подача заявки не поддерживается для серверов пограничного сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8cef2-120">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="8cef2-121">Когда вы отправляете запрос на веб-сертификат в центр сертификации Windows Server 2003, вы должны отправить его с компьютера под управлением Windows Server 2003 с пакетом обновления 2 (SP2) или Windows XP.</span><span class="sxs-lookup"><span data-stu-id="8cef2-121">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="8cef2-122">Обратите внимание, что несмотря на то, что KB922706 предоставляет поддержку для устранения проблем, связанных с регистрацией веб-сертификатов на веб-сайте службы сертификации Windows Server 2003, она не позволяет использовать Windows Server 2008, Windows Vista и Windows 7 для запроса сертификат, предоставленный центром сертификации Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="8cef2-122">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="8cef2-123">Поддерживается длина ключей шифрования в 1024, 2048 и 4096 бит.</span><span class="sxs-lookup"><span data-stu-id="8cef2-123">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="8cef2-124">Рекомендуется использовать ключи не короче 2048 бит.</span><span class="sxs-lookup"><span data-stu-id="8cef2-124">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="8cef2-125">По умолчанию используется дайджест-алгоритм (алгоритм хэширования и подписывания) RSA.</span><span class="sxs-lookup"><span data-stu-id="8cef2-125">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="8cef2-126">Также поддерживаются\_алгоритмы\_ECDH P256, ECDH\_P384 и ECDH P521.</span><span class="sxs-lookup"><span data-stu-id="8cef2-126">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="8cef2-127">Содержание</span><span class="sxs-lookup"><span data-stu-id="8cef2-127">In This Section</span></span>

  - [<span data-ttu-id="8cef2-128">Требования к сертификатам для внутренних серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cef2-128">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="8cef2-129">Требования к сертификатам для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cef2-129">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="8cef2-130">Требования к сертификатам для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cef2-130">Certificate requirements for Persistent Chat server in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="8cef2-131">Требования к сертификатам для организации мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cef2-131">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

