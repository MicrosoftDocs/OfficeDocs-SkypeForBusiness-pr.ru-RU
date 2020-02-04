---
title: 'Lync Server 2013: запрос сертификатов для пограничных компонентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 096603b48e6a3636a397c4abf7c19c2b4237f132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="948fe-102">Запрос сертификатов для пограничных компонентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="948fe-102">Request certificates for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="948fe-103">_**Тема последнего изменения:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="948fe-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="948fe-104">Сертификаты, необходимые для поддержки внешних пользователей, включают сертификаты, выданные общедоступным центром сертификации (ЦС), и сертификаты, выданные внутренним центром сертификации предприятия.</span><span class="sxs-lookup"><span data-stu-id="948fe-104">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="948fe-105">Сертификаты, необходимые для внешнего интерфейса пограничного сервера и обратного прокси-сервера, должны быть выпущены общедоступным центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="948fe-105">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="948fe-106">Сертификаты, необходимые для внутреннего интерфейса, могут быть выданы либо общедоступным центром сертификации, либо внутренним центром сертификации предприятия.</span><span class="sxs-lookup"><span data-stu-id="948fe-106">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="948fe-107">Мы рекомендуем использовать внутренний центр сертификации для Windows Server 2008, Windows Server 2008 R2, центр сертификации Windows Server 2012 или центр сертификации Windows Server 2012 R2 для создания этих сертификатов, чтобы сэкономить на расходах на использование общедоступных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="948fe-107">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="948fe-108">Обработка запросов на сертификат, особенно запросов к общедоступным центрам сертификации, может занять некоторое время, поэтому вы должны заранее запросить сертификаты для пограничных серверов, чтобы убедиться, что они доступны при развертывании компонентов пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="948fe-108">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="948fe-109">Общие сведения о требованиях к сертификатам пограничного сервера приведены <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">в разделе Требования к сертификатам для доступа внешних пользователей в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="948fe-109">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="948fe-110">Несмотря на то, что вы можете использовать общедоступный центр сертификации для внутреннего пограничного сертификата, мы рекомендуем использовать внутренний центр сертификации предприятия для этих других сертификатов, чтобы свести к минимуму стоимость сертификатов.</span><span class="sxs-lookup"><span data-stu-id="948fe-110">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="948fe-111">Общие сведения о требованиях к сертификатам пограничного сервера приведены [в разделе Требования к сертификатам для доступа внешних пользователей в Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="948fe-111">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="948fe-112">При установке пограничного сервера программа установки включает мастер сертификатов, который упрощает выполнение запросов, назначение и установку сертификатов, как описано в разделе <A href="lync-server-2013-set-up-edge-certificates.md">Настройка сертификатов Edge для Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="948fe-112">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="948fe-113">Если вы хотите запросить сертификаты перед установкой пограничного сервера (например, для экономии времени во время фактического развертывания компонентов пограничного сервера), вы можете использовать внутренние серверы, пока вы убедитесь, что сертификаты экспортированы и содержат все обязательные альтернативные имена для темы.</span><span class="sxs-lookup"><span data-stu-id="948fe-113">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="948fe-114">Эта документация не содержит процедур для использования внутренних серверов для запроса сертификатов.</span><span class="sxs-lookup"><span data-stu-id="948fe-114">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="948fe-115">Запрос сертификата в общедоступном центре сертификации</span><span class="sxs-lookup"><span data-stu-id="948fe-115">Request certificates from a public CA</span></span>

<span data-ttu-id="948fe-116">Развертывание пограничного сервера требует наличия единого общедоступного сертификата для внешних интерфейсов пограничных серверов, которые используются для службы пограничного доступа, службы Edge для веб-конференций и для службы проверки подлинности (V).</span><span class="sxs-lookup"><span data-stu-id="948fe-116">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="948fe-117">Этот сертификат должен иметь экспортированный закрытый ключ, чтобы служба проверки подлинности (A/V) использовала те же ключи на всех пограничных серверах в пуле.</span><span class="sxs-lookup"><span data-stu-id="948fe-117">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="948fe-118">На обратном прокси-сервере, который используется в Microsoft Internet Security and Acceleration (ISA) Server 2006 или Microsoft Forefront Threat Management Gateway 2010, также требуется общедоступный сертификат.</span><span class="sxs-lookup"><span data-stu-id="948fe-118">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="948fe-119">Запрос сертификата во внутреннем центре сертификации предприятия</span><span class="sxs-lookup"><span data-stu-id="948fe-119">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="948fe-120">Сертификаты, необходимые внутреннему интерфейсу EDGE, могут выдаваться либо общедоступным центром сертификации (ЦС), либо внутренним центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="948fe-120">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA.</span></span> <span data-ttu-id="948fe-121">Вы можете использовать внутренний центр сертификации предприятия, чтобы свести к минимуму стоимость сертификатов.</span><span class="sxs-lookup"><span data-stu-id="948fe-121">You can use an internal enterprise CA to help minimize the cost of certificates.</span></span> <span data-ttu-id="948fe-122">Если в вашей организации развернут внутренний центр сертификации, сертификаты внутренней стороны должны выдаваться внутренним центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="948fe-122">If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA.</span></span> <span data-ttu-id="948fe-123">Использование внутреннего ЦС предприятия для внутренних сертификатов может снизить стоимость сертификатов.</span><span class="sxs-lookup"><span data-stu-id="948fe-123">Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="948fe-124">Общие сведения о требованиях к сертификатам для компонентов Edge приведены [в разделе Требования к сертификатам для внешних пользователей Access в Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="948fe-124">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="948fe-125">Подробнее о том, как использовать общедоступный центр сертификации для получения сертификатов, можно узнать в статьях [запрос сертификатов для компонентов EDGE в Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span><span class="sxs-lookup"><span data-stu-id="948fe-125">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="948fe-126">Подробные сведения о запросе, установке и назначении сертификатов можно найти в статьях [Настройка сертификатов Edge для Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="948fe-126">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

