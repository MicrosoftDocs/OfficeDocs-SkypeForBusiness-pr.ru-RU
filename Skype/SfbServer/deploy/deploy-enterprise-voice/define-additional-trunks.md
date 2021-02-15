---
title: Определение дополнительных магистральных магистрали в построителье топологий в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: Сводка. Узнайте, как определить дополнительную магистраль между сервером-посредником и одноранговой частью шлюза в построителе топологий в Skype для бизнеса Server.
ms.openlocfilehash: 3aab744761420ab631f17e6b56391f1fab120ccf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836999"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="0a2c8-103">Определение дополнительных магистральных магистрали в построителье топологий в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0a2c8-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="0a2c8-104">**Сводка:** Узнайте, как определить дополнительную магистраль между сервером-посредником и шлюзом в построителе топологий в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="0a2c8-105">Выполните следующие действия, чтобы определить дополнительную магистраль, с которой можно связать одноранговую магистраль с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="0a2c8-106">Одноранговая сеть предоставляет пользователям, Корпоративная голосовая связь возможность подключения к телефонной сети общего перейти на телефонную сеть (STN).</span><span class="sxs-lookup"><span data-stu-id="0a2c8-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="0a2c8-107">Узлом может быть шлюз ТСОП, IP-УАТС или пограничный контроллер сеансов (SBC) для поставщика услуг Интернет-телефонии (ITSP).</span><span class="sxs-lookup"><span data-stu-id="0a2c8-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="0a2c8-108">Магистраль — это логическое соединение между сервером-посредником и шлюзом.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0a2c8-109">В этом разделе предполагается, что вы настроили шлюз ТСТС и корневую магистраль по крайней мере с одним размещенным или автономным сервером-посредником или пулом, как описано в разделе "Определение шлюза в построителе топологий в Skype для бизнеса [Server"](define-a-gateway.md) документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="0a2c8-110">Определение дополнительной магистрали между сервером-посредником и одноранговой магистралью шлюза</span><span class="sxs-lookup"><span data-stu-id="0a2c8-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="0a2c8-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click Skype for Business Server **2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="0a2c8-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="0a2c8-113">В окне **Определение новой магистрали** введите понятное имя для уникальной идентификации магистрали.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="0a2c8-114">Не может быть двух магистралей с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="0a2c8-115">Если в качестве типа транспорта указан TLS, необходимо указать FQDN вместо IP-адреса однорангового узла сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="0a2c8-116">В окне **Связанный шлюз ТСОП** выберите узел шлюза ТСОП, который следует связать с этой магистралью.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="0a2c8-117">В подмножестве прослушиваемого порта для шлюза **STN** введите порт прослушивания, который одноранговый сервер (шлюз STN, IP-PBX или SBC) будет получать SIP-сообщения от сервера-посредника, который должен быть связан с этой магистралью.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="0a2c8-118">Порты по умолчанию — 5066 для протокола TCP и 5067 для TLS.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="0a2c8-119">Порты устройства для survivable branch Appliance по умолчанию : 5081 для TCP и 5082 для TLS.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="0a2c8-120">В окне **Транспортный протокол SIP** щелкните тип транспорта, используемый узлом.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0a2c8-121">Из соображений безопасности настоятельно рекомендуется развернуть одноранговой сервер на сервере-посреднике, который может использовать TLS.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="0a2c8-122">В **связанном сервере-посреднике** выберите пул серверов-посредников, который необходимо связать с корневой магистралью этого узла</span><span class="sxs-lookup"><span data-stu-id="0a2c8-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="0a2c8-123">В **связанном порте сервера-посредника** введите порт прослушивания, который сервер-посредник будет получать SIP-сообщения от однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0a2c8-124">При поддержке нескольких магистральных магистральных магистрали в Skype для бизнеса Server  нельзя настроить две магистрали с разными именами магистрали с одинаковым портом связанного сервера-посредника и портом прослушивания для **шлюза IP/STN**</span><span class="sxs-lookup"><span data-stu-id="0a2c8-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="0a2c8-125">При поддержке нескольких магистральных каналов в Skype для бизнеса Server можно определить несколько сигнальных портов SIP на сервере-посреднике для связи с несколькими однорангами.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="0a2c8-126">При определении магистрали  номер порта связанного сервера-посредника должен быть в диапазоне прослушивающих портов для соответствующего протокола, разрешенного сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="0a2c8-127">Этот диапазон портов определяется в пулах Skype для бизнеса Server и серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="0a2c8-128">Щелкните правой кнопкой мыши соответствующий пул серверов-посредников и выберите **"Изменить свойства".**</span><span class="sxs-lookup"><span data-stu-id="0a2c8-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="0a2c8-129">Укажите диапазон портов в поле **Прослушивающие порты**.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="0a2c8-130">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0a2c8-130">Click **OK**.</span></span> 
    

