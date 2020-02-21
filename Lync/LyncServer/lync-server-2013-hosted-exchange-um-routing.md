---
title: 'Lync Server 2013: Маршрутизация размещенной единой системы обмена сообщениями Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bace74b58c706ef58d05e54e31d2f79ab587ba64
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="0da72-102">Маршрутизация размещенной единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0da72-102">Hosted Exchange UM routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0da72-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0da72-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0da72-104">Приложение маршрутизации единой системы обмена сообщениями Exchange работает на сервере переднего плана для маршрутизации вызовов либо в локальное развертывание единой системы обмена сообщениями Microsoft Exchange Server (единой системы обмена сообщениями), либо в размещенную службу единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="0da72-104">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="0da72-105">Приложение маршрутизации ExUM</span><span class="sxs-lookup"><span data-stu-id="0da72-105">The ExUM Routing Application</span></span>

<span data-ttu-id="0da72-106">Приложение для маршрутизации единой системы обмена сообщениями Lync Server 2013 использует сведения из параметров учетной записи пользователя и параметры политики размещенной голосовой почты, чтобы определить, как следует маршрутизировать вызовы для размещенных сообщений голосовой почты, как показано на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="0da72-106">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="0da72-107">**Пример маршрутизации в смешанном развертывании единой системы обмена сообщениями Exchange**</span><span class="sxs-lookup"><span data-stu-id="0da72-107">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="0da72-108">![Развертывание локальной единой системы обмена сообщениями Lync Server Exchange](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Развертывание локальной единой системы обмена сообщениями Lync Server Exchange")</span><span class="sxs-lookup"><span data-stu-id="0da72-108">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="0da72-109">Маршрутизацию единой системы обмена сообщениями Exchange можно настроить для маршрутизации вызовов пользователям, для которых включена локальная система обмена сообщениями Exchange, пользователям с включенной поддержкой единой системы обмена сообщениями Exchange или сочетанием этих двух способов.</span><span class="sxs-lookup"><span data-stu-id="0da72-109">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="0da72-110">Например, предположим, что почтовый ящик Роя и служба единой системы обмена сообщениями Exchange размещены в локальном развертывании Exchange.</span><span class="sxs-lookup"><span data-stu-id="0da72-110">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="0da72-111">Сведения об адресе прокси-сервера из учетной записи пользователя Роя предоставляют сведения, используемые приложением маршрутизации ExUM для направления своих вызовов на локальный сервер единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="0da72-111">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="0da72-112">Почтовый ящик Алисы и служба единой системы обмена сообщениями Exchange расположены в центре обработки данных размещенного поставщика услуг Exchange.</span><span class="sxs-lookup"><span data-stu-id="0da72-112">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="0da72-113">Маршрутизация для вызовов единой системы обмена сообщениями Exchange настроена следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0da72-113">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="0da72-114">Значения, установленные в атрибуте msExchUCVoiceMailSettings учетной записи пользователя Алисы, сообщают приложению маршрутизации ExUM, что следует искать детали маршрутизации в политике маршрутизации размещенной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="0da72-114">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0da72-115">Значение атрибута msExchUCVoiceMailSettings может быть задано поставщиком службы Exchange или администратором Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0da72-115">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="0da72-116">В примере, показанном на предыдущей схеме, значение (CsHostedVoiceMail = 1) было задано администратором Lync Server 2013 для включения размещенной голосовой почты для Алисы.</span><span class="sxs-lookup"><span data-stu-id="0da72-116">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="0da72-117">Для получения дополнительных сведений об этом атрибуте обратитесь к разделу <A href="lync-server-2013-hosted-exchange-user-management.md">Управление пользователями размещенного Exchange в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0da72-117">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="0da72-118">Политика маршрутизации размещенной голосовой почты, назначенная учетной записи пользователя Алисы, предоставляет следующие сведения для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="0da72-118">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="0da72-119">Destination — размещенный поставщик службы единой системы обмена сообщениями Exchange (Ls. ExUm. \<хостедексчанжесервер\>. com в этом примере).</span><span class="sxs-lookup"><span data-stu-id="0da72-119">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="0da72-120">Организации идентифицируются по идентификаторам клиентов, которые являются полными доменными именами для сообщений SIP для клиентов Exchange Server, расположенных на сайте Ls. ExUm. \<хостедексчанжесервер\>. com (в этом примере — Corp.contoso.com и Corp.litwareinc.com).</span><span class="sxs-lookup"><span data-stu-id="0da72-120">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="0da72-121">Полное доменное имя для Exchange Online — exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0da72-121">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="0da72-122">Дополнительные сведения см. [в разделе политики размещенной голосовой почты в Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0da72-122">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0da72-123">Если в учетной записи присутствуют как атрибут msExchUCVoiceMailSettings, так и параметры адреса прокси-сервера единой системы обмена сообщениями, то преимущество имеет атрибут msExchUCVoiceMailSettings.</span><span class="sxs-lookup"><span data-stu-id="0da72-123">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

