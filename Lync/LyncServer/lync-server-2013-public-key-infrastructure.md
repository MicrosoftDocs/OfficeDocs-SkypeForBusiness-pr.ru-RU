---
title: 'Lync Server 2013: инфраструктура открытых ключей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b205699e9efd896a157654f5c1fb200e34087fc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a><span data-ttu-id="e6712-102">Инфраструктура открытых ключей для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6712-102">Public Key Infrastructure for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6712-103">_**Тема последнего изменения:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="e6712-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="e6712-104">Microsoft Lync Server 2013 использует сертификаты для проверки подлинности сервера и для создания цепочки доверия между клиентами и серверами, а также между разными серверными ролями.</span><span class="sxs-lookup"><span data-stu-id="e6712-104">Microsoft Lync Server 2013 relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="e6712-105">Инфраструктура открытых ключей (PKI) для Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 и Windows Server 2003 обеспечивает инфраструктуру для установления и проверки подлинности этой цепочки доверия.</span><span class="sxs-lookup"><span data-stu-id="e6712-105">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>

<span data-ttu-id="e6712-p102">Сертификаты представляют собой цифровые идентификаторы. Они определяют сервер по имени и указывают его свойства. Для обеспечения действительности сведений сертификата он должен быть выдан ЦС, которому доверяют подключенные к серверу клиенты и другие серверы. Если сервер подключается только к другим клиентам и серверам в частной сети, ЦС может являться корпоративным ЦС. Если сервер взаимодействует с объектами за пределами частной сети, может потребоваться общедоступный ЦС.</span><span class="sxs-lookup"><span data-stu-id="e6712-p102">Certificates are digital IDs. They identify a server by name and specify its properties. To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server. If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA. If the server interacts with entities outside the private network, a public CA might be required.</span></span>

<span data-ttu-id="e6712-p103">Даже при условии действительности сведений сертификата необходим способ проверки того, что представляющий сертификат сервер фактически является тем, который представлен сертификатом. Именно в этом случае используется Windows PKI.</span><span class="sxs-lookup"><span data-stu-id="e6712-p103">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in.</span></span>

<span data-ttu-id="e6712-p104">Каждый сертификат связан с открытым ключом. Сервер, который указан в сертификате, содержит соответствующий известный только ему закрытый ключ. Подключаемый клиент или сервер использует открытый ключ для шифрования произвольной части сведений и отправляет его на сервер. Если сервер расшифровывает эти сведения и возвращает их в виде обычного текста, подключаемый объект может быть уверен в том, что сервер содержит закрытый ключ для сертификата и, следовательно, является указанным в сертификате сервером.</span><span class="sxs-lookup"><span data-stu-id="e6712-p104">Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e6712-117">Не все общедоступные ЦС соответствуют требованиям, предъявляемым к Lync Server 2013 Certificates.</span><span class="sxs-lookup"><span data-stu-id="e6712-117">Not all public CAs comply with the requirements of Lync Server 2013 certificates.</span></span> <span data-ttu-id="e6712-118">Мы рекомендуем ознакомиться со списком сертифицированных поставщиков общедоступных ЦС для получения сведений о требованиях общих сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e6712-118">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="e6712-119">Дополнительные сведения можно найти в разделе Партнеры по <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>сертификатам единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e6712-119">For details, see Unified Communications Certificate Partners at <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>.</span></span>



</div>

<div>

## <a name="crl-distribution-points"></a><span data-ttu-id="e6712-120">Точки распространения списка отзыва сертификатов (CRL)</span><span class="sxs-lookup"><span data-stu-id="e6712-120">CRL Distribution Points</span></span>

<span data-ttu-id="e6712-121">Для Lync Server 2013 требуется, чтобы все сертификаты сервера содержали одну или несколько точек распространения списков отзыва сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="e6712-121">Lync Server 2013 requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="e6712-122">Точки распространения списка отзыва сертификатов (CDP) представляют собой местоположения, из которых можно загрузить CRL для проверки того, что сертификат не был отозван с момента выдачи и его срок действия не истек.</span><span class="sxs-lookup"><span data-stu-id="e6712-122">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="e6712-123">Точка распространения списка отзыва сертификатов CRL указывается в свойствах сертификата в виде URL-адреса и обычно является безопасным протоколом HTTP.</span><span class="sxs-lookup"><span data-stu-id="e6712-123">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>

</div>

<div>

## <a name="enhanced-key-usage"></a><span data-ttu-id="e6712-124">Расширенное использование ключа</span><span class="sxs-lookup"><span data-stu-id="e6712-124">Enhanced Key Usage</span></span>

<span data-ttu-id="e6712-125">В Lync Server 2013 для проверки подлинности сервера требуется, чтобы все сертификаты сервера поддерживали использование расширенного ключа (EKU).</span><span class="sxs-lookup"><span data-stu-id="e6712-125">Lync Server 2013 requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="e6712-126">Настройка поля EKU для проверки подлинности сервера означает, что сертификат действителен для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="e6712-126">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="e6712-127">Использование EKU важно для MTLS.</span><span class="sxs-lookup"><span data-stu-id="e6712-127">This EKU is essential for MTLS.</span></span> <span data-ttu-id="e6712-128">Можно иметь более одной записи в EKU, что позволяет использовать сертификат в нескольких целях.</span><span class="sxs-lookup"><span data-stu-id="e6712-128">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e6712-129">EKU для проверки подлинности клиента требуется для исходящих подключений MTLS от сервера Live Communications Server 2003 и Live Communications Server 2005, но его больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="e6712-129">The Client Authentication EKU is required for outbound MTLS connections from Live Communications Server 2003 and Live Communications Server 2005, but it is no longer required.</span></span> <span data-ttu-id="e6712-130">Однако это EKU должно быть представлено на пограничных серверах, которые подключаются к AOL с помощью общедоступной службы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e6712-130">However, this EKU must be present on Edge Servers that connect to AOL by means of public IM connectivity.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

