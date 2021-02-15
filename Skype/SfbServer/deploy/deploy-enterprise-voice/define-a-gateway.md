---
title: Определение шлюза в построителье топологий в Skype для бизнеса Server
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
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: Сводка. Узнайте, как определить шлюз STN в построителе топологий в Skype для бизнеса Server.
ms.openlocfilehash: be68c853cdcd530b05ad4b0949f722788e77d0df
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837029"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="66f81-103">Определение шлюза в построителье топологий в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="66f81-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="66f81-104">**Сводка:** Узнайте, как определить шлюз STN в построителе топологий в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="66f81-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="66f81-105">Выполните следующие действия, чтобы использовать построитель топологий, чтобы определить одноранговой сервер, с которым можно связать сервер-посредник, чтобы обеспечить подключение к телефонной сети общего пользования (PSTN) для пользователей с включенной поддержкой Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="66f81-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="66f81-106">Одноранговая связь с сервером-посредником может быть шлюзом STN, IP-PBX или пограничным контроллером сеансов (SBC) для поставщика услуг интернет-телефонии (ITSP), к которому подключается настройка магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="66f81-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="66f81-107">Определение одноранговой сети для сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="66f81-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="66f81-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click Skype for Business Server **2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="66f81-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="66f81-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span><span class="sxs-lookup"><span data-stu-id="66f81-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="66f81-110">В диалоговом окне **Определение нового шлюза IP/ТСОП** введите полное доменное имя или IP-адрес узла и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="66f81-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="66f81-111">Если в качестве типа транспорта указан TLS, необходимо указать FQDN вместо IP-адреса однорангового узла сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="66f81-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="66f81-112">Определите режим прослушивания (IPv6 или IPv4) IP-адреса нового шлюза ТСОП и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="66f81-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="66f81-113">Определите корневую магистраль для шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="66f81-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="66f81-114">Магистраль — это логическое соединение между сервером-посредником и шлюзом, уникальным образом идентифицированным по обойму.</span><span class="sxs-lookup"><span data-stu-id="66f81-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="66f81-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : ip and FQDN шлюза, прослушивает порт шлюза}</span><span class="sxs-lookup"><span data-stu-id="66f81-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="66f81-116">При определении шлюза STN в построителе топологий необходимо определить корневую магистраль для успешного добавления шлюза STN в топологию.</span><span class="sxs-lookup"><span data-stu-id="66f81-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="66f81-117">Корневая магистраль не может быть удалена, пока не будет удален шлюз ТСОП.</span><span class="sxs-lookup"><span data-stu-id="66f81-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="66f81-118">В области прослушиваемого порта для **шлюза IP/STN** введите порт прослушивания, который шлюз, УАПС или SBC будет использовать для SIP-сообщений с сервера-посредника, которые будут связаны с корневой магистралью шлюза STN.</span><span class="sxs-lookup"><span data-stu-id="66f81-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="66f81-119">(По умолчанию имеются порты 5066 для протокола TCP и 5067 для протокола TLS на шлюзе STN, УАЦ или SBC.</span><span class="sxs-lookup"><span data-stu-id="66f81-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="66f81-120">На устройстве для survivable Branch Appliance на сайте филиала порты по умолчанию : 5081 для TCP и 5082 для TLS.)</span><span class="sxs-lookup"><span data-stu-id="66f81-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="66f81-121">В разделе **Транспортный протокол SIP** выберите тип транспорта, используемый одноранговым узлом, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="66f81-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="66f81-122">Из соображений безопасности настоятельно рекомендуется развернуть одноранговой сервер на сервере-посреднике, который может использовать TLS.</span><span class="sxs-lookup"><span data-stu-id="66f81-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="66f81-123">В **связанном сервере-посреднике** выберите пул серверов-посредников, который необходимо связать с корневой магистралью этого шлюза STN.</span><span class="sxs-lookup"><span data-stu-id="66f81-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="66f81-124">В **связанном порте сервера-посредника** введите порт прослушивания, который сервер-посредник будет использовать для SIP-сообщений от шлюза.</span><span class="sxs-lookup"><span data-stu-id="66f81-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="66f81-125">При поддержке нескольких магистральных каналов в Skype для бизнеса Server можно определить несколько сигнальных портов SIP на сервере-посреднике для связи с несколькими шлюзами STN.</span><span class="sxs-lookup"><span data-stu-id="66f81-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="66f81-126">При определении магистрали  порт связанного сервера-посредника должен быть в диапазоне прослушивающих портов для соответствующего протокола, разрешенного сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="66f81-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="66f81-127">Этот диапазон портов определяется в Skype для бизнеса Server и пулах-посредниках.</span><span class="sxs-lookup"><span data-stu-id="66f81-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="66f81-128">Щелкните правой кнопкой мыши интересуя пул серверов-посредников и выберите **"Изменить свойства".**</span><span class="sxs-lookup"><span data-stu-id="66f81-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="66f81-129">Укажите диапазон портов в поле **Прослушивающие порты**.</span><span class="sxs-lookup"><span data-stu-id="66f81-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="66f81-130">Убедитесь, что определенный вами одноранговой адрес работает и использует указанное вами FQDN или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="66f81-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="66f81-131">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="66f81-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="66f81-132">Щелкните правой кнопкой мыши узел **Skype для** бизнеса Server и выберите **"Опубликовать топологию".**</span><span class="sxs-lookup"><span data-stu-id="66f81-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

