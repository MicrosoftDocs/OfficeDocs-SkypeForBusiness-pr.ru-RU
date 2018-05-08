---
title: Определение дополнительных магистралей в построителе топологий в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Сводка: Узнайте, как определение дополнительной магистрали между сервером-посредником и одноранговым узлом шлюза в построителе топологий в Скайп для Business Server 2015.'
ms.openlocfilehash: e76555d0f03b884ad3f3c91c5ca4ad5d687711a2
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server-2015"></a><span data-ttu-id="86e3f-103">Определение дополнительных магистралей в построителе топологий в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="86e3f-103">Define additional trunks in Topology Builder in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="86e3f-104">**Сводка:** Узнайте, как определение дополнительной магистрали между сервером-посредником и одноранговым узлом шлюза в построителе топологий в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="86e3f-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="86e3f-105">Выполните следующие действия, чтобы определить дополнительные линии связи, к которому можно связать одноранговый узел с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="86e3f-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="86e3f-106">Одноранговый узел предоставляет пользователям, включенным для корпоративной голосовой связи с подключением к общедоступной переключения телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="86e3f-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="86e3f-107">Одноранговый узел может быть шлюзом ТСОП, узлом IP-УАТС или пограничным контроллером сеансов (SBC) для поставщика услуг интернет-телефонии (ITSP).</span><span class="sxs-lookup"><span data-stu-id="86e3f-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="86e3f-108">Магистраль — это логическое соединение между сервером-посредником и шлюзом.</span><span class="sxs-lookup"><span data-stu-id="86e3f-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="86e3f-109">В этом разделе предполагается, что программа установки шлюз ТСОП и корневую магистраль по крайней мере один выровненный или изолированный сервер-посредник или пул как описано в [окне Определение шлюза в построителе топологий в Скайп для Business Server 2015](define-a-gateway.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="86e3f-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server 2015](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="86e3f-110">Определение дополнительной магистрали между сервером-посредником и одноранговым узлом шлюза</span><span class="sxs-lookup"><span data-stu-id="86e3f-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="86e3f-111">Запустите построитель топологий: Нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для Business Server 2015**и нажмите кнопку **Скайп для построителя 2015Topology Business Server**.</span><span class="sxs-lookup"><span data-stu-id="86e3f-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="86e3f-112">В разделе Скайп для Business Server, имя узла, **Общие компоненты**, щелкните правой кнопкой мыши узел **магистрали** и затем щелкните **Создать магистраль**.</span><span class="sxs-lookup"><span data-stu-id="86e3f-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    3. <span data-ttu-id="86e3f-p102">В поле **Определение новой линии связи** введите информативное имя, однозначно определяющее магистраль. Повторяющиеся имена магистралей не допускаются.</span><span class="sxs-lookup"><span data-stu-id="86e3f-p102">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk. You cannot have two trunks with the same name.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="86e3f-115">Если в качестве типа транспорта указан безопасности TLS (Transport Layer), необходимо указать полное доменное имя, а не IP-адрес однорангового узла сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="86e3f-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="86e3f-116">В разделе **Связанный шлюз ТСОП** выберите одноранговый узел шлюза ТСОП для связывания с данной магистралью.</span><span class="sxs-lookup"><span data-stu-id="86e3f-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="86e3f-117">В поле **Порт прослушивания для шлюза ТСОП**, введите прослушивающий порт, что одноранговый узел (PSTN gateway, IP-PBX или SBC) будет получать SIP-сообщения от сервера-посредника, который должен быть связан с этой магистралью.</span><span class="sxs-lookup"><span data-stu-id="86e3f-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="86e3f-118">По умолчанию для протокола TCP применяется одноранговый порт 5066, а для протокола TLS – одноранговый порт 5067.</span><span class="sxs-lookup"><span data-stu-id="86e3f-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="86e3f-119">Для обеспечения связи в филиалах портов по умолчанию — 5081 для TCP и 5082 для протокола TLS.</span><span class="sxs-lookup"><span data-stu-id="86e3f-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
6. <span data-ttu-id="86e3f-120">В разделе **Транспортный протокол SIP** щелкните тип транспортного протокола, применяемый на одноранговом узле.</span><span class="sxs-lookup"><span data-stu-id="86e3f-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="86e3f-121">В целях безопасности настоятельно рекомендуется развернуть узел на промежуточный сервер, который может использовать TLS.</span><span class="sxs-lookup"><span data-stu-id="86e3f-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
7. <span data-ttu-id="86e3f-122">В разделе **Связанный сервер-посредник**выберите пул сервера-посредника для связи с корневой магистралью этого узла</span><span class="sxs-lookup"><span data-stu-id="86e3f-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
8. <span data-ttu-id="86e3f-123">В поле **порт связанного сервера-посредника**введите прослушивающий порт, что сервер-посредник будет получать SIP-сообщения от узла.</span><span class="sxs-lookup"><span data-stu-id="86e3f-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="86e3f-124">Благодаря поддержке нескольких магистралей в Скайп для Business Server нельзя настроить две магистрали с разными именами с того же **порта связанный сервер-посредник** и **Порт прослушивания для шлюза IP/ТСОП**</span><span class="sxs-lookup"><span data-stu-id="86e3f-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="86e3f-125">Благодаря поддержке нескольких магистралей в Скайп для Business Server несколько сигналы порты SIP может быть определен на сервер-посредник для связи со множеством узлов.</span><span class="sxs-lookup"><span data-stu-id="86e3f-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="86e3f-126">При определении магистрали, номер **порта связанного сервера-посредника** должен быть в диапазоне портов, прослушиваемых для соответствующих протоколов, предоставляемым сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="86e3f-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="86e3f-127">Этот диапазон портов определен в разделе Скайп для пулов Business Server и сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="86e3f-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="86e3f-128">Щелкните правой кнопкой мыши соответствующий пул сервера-посредника и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="86e3f-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="86e3f-129">Укажите диапазон портов в поле **Прослушивающие порты**.</span><span class="sxs-lookup"><span data-stu-id="86e3f-129">Specify the port range in the **Listening ports** field.</span></span>
  
9. <span data-ttu-id="86e3f-130">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="86e3f-130">Click **OK**.</span></span> 
    

