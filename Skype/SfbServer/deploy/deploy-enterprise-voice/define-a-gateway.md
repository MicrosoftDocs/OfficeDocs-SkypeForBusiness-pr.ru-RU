---
title: Определение шлюза в построителе топологий в Skype для бизнеса Server 2015
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
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Сводка: Узнайте, как определить шлюз ТСОП в построителе топологий в Скайп для Business Server 2015.'
ms.openlocfilehash: ae8656d60d819a92a22db6e97f83ea847ee15765
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server-2015"></a><span data-ttu-id="6e17b-103">Определение шлюза в построителе топологий в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="6e17b-103">Define a gateway in Topology Builder in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6e17b-104">**Сводка:** Узнайте, как определить шлюз ТСОП в построителе топологий в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6e17b-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6e17b-105">Выполните следующие действия, чтобы использовать построитель топологий определение однорангового узла с помощью которой можно связать сервер-посредник для подключений к телефонной сети общего пользования (PSTN) пользователям, включенным для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="6e17b-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="6e17b-106">Одноранговый узел на промежуточный сервер может быть шлюз ТСОП, IP-PBX или пограничный контроллер сеансов (SBC) для Интернета телефонии службы поставщика (ITSP) подключение к которому выполняется путем настройки канала SIP.</span><span class="sxs-lookup"><span data-stu-id="6e17b-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="6e17b-107">Определение однорангового узла для сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="6e17b-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="6e17b-108">Запустите построитель топологий: Нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для Business Server 2015**и нажмите кнопку **Скайп для построителя 2015Topology Business Server**.</span><span class="sxs-lookup"><span data-stu-id="6e17b-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="6e17b-109">В разделе Скайп Business Server имя узла, общие компоненты щелкните правой кнопкой мыши узел **Шлюзы ТСОП** и выберите команду **Создать шлюз ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="6e17b-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="6e17b-110">В диалоговом окне **Определение нового шлюза IP/ТСОП** введите полное доменное имя или IP-адрес узла и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6e17b-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6e17b-111">Если в качестве типа транспорта указан безопасности TLS (Transport Layer), необходимо указать полное доменное имя, а не IP-адрес однорангового узла сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="6e17b-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="6e17b-112">Определите режим прослушивания (IPv6 или IPv4) IP-адреса нового шлюза ТСОП и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6e17b-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="6e17b-113">Указать корневую магистраль для шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="6e17b-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="6e17b-114">Магистраль — это логическое соединение между сервером-посредником и шлюзом, уникально определяется следующим кортежем.</span><span class="sxs-lookup"><span data-stu-id="6e17b-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="6e17b-115">{Полное доменное имя сервера посредника, порт прослушивания сервера-посредника (TLS или TCP): IP-адрес и полное доменное имя, порт прослушивания шлюза}</span><span class="sxs-lookup"><span data-stu-id="6e17b-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="6e17b-116">При определении шлюза ТСОП в построителе топологий, необходимо указать корневую магистраль, чтобы успешно добавить шлюз ТСОП в топологию.</span><span class="sxs-lookup"><span data-stu-id="6e17b-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="6e17b-117">Корневая магистраль не может быть удалена, пока не будет удален шлюз ТСОП.</span><span class="sxs-lookup"><span data-stu-id="6e17b-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="6e17b-118">В поле **Порт прослушивания для шлюза IP/ТСОП**введите прослушивающий порт, который будет использоваться шлюз, PBX или SBC для SIP-сообщений от сервера-посредника, который будет связан с корневой магистралью шлюз ТСОП.</span><span class="sxs-lookup"><span data-stu-id="6e17b-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="6e17b-119">(По умолчанию используется порт 5066 для TCP и порт 5067 для TLS на шлюзе ТСОП, УАТС или SBC.</span><span class="sxs-lookup"><span data-stu-id="6e17b-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="6e17b-120">Для обеспечения связи в филиалах в филиале портов по умолчанию: 5081 для TCP и 5082 для протокола TLS.)</span><span class="sxs-lookup"><span data-stu-id="6e17b-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="6e17b-121">В разделе **Транспортный протокол SIP** выберите тип транспорта, используемый одноранговым узлом, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6e17b-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6e17b-122">В целях безопасности настоятельно рекомендуется развернуть узел на промежуточный сервер, который может использовать TLS.</span><span class="sxs-lookup"><span data-stu-id="6e17b-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="6e17b-123">В разделе **Связанный сервер-посредник**выберите пул сервера-посредника для связи с корневой магистралью этот шлюз ТСОП.</span><span class="sxs-lookup"><span data-stu-id="6e17b-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="6e17b-124">В поле **порт связанного сервера-посредника**введите прослушивающий порт, сервер-посредник будет использоваться для SIP-сообщений от шлюза.</span><span class="sxs-lookup"><span data-stu-id="6e17b-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6e17b-125">Благодаря поддержке нескольких магистралей в Скайп для Business Server можно определить несколько SIP, сигналы порты на сервер-посредник для связи с несколькими шлюзов ТСОП.</span><span class="sxs-lookup"><span data-stu-id="6e17b-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="6e17b-126">При определении магистрали, **порт связанного сервера-посредника** должен быть в диапазоне портов, прослушиваемых для соответствующих протоколов, предоставляемым сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="6e17b-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="6e17b-127">Этот диапазон портов для Business Server и пулы-посредники определяется в разделе Скайп.</span><span class="sxs-lookup"><span data-stu-id="6e17b-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="6e17b-128">Щелкните правой кнопкой мыши пула серверов-посредников интересов и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="6e17b-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="6e17b-129">Укажите диапазон портов в поле **Прослушивающие порты**.</span><span class="sxs-lookup"><span data-stu-id="6e17b-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="6e17b-p105">Убедитесь, что определенный вами одноранговый узел работает и использует заданное полное доменное имя или IP-адрес. Затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="6e17b-p105">Be sure that the peer you defined is running and using the FQDN or IP address that you specified. Then click **Finish**.</span></span>
    
11. <span data-ttu-id="6e17b-132">Щелкните узел **Skype для бизнеса Server** правой кнопкой мыши,затем щелкните **Публикация топологии**.</span><span class="sxs-lookup"><span data-stu-id="6e17b-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

