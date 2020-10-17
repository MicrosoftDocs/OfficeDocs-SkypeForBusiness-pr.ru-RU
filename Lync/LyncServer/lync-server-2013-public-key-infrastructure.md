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
ms.openlocfilehash: 7cee633f877a34dcf2ec0fd0b98891c62faf0bad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512416"
---
# <a name="public-key-infrastructure-for-lync-server-2013"></a><span data-ttu-id="74c57-102">Инфраструктура открытого ключа для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74c57-102">Public Key Infrastructure for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74c57-103">_**Последнее изменение темы:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="74c57-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="74c57-104">Microsoft Lync Server 2013 использует сертификаты для проверки подлинности сервера и для создания цепочки доверия между клиентами и серверами и между разными ролями сервера.</span><span class="sxs-lookup"><span data-stu-id="74c57-104">Microsoft Lync Server 2013 relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="74c57-105">Инфраструктура открытых ключей (PKI) Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 и Windows Server 2003 (PKI) предоставляет инфраструктуру для установки и проверки этой цепи доверия.</span><span class="sxs-lookup"><span data-stu-id="74c57-105">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>

<span data-ttu-id="74c57-106">Сертификаты представляют собой цифровые идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="74c57-106">Certificates are digital IDs.</span></span> <span data-ttu-id="74c57-107">Они идентифицируют сервер по имени и указывают его свойства.</span><span class="sxs-lookup"><span data-stu-id="74c57-107">They identify a server by name and specify its properties.</span></span> <span data-ttu-id="74c57-108">Чтобы убедиться, что информация в сертификате действительна, сертификат должен быть выдан центром сертификации, который является доверенным для клиентов или других серверов, подключающихся к серверу.</span><span class="sxs-lookup"><span data-stu-id="74c57-108">To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server.</span></span> <span data-ttu-id="74c57-109">Если сервер подключается только к другим клиентам и серверам в частной сети, ЦС может быть центром сертификации предприятия.</span><span class="sxs-lookup"><span data-stu-id="74c57-109">If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA.</span></span> <span data-ttu-id="74c57-110">Если сервер взаимодействует с объектами, находящимися за прев частной сети, может потребоваться общедоступный центр сертификации.</span><span class="sxs-lookup"><span data-stu-id="74c57-110">If the server interacts with entities outside the private network, a public CA might be required.</span></span>

<span data-ttu-id="74c57-111">Даже если сведения о сертификате действительны, должен быть, чтобы убедиться, что сервер, на котором представлен сертификат, фактически является сертификатом.</span><span class="sxs-lookup"><span data-stu-id="74c57-111">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate.</span></span> <span data-ttu-id="74c57-112">Именно здесь идет инфраструктура PKI Windows.</span><span class="sxs-lookup"><span data-stu-id="74c57-112">This is where the Windows PKI comes in.</span></span>

<span data-ttu-id="74c57-113">Каждый сертификат связан с открытым ключом.</span><span class="sxs-lookup"><span data-stu-id="74c57-113">Each certificate is linked to a public key.</span></span> <span data-ttu-id="74c57-114">Сервер, указанный в сертификате, содержит соответствующий закрытый ключ, который известен только ему.</span><span class="sxs-lookup"><span data-stu-id="74c57-114">The server named on the certificate holds a corresponding private key that only it knows.</span></span> <span data-ttu-id="74c57-115">Подключаемый клиент или сервер использует открытый ключ для шифрования произвольного фрагмента данных и отправляет его на сервер.</span><span class="sxs-lookup"><span data-stu-id="74c57-115">A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server.</span></span> <span data-ttu-id="74c57-116">Если сервер расшифровывает данные и возвращает их в виде обычного текста, подключаемый объект может быть уверен, что сервер содержит закрытый ключ для сертификата, и поэтому это сервер, указанный в сертификате.</span><span class="sxs-lookup"><span data-stu-id="74c57-116">If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74c57-117">Не все общедоступные ЦС соответствуют требованиям Lync Server 2013 Certificates.</span><span class="sxs-lookup"><span data-stu-id="74c57-117">Not all public CAs comply with the requirements of Lync Server 2013 certificates.</span></span> <span data-ttu-id="74c57-118">Мы рекомендуем ознакомиться со списком сертифицированных поставщиков общедоступных центров сертификации для удовлетворения потребностей общедоступных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="74c57-118">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="74c57-119">Для получения дополнительных сведений обратитесь к партнерам по сертификации Объединенных коммуникаций <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A> .</span><span class="sxs-lookup"><span data-stu-id="74c57-119">For details, see Unified Communications Certificate Partners at <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A>.</span></span>



</div>

<div>

## <a name="crl-distribution-points"></a><span data-ttu-id="74c57-120">Точки распространения списка отзыва сертификатов</span><span class="sxs-lookup"><span data-stu-id="74c57-120">CRL Distribution Points</span></span>

<span data-ttu-id="74c57-121">Для Lync Server 2013 требуется, чтобы все сертификаты сервера содержали одну или несколько точек распространения списков отзыва сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="74c57-121">Lync Server 2013 requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="74c57-122">Точки распространения списков отзыва сертификатов (CDP) — это расположения, из которых можно скачать списки отзыва сертификатов для проверки того, что сертификат не был отозван с момента его выпуска, а сертификат все еще находится в пределах срока действия.</span><span class="sxs-lookup"><span data-stu-id="74c57-122">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="74c57-123">Точка распространения списка отзыва сертификатов указана в свойствах сертификата как URL-адрес, и обычно это безопасный HTTP.</span><span class="sxs-lookup"><span data-stu-id="74c57-123">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>

</div>

<div>

## <a name="enhanced-key-usage"></a><span data-ttu-id="74c57-124">Расширенное использование ключа</span><span class="sxs-lookup"><span data-stu-id="74c57-124">Enhanced Key Usage</span></span>

<span data-ttu-id="74c57-125">Lync Server 2013 требует, чтобы все сертификаты сервера поддерживали расширенное использование ключа (EKU) в целях проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="74c57-125">Lync Server 2013 requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="74c57-126">Настройка поля EKU для проверки подлинности сервера означает, что сертификат действителен в целях проверки подлинности серверов.</span><span class="sxs-lookup"><span data-stu-id="74c57-126">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="74c57-127">Это EKU важно для MTLS.</span><span class="sxs-lookup"><span data-stu-id="74c57-127">This EKU is essential for MTLS.</span></span> <span data-ttu-id="74c57-128">В EKU может быть несколько записей, что позволяет использовать сертификаты для нескольких целей.</span><span class="sxs-lookup"><span data-stu-id="74c57-128">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74c57-129">Для исходящих подключений MTLS от Live Communications Server 2003 и Live Communications Server 2005 необходим EKU проверки подлинности клиента, но он больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="74c57-129">The Client Authentication EKU is required for outbound MTLS connections from Live Communications Server 2003 and Live Communications Server 2005, but it is no longer required.</span></span> <span data-ttu-id="74c57-130">Однако это EKU должно присутствовать на пограничных серверах, которые подключаются к AOL с помощью общедоступной службы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="74c57-130">However, this EKU must be present on Edge Servers that connect to AOL by means of public IM connectivity.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

