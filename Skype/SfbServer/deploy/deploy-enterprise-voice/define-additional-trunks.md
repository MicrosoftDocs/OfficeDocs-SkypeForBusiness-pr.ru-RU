---
title: Определение дополнительных каналов в построителе топологии в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Сводка: сведения о том, как определить дополнительную магистраль между сервером-посредником и одноранговым элементом шлюза в построителе топологии в Skype для бизнеса Server.'
ms.openlocfilehash: afd8a37272d7450115f688bafe3627fb2689903c
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767722"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="42f43-103">Определение дополнительных каналов в построителе топологии в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="42f43-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="42f43-104">**Сводка:** Сведения о том, как определить дополнительную магистраль между сервером-посредником и одноранговым элементом шлюза в построителе топологии в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="42f43-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="42f43-105">Выполните указанные ниже действия, чтобы определить дополнительный магистраль, с которым вы можете связать одноранговый элемент с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="42f43-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="42f43-106">Одноранговая сеть обеспечивает пользователей, подключенных к корпоративной голосовой связи, с подключением к телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="42f43-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="42f43-107">Одноранговый узел может быть шлюзом ТСОП, узлом IP-УАТС или пограничным контроллером сеансов (SBC) для поставщика услуг интернет-телефонии (ITSP).</span><span class="sxs-lookup"><span data-stu-id="42f43-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="42f43-108">Магистраль — это логическая связь между сервером-посредником и шлюзом.</span><span class="sxs-lookup"><span data-stu-id="42f43-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="42f43-109">В этой статье предполагается, что вы намерены настроить шлюз PSTN и корневой магистрали по крайней мере на одном размещенном или отдельном сервере или в отдельном пуле, как описано в разделе [определение шлюза в построителе топологии в Skype для бизнеса Server](define-a-gateway.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="42f43-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="42f43-110">Определение дополнительной магистрали между сервером-посредником и одноранговым узлом шлюза</span><span class="sxs-lookup"><span data-stu-id="42f43-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="42f43-111">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — skype для бизнеса **Server 2015**и выберите пункт **Построитель Skype для бизнеса Server 2015Topology**.</span><span class="sxs-lookup"><span data-stu-id="42f43-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="42f43-112">В разделе "сервер Skype для бизнеса", " **Общие компоненты**", щелкните правой кнопкой мыши узел " **магистральные** сайты" и выберите команду **создать новую магистраль**.</span><span class="sxs-lookup"><span data-stu-id="42f43-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="42f43-113">В поле **Определение новой линии связи** введите информативное имя, однозначно определяющее магистраль.</span><span class="sxs-lookup"><span data-stu-id="42f43-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="42f43-114">Повторяющиеся имена магистралей не допускаются.</span><span class="sxs-lookup"><span data-stu-id="42f43-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="42f43-115">Если в качестве типа транспорта указан протокол TLS, необходимо указать полное доменное имя, а не IP-адрес однорангового сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="42f43-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="42f43-116">В разделе **Связанный шлюз ТСОП** выберите одноранговый узел шлюза ТСОП для связывания с данной магистралью.</span><span class="sxs-lookup"><span data-stu-id="42f43-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="42f43-117">В разделе **прослушивающий порт для шлюза PSTN**введите прослушивающий порт, который узел (шлюз PSTN, IP-УАТС или SBC) будет получать сообщения SIP от сервера-посредника, который должен быть связан с этой магистральной магистрали.</span><span class="sxs-lookup"><span data-stu-id="42f43-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="42f43-118">По умолчанию для протокола TCP применяется одноранговый порт 5066, а для протокола TLS – одноранговый порт 5067.</span><span class="sxs-lookup"><span data-stu-id="42f43-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="42f43-119">Значения по умолчанию для бесперебойно применяемых портов устройства ветвления — 5081 для TCP и 5082 для TLS.</span><span class="sxs-lookup"><span data-stu-id="42f43-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="42f43-120">В разделе **Транспортный протокол SIP** щелкните тип транспортного протокола, применяемый на одноранговом узле.</span><span class="sxs-lookup"><span data-stu-id="42f43-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="42f43-121">По соображениям безопасности настоятельно рекомендуется развернуть одноранговый элемент на сервере-посреднике, который может использовать TLS.</span><span class="sxs-lookup"><span data-stu-id="42f43-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="42f43-122">В разделе **сопоставленный сервер исправлений**выберите пул серверов обисправлений, который нужно связать с корневой магистралью этого узла.</span><span class="sxs-lookup"><span data-stu-id="42f43-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="42f43-123">В разделе **связанный порт сервера исправлений**введите прослушивающий порт, который сервер обновлений будет получать сообщения SIP от однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="42f43-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="42f43-124">Если в Skype для бизнеса Server включена поддержка нескольких магистральных каналов, для двух каналов с разными именами для магистрали нельзя настроить один и тот же **порт сервера-посредника** и **порт прослушивания для IP/КТСОП Gateway** .</span><span class="sxs-lookup"><span data-stu-id="42f43-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="42f43-125">Поддержка нескольких коммуникационных каналов в Skype для бизнеса Server позволяет определять несколько сигнальных портов SIP на сервере-посреднике для связи с несколькими узлами.</span><span class="sxs-lookup"><span data-stu-id="42f43-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="42f43-126">При определении магистрали номер **порта соответствующего сервера-посредника** должен находиться в диапазоне портов прослушивания для соответствующего протокола, разрешенного сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="42f43-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="42f43-127">Этот диапазон портов определен в группе "пулы серверов и исправлений" в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="42f43-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="42f43-128">Щелкните правой кнопкой мыши требуемый пул серверов исправлений и выберите пункт **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="42f43-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="42f43-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="42f43-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="42f43-130">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="42f43-130">Click **OK**.</span></span> 
    

