---
title: Определение шлюза в построителе топологии в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Сводка: сведения о том, как определить шлюз PSTN в построителе топологии в Skype для бизнеса Server.'
ms.openlocfilehash: 39e2bdf041055e392b88cc25594b45c2529161d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286171"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="4766d-103">Определение шлюза в построителе топологии в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4766d-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="4766d-104">**Сводка:** Сведения о том, как определить шлюз PSTN в построителе топологии в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4766d-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="4766d-105">Выполните эти действия, чтобы определить одноранговый элемент, с помощью которого можно связать сервер-посредник, чтобы обеспечить подключение к телефонной сети с открытым коммутируемым доступом (КТСОП) для пользователей, поддерживающих корпоративную голосовую связь.</span><span class="sxs-lookup"><span data-stu-id="4766d-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="4766d-106">Одноранговый сервер может быть шлюзом PSTN, IP-УАТС или контроллером границ сеанса (SBC) для поставщика услуг телефонной связи через Интернет (ИТСП), к которому вы подключаетесь, настраивая магистраль SIP.</span><span class="sxs-lookup"><span data-stu-id="4766d-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="4766d-107">Определение однорангового узла для сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="4766d-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="4766d-108">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — skype для бизнеса **Server 2015**и выберите пункт Построитель **Skype для бизнеса Server 2015Topology**.</span><span class="sxs-lookup"><span data-stu-id="4766d-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="4766d-109">В разделе "сервер Skype для бизнеса", "имя сайта", "Общие компоненты" щелкните правой кнопкой мыши узел **шлюзы PSTN** и выберите пункт **создать шлюз PSTN**.</span><span class="sxs-lookup"><span data-stu-id="4766d-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="4766d-110">В диалоговом окне **Определение нового шлюза IP/ТСОП** введите полное доменное имя или IP-адрес узла и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4766d-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4766d-111">Если в качестве типа транспорта указан протокол TLS, необходимо указать полное доменное имя, а не IP-адрес однорангового сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="4766d-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="4766d-112">Определите режим прослушивания (IPv6 или IPv4) IP-адреса нового шлюза ТСОП и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4766d-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="4766d-113">Определите корневую магистраль для шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="4766d-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="4766d-114">Магистраль — это логическая связь между сервером-посредником и шлюзом, уникальным образом идентифицированными кортежем.</span><span class="sxs-lookup"><span data-stu-id="4766d-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="4766d-115">Полное доменное имя сервера-посредника, прослушивающий порт сервера (TLS или TCP): IP Gateway и FQDN, порт прослушивания шлюза}</span><span class="sxs-lookup"><span data-stu-id="4766d-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="4766d-116">При определении шлюза PSTN в построителе топологии необходимо определить корневой магистраль, чтобы успешно добавить шлюз PSTN в топологию.</span><span class="sxs-lookup"><span data-stu-id="4766d-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="4766d-117">Корневая магистраль не может быть удалена, пока не будет удален шлюз ТСОП.</span><span class="sxs-lookup"><span data-stu-id="4766d-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="4766d-118">В разделе **прослушивающий порт для IP/КТСОП Gateway**введите прослушивающий порт, который шлюз, УАТС или SBC будет использовать для сообщений SIP от сервера-посредника, который будет связан с корневой магистральным шлюзом PSTN.</span><span class="sxs-lookup"><span data-stu-id="4766d-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="4766d-119">(По умолчанию используется порт 5066 для TCP и порт 5067 для TLS на шлюзе ТСОП, УАТС или SBC.</span><span class="sxs-lookup"><span data-stu-id="4766d-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="4766d-120">Для бесперебойно работающего устройства филиалов на сайте филиала по умолчанию используются порты 5081 для TCP и 5082 для TLS.</span><span class="sxs-lookup"><span data-stu-id="4766d-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="4766d-121">В разделе **Транспортный протокол SIP** выберите тип транспорта, используемый одноранговым узлом, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4766d-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4766d-122">По соображениям безопасности настоятельно рекомендуется развернуть одноранговый элемент на сервере-посреднике, который может использовать TLS.</span><span class="sxs-lookup"><span data-stu-id="4766d-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="4766d-123">В разделе сопоставленный **сервер исправлений**выберите пул серверов обисправлений, который нужно связать с корневой магистральной магистрали этого шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="4766d-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="4766d-124">В разделе **связанный порт сервера исправлений**введите прослушивающий порт, который сервер обправителя будет использовать для SIP messages с шлюза.</span><span class="sxs-lookup"><span data-stu-id="4766d-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4766d-125">Поддержка нескольких коммуникационных каналов в Skype для бизнеса Server позволяет определить несколько сигнальных портов SIP на сервере-посреднике для связи с несколькими шлюзами PSTN.</span><span class="sxs-lookup"><span data-stu-id="4766d-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="4766d-126">При определении канала связи **соответствующий порт сервера** -посредника должен находиться в диапазоне портов прослушивания соответствующего протокола, разрешенного сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="4766d-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="4766d-127">Этот диапазон портов определен в разделе "сервер и пулы исправлений" в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4766d-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="4766d-128">Щелкните правой кнопкой мыши требуемый пул серверов-исправлений и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="4766d-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="4766d-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="4766d-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="4766d-130">Убедитесь, что определенный вами одноранговый узел работает и использует заданное полное доменное имя или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="4766d-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="4766d-131">Затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="4766d-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="4766d-132">Щелкните узел **Skype для бизнеса Server** правой кнопкой мыши,затем щелкните **Публикация топологии**.</span><span class="sxs-lookup"><span data-stu-id="4766d-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

