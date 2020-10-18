---
title: 'Lync Server 2013: запрос сертификатов для пограничных компонентов'
description: 'Lync Server 2013: запрос сертификатов для пограничных компонентов.'
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
ms.openlocfilehash: 461e40921c88f26ce56141a8782ef2a04ce99667
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579015"
---
# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="87a97-103">Запрос сертификатов для пограничных компонентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87a97-103">Request certificates for edge components in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87a97-104">_**Последнее изменение темы:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="87a97-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="87a97-105">Сертификаты, необходимые для поддержки доступа внешних пользователей, включают сертификаты, выданные общедоступным центром сертификации (ЦС) и сертификаты, выданные внутренним ЦС предприятия.</span><span class="sxs-lookup"><span data-stu-id="87a97-105">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="87a97-106">Сертификаты, необходимые для внешнего интерфейса пограничного сервера и обратного прокси-сервера, должны быть выпущены общедоступным центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="87a97-106">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="87a97-107">Сертификаты, необходимые для внутреннего интерфейса, могут быть выданы как общедоступным ЦС, так и внутренним ЦС предприятия.</span><span class="sxs-lookup"><span data-stu-id="87a97-107">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="87a97-108">Мы рекомендуем использовать внутренний ЦС Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 ЦС, центр сертификации Windows Server или ЦС Windows Server 2012 R2 для создания этих сертификатов, чтобы сэкономить на расходе на использование общедоступных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="87a97-108">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="87a97-109">Обработка запросов на сертификаты, особенно запросов к общедоступным центрам сертификации, может занять некоторое время, поэтому следует заранее запрашивать сертификаты для пограничных серверов, чтобы убедиться, что они доступны при запуске развертывания компонентов пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="87a97-109">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="87a97-110">Общие сведения о требованиях к сертификатам для пограничных серверов приведены <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">в статье требования к сертификатам для доступа внешних пользователей в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="87a97-110">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="87a97-111">Хотя можно выбрать использование общедоступного ЦС для сертификата внутреннего периметра, рекомендуется использовать внутренний ЦС предприятия, чтобы максимально уменьшить затраты на сертификаты.</span><span class="sxs-lookup"><span data-stu-id="87a97-111">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="87a97-112">Общие сведения о требованиях к сертификатам для пограничных серверов приведены [в статье требования к сертификатам для доступа внешних пользователей в Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="87a97-112">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="87a97-113">При установке пограничного сервера программа установки включает мастер сертификатов, который упрощает задачу запроса, назначения и установки сертификатов, как описано в разделе <A href="lync-server-2013-set-up-edge-certificates.md">Настройка пограничных сертификатов для Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="87a97-113">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="87a97-114">Если необходимо запросить сертификаты перед установкой пограничного сервера (например, для экономии времени при фактическом развертывании компонентов пограничного сервера), можно использовать внутренние серверы, если вы гарантируете, что сертификаты будут экспортироваться и содержат все необходимые альтернативные имена субъектов.</span><span class="sxs-lookup"><span data-stu-id="87a97-114">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="87a97-115">В этой документации не приводятся процедуры использования внутренних серверов для запроса сертификатов.</span><span class="sxs-lookup"><span data-stu-id="87a97-115">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="87a97-116">Запрос сертификатов в общедоступном ЦС</span><span class="sxs-lookup"><span data-stu-id="87a97-116">Request certificates from a public CA</span></span>

<span data-ttu-id="87a97-117">Для развертывания пограничного сервера необходим один общедоступный сертификат для внешних интерфейсов пограничных серверов, который используется для пограничной службы доступа, пограничной службы веб-конференций и для службы проверки подлинности (A/V).</span><span class="sxs-lookup"><span data-stu-id="87a97-117">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="87a97-118">Этот сертификат должен иметь экспортируемый закрытый ключ, чтобы служба проверки подлинности аудио-и видеоданных использовала одни и те же ключи на всех пограничных серверах в пуле.</span><span class="sxs-lookup"><span data-stu-id="87a97-118">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="87a97-119">Для обратного прокси-сервера, используемого с Microsoft Internet Security and Acceleration (ISA) Server 2006 или Microsoft Forefront Threat Management Gateway 2010, также требуется общедоступный сертификат.</span><span class="sxs-lookup"><span data-stu-id="87a97-119">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="87a97-120">Запрос сертификатов во внутреннем ЦС предприятия</span><span class="sxs-lookup"><span data-stu-id="87a97-120">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="87a97-p106">Сертификаты, необходимые для внутреннего пограничного интерфейса, могут быть выданы либо общедоступным ЦС, либо внутренним ЦС. Используя внутренний ЦС предприятия, можно сократить затраты на сертификаты. Если в организации развернут внутренний ЦС, то сертификаты для внутреннего периметра должны быть выданы внутренним ЦС. Использование внутреннего ЦС предприятия для внутренних сертификатом может уменьшить стоимость сертификатов.</span><span class="sxs-lookup"><span data-stu-id="87a97-p106">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA. You can use an internal enterprise CA to help minimize the cost of certificates. If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA. Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="87a97-125">Общие сведения о требованиях к сертификатам для пограничных компонентов приведены [в статье требования к сертификатам для доступа внешних пользователей в Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="87a97-125">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="87a97-126">Для получения дополнительных сведений об использовании общедоступного ЦС для получения сертификатов, ознакомьтесь со статьей [запрос сертификатов для пограничных компонентов в Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span><span class="sxs-lookup"><span data-stu-id="87a97-126">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="87a97-127">Дополнительные сведения о запросе, установке и назначении сертификатов приведены в статье [Настройка пограничных сертификатов для Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="87a97-127">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

