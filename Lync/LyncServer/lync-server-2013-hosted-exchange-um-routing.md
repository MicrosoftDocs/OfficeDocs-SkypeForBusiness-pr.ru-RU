---
title: 'Lync Server 2013: Маршрутизация размещенной единой системы обмена сообщениями Exchange'
description: 'Lync Server 2013: Маршрутизация размещенной единой системы обмена сообщениями Exchange.'
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
ms.openlocfilehash: 72fbdee5550ae53d5ff5e7513ea384cedad62c5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550135"
---
# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="8aa29-103">Маршрутизация размещенной единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8aa29-103">Hosted Exchange UM routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8aa29-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8aa29-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8aa29-105">Приложение маршрутизации единой системы обмена сообщениями Exchange работает на сервере переднего плана для маршрутизации вызовов либо в локальное развертывание единой системы обмена сообщениями Microsoft Exchange Server (единой системы обмена сообщениями), либо в размещенную службу единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="8aa29-105">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="8aa29-106">Приложение маршрутизации ExUM</span><span class="sxs-lookup"><span data-stu-id="8aa29-106">The ExUM Routing Application</span></span>

<span data-ttu-id="8aa29-107">Приложение для маршрутизации единой системы обмена сообщениями Lync Server 2013 использует сведения из параметров учетной записи пользователя и параметры политики размещенной голосовой почты, чтобы определить, как следует маршрутизировать вызовы для размещенных сообщений голосовой почты, как показано на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="8aa29-107">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="8aa29-108">**Пример маршрутизации в смешанном развертывании единой системы обмена сообщениями Exchange**</span><span class="sxs-lookup"><span data-stu-id="8aa29-108">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="8aa29-109">![Развертывание локальной единой системы обмена сообщениями Lync Server Exchange](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Развертывание локальной единой системы обмена сообщениями Lync Server Exchange")</span><span class="sxs-lookup"><span data-stu-id="8aa29-109">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="8aa29-110">Маршрутизацию единой системы обмена сообщениями Exchange можно настроить для маршрутизации вызовов пользователям, для которых включена локальная система обмена сообщениями Exchange, пользователям с включенной поддержкой единой системы обмена сообщениями Exchange или сочетанием этих двух способов.</span><span class="sxs-lookup"><span data-stu-id="8aa29-110">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="8aa29-111">Например, предположим, что почтовый ящик Роя и служба единой системы обмена сообщениями Exchange размещены в локальном развертывании Exchange.</span><span class="sxs-lookup"><span data-stu-id="8aa29-111">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="8aa29-112">Сведения об адресе прокси-сервера из учетной записи пользователя Роя предоставляют сведения, используемые приложением маршрутизации ExUM для направления своих вызовов на локальный сервер единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="8aa29-112">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="8aa29-113">Почтовый ящик Алисы и служба единой системы обмена сообщениями Exchange расположены в центре обработки данных размещенного поставщика услуг Exchange.</span><span class="sxs-lookup"><span data-stu-id="8aa29-113">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="8aa29-114">Маршрутизация для вызовов единой системы обмена сообщениями Exchange настроена следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8aa29-114">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="8aa29-115">Значения, установленные в атрибуте msExchUCVoiceMailSettings учетной записи пользователя Алисы, сообщают приложению маршрутизации ExUM, что следует искать детали маршрутизации в политике маршрутизации размещенной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="8aa29-115">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8aa29-116">Значение атрибута msExchUCVoiceMailSettings может быть задано поставщиком службы Exchange или администратором Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8aa29-116">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="8aa29-117">В примере, показанном на предыдущей схеме, значение (CsHostedVoiceMail = 1) было задано администратором Lync Server 2013 для включения размещенной голосовой почты для Алисы.</span><span class="sxs-lookup"><span data-stu-id="8aa29-117">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="8aa29-118">Для получения дополнительных сведений об этом атрибуте обратитесь к разделу <A href="lync-server-2013-hosted-exchange-user-management.md">Управление пользователями размещенного Exchange в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8aa29-118">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="8aa29-119">Политика маршрутизации размещенной голосовой почты, назначенная учетной записи пользователя Алисы, предоставляет следующие сведения для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="8aa29-119">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="8aa29-120">Destination — размещенный поставщик службы единой системы обмена сообщениями Exchange (Ls. ExUm. \<hostedExchangeServer\> . в этом примере com).</span><span class="sxs-lookup"><span data-stu-id="8aa29-120">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="8aa29-121">Организации идентифицируются по идентификаторам клиентов, которые являются полными доменными именами для сообщений SIP для клиентов Exchange Server, расположенных на сайте Ls. ExUm. \<hostedExchangeServer\> . com (в данном примере — corp.contoso.com и corp.litwareinc.com).</span><span class="sxs-lookup"><span data-stu-id="8aa29-121">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8aa29-122">Полное доменное имя для Exchange Online — exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8aa29-122">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="8aa29-123">Дополнительные сведения см. [в разделе политики размещенной голосовой почты в Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8aa29-123">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8aa29-124">Если в учетной записи присутствуют как атрибут msExchUCVoiceMailSettings, так и параметры адреса прокси-сервера единой системы обмена сообщениями, то преимущество имеет атрибут msExchUCVoiceMailSettings.</span><span class="sxs-lookup"><span data-stu-id="8aa29-124">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

