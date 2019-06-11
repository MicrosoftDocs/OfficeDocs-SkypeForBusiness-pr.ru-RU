---
title: 'Lync Server 2013: маршрутизация для размещенной единой системы обмена сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90cc1112effd0eac0a25614ee50d7008ee1c5e37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="a4b40-102">Маршрутизация для размещенной единой системы обмена сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4b40-102">Hosted Exchange UM routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4b40-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a4b40-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a4b40-104">Приложение маршрутизации UM Exchange запускается на сервере переднего плана для маршрутизации вызовов либо на развертывание локальной системы обмена сообщениями Microsoft Exchange Server (UM) или в размещенной службе Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="a4b40-104">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="a4b40-105">Приложение маршрутизации Ексум</span><span class="sxs-lookup"><span data-stu-id="a4b40-105">The ExUM Routing Application</span></span>

<span data-ttu-id="a4b40-106">Приложение Lync Server 2013 Exchange для маршрутизации UM использует данные из параметров учетной записи пользователя и из параметров политики размещенной голосовой почты, чтобы определить, как перенаправлять звонки на размещенные голосовые сообщения, как показано на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="a4b40-106">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="a4b40-107">**Пример маршрутизации единой системы обмена сообщениями Exchange для смешанного развертывания**</span><span class="sxs-lookup"><span data-stu-id="a4b40-107">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="a4b40-108">![Развертывание локальной системы обмена сообщениями на сервере Lync Server] (images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Развертывание локальной системы обмена сообщениями на сервере Lync Server")</span><span class="sxs-lookup"><span data-stu-id="a4b40-108">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="a4b40-109">Маршрутизацию в UM-среде Exchange можно настроить так, чтобы она направляла звонки пользователям, которые поддерживают локальную систему обмена СООБЩЕНИЯми Exchange, пользователям, которые работают с размещенной единой системой обмена сообщениями, или сочетанием этих двух служб.</span><span class="sxs-lookup"><span data-stu-id="a4b40-109">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="a4b40-110">Например, предположим, что почтовый ящик Рой и служба Exchange UM размещены в локальной среде развертывания Exchange.</span><span class="sxs-lookup"><span data-stu-id="a4b40-110">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="a4b40-111">Сведения об адресах прокси-сервера из учетной записи пользователя Рой предоставляют сведения, которые используются приложением Routing Ексум, чтобы перенаправлять свои звонки на локальный сервер единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a4b40-111">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="a4b40-112">Почтовый ящик Алисы и служба Exchange UM находятся в центре обработки данных размещенного поставщика услуг Exchange.</span><span class="sxs-lookup"><span data-stu-id="a4b40-112">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="a4b40-113">Маршрутизация для входящих звонков UM происходит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a4b40-113">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="a4b40-114">Значения, заданные в атрибуте Мсексчуквоицемаилсеттингс учетной записи Алисы, говорят приложению Routing Ексум о необходимости поиска подробных сведений о маршрутизации в политике размещенной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="a4b40-114">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a4b40-115">Значение атрибута Мсексчуквоицемаилсеттингс может быть задано поставщиком услуг Exchange или администратором Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4b40-115">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="a4b40-116">В примере, показанном на предыдущей схеме, значение (Кшостедвоицемаил = 1) было установлено администратором Lync Server 2013 для включения размещенной голосовой почты для Алисы.</span><span class="sxs-lookup"><span data-stu-id="a4b40-116">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="a4b40-117">Подробнее об этом атрибуте можно узнать <A href="lync-server-2013-hosted-exchange-user-management.md">в разделе Управление пользователями Exchange в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a4b40-117">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="a4b40-118">Политика размещенной голосовой почты, назначенная учетной записи пользователя Алисы, предоставляет сведения о маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a4b40-118">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="a4b40-119">Destination — это размещенный поставщик служб обмена почтовыми сообщениями (лат. Ексум. \<хостедексчанжесервер\>. com в этом примере).</span><span class="sxs-lookup"><span data-stu-id="a4b40-119">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="a4b40-120">Организации определяются с помощью идентификаторов клиентов, которые представляют собой полные доменные имена для сообщений SIP для клиентов Exchange Server, размещенных на Ls. Ексум. \<хостедексчанжесервер\>. com (в этом примере — Corp.contoso.com и Corp.litwareinc.com).</span><span class="sxs-lookup"><span data-stu-id="a4b40-120">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a4b40-121">Полное доменное имя Exchange Online — exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a4b40-121">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="a4b40-122">Подробнее смотрите в разделе [политики размещенной голосовой почты в Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a4b40-122">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a4b40-123">Если в учетной записи пользователя есть атрибут Мсексчуквоицемаилсеттингс и параметры прокси-сервера UM, атрибут Мсексчуквоицемаилсеттингс имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="a4b40-123">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

