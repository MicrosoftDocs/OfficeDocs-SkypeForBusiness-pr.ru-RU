---
title: Определение дополнительных магистралей в построителе топологий в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Сводка: Узнайте, как определение дополнительной магистрали между сервером-посредником и одноранговым узлом шлюза в построителе топологий в Скайп для Business Server.'
ms.openlocfilehash: 308cd200af2ee046a3e2bcc84815d3755cea932f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892862"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="db71e-103">Определение дополнительных магистралей в построителе топологий в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="db71e-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="db71e-104">**Сводка:** Узнайте, как определение дополнительной магистрали между сервером-посредником и одноранговым узлом шлюза в построителе топологий в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="db71e-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="db71e-105">Выполните следующие действия, чтобы определить дополнительные линии связи, к которому можно связать одноранговый узел с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="db71e-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="db71e-106">Одноранговый узел предоставляет пользователям, включенным для корпоративной голосовой связи с подключением к общедоступной переключения телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="db71e-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="db71e-107">Одноранговый узел может быть шлюзом ТСОП, узлом IP-УАТС или пограничным контроллером сеансов (SBC) для поставщика услуг интернет-телефонии (ITSP).</span><span class="sxs-lookup"><span data-stu-id="db71e-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="db71e-108">Магистраль — это логическое соединение между сервером-посредником и шлюзом.</span><span class="sxs-lookup"><span data-stu-id="db71e-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="db71e-109">В этом разделе предполагается, что программа установки шлюз ТСОП и корневую магистраль по крайней мере один выровненный или изолированный сервер-посредник или пул как описано в [окне Определение шлюза в построителе топологий в Скайп для Business Server](define-a-gateway.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="db71e-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="db71e-110">Определение дополнительной магистрали между сервером-посредником и одноранговым узлом шлюза</span><span class="sxs-lookup"><span data-stu-id="db71e-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="db71e-111">Запустите построитель топологий: Нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для Business Server 2015**и нажмите кнопку **Скайп для построителя 2015Topology Business Server**.</span><span class="sxs-lookup"><span data-stu-id="db71e-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="db71e-112">В разделе Скайп для Business Server, имя узла, **Общие компоненты**, щелкните правой кнопкой мыши узел **магистрали** и затем щелкните **Создать магистраль**.</span><span class="sxs-lookup"><span data-stu-id="db71e-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="db71e-113">В поле **Определение новой линии связи** введите информативное имя, однозначно определяющее магистраль.</span><span class="sxs-lookup"><span data-stu-id="db71e-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="db71e-114">Повторяющиеся имена магистралей не допускаются.</span><span class="sxs-lookup"><span data-stu-id="db71e-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="db71e-115">Если в качестве типа транспорта указан безопасности TLS (Transport Layer), необходимо указать полное доменное имя, а не IP-адрес однорангового узла сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="db71e-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="db71e-116">В разделе **Связанный шлюз ТСОП** выберите одноранговый узел шлюза ТСОП для связывания с данной магистралью.</span><span class="sxs-lookup"><span data-stu-id="db71e-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="db71e-117">В поле **Порт прослушивания для шлюза ТСОП**, введите прослушивающий порт, что одноранговый узел (PSTN gateway, IP-PBX или SBC) будет получать SIP-сообщения от сервера-посредника, который должен быть связан с этой магистралью.</span><span class="sxs-lookup"><span data-stu-id="db71e-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="db71e-118">По умолчанию для протокола TCP применяется одноранговый порт 5066, а для протокола TLS – одноранговый порт 5067.</span><span class="sxs-lookup"><span data-stu-id="db71e-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="db71e-119">Для обеспечения связи в филиалах портов по умолчанию — 5081 для TCP и 5082 для протокола TLS.</span><span class="sxs-lookup"><span data-stu-id="db71e-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="db71e-120">В разделе **Транспортный протокол SIP** щелкните тип транспортного протокола, применяемый на одноранговом узле.</span><span class="sxs-lookup"><span data-stu-id="db71e-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="db71e-121">В целях безопасности настоятельно рекомендуется развернуть узел на промежуточный сервер, который может использовать TLS.</span><span class="sxs-lookup"><span data-stu-id="db71e-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="db71e-122">В разделе **Связанный сервер-посредник**выберите пул сервера-посредника для связи с корневой магистралью этого узла</span><span class="sxs-lookup"><span data-stu-id="db71e-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="db71e-123">В поле **порт связанного сервера-посредника**введите прослушивающий порт, что сервер-посредник будет получать SIP-сообщения от узла.</span><span class="sxs-lookup"><span data-stu-id="db71e-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="db71e-124">Благодаря поддержке нескольких магистралей в Скайп для Business Server нельзя настроить две магистрали с разными именами с того же **порта связанный сервер-посредник** и **Порт прослушивания для шлюза IP/ТСОП**</span><span class="sxs-lookup"><span data-stu-id="db71e-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="db71e-125">Благодаря поддержке нескольких магистралей в Скайп для Business Server несколько сигналы порты SIP может быть определен на сервер-посредник для связи со множеством узлов.</span><span class="sxs-lookup"><span data-stu-id="db71e-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="db71e-126">При определении магистрали, номер **порта связанного сервера-посредника** должен быть в диапазоне портов, прослушиваемых для соответствующих протоколов, предоставляемым сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="db71e-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="db71e-127">Этот диапазон портов определен в разделе Скайп для пулов Business Server и сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="db71e-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="db71e-128">Щелкните правой кнопкой мыши соответствующий пул сервера-посредника и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="db71e-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="db71e-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="db71e-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="db71e-130">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="db71e-130">Click **OK**.</span></span> 
    

