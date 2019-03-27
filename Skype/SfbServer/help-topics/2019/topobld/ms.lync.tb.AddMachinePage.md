---
title: Добавление сервера
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: 'Чтобы добавить новый сервер в существующий пул серверов, где пула — это один из следующих действий:'
ms.openlocfilehash: 5db99c8cdd2a08722a27a9da437911dcf573d5bf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875618"
---
# <a name="add-server"></a><span data-ttu-id="5436a-103">Добавление сервера</span><span class="sxs-lookup"><span data-stu-id="5436a-103">Add Server</span></span>
 
<span data-ttu-id="5436a-104">Чтобы добавить новый сервер в существующий пул серверов, где пула — это один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="5436a-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="5436a-105">Сервер переднего плана Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="5436a-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="5436a-106">Директоров</span><span class="sxs-lookup"><span data-stu-id="5436a-106">Director server</span></span>
    
- <span data-ttu-id="5436a-107">посредник</span><span class="sxs-lookup"><span data-stu-id="5436a-107">Mediation Server</span></span>
    
- <span data-ttu-id="5436a-108">Сервер аудио-и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="5436a-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="5436a-109">Серверов доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="5436a-109">Trusted Application server</span></span>
    
<span data-ttu-id="5436a-110">Каждый новый пул серверов имеет различные требования.</span><span class="sxs-lookup"><span data-stu-id="5436a-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="5436a-111">В следующих разделах найдите тип сервера, который добавляется в существующий пул и укажите сведения о запросе, как оно указано для каждого типа сервера.</span><span class="sxs-lookup"><span data-stu-id="5436a-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="5436a-112">Укажите сведения, необходимые для определения нового сервера пула.</span><span class="sxs-lookup"><span data-stu-id="5436a-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="5436a-113">**Сервер переднего плана Enterprise Edition**</span><span class="sxs-lookup"><span data-stu-id="5436a-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="5436a-114">Полное доменное имя (FQDN) нового сервера, как оно указано в доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="5436a-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="5436a-115">Выберите **использовать все настроенные IP-адреса**, что означает, что можно использовать любой IP-адрес, определенные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5436a-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="5436a-116">Кроме того можно выбрать **ограничьте использование службы выбранных IP-адресов** и введите определенный адрес на новом сервере.</span><span class="sxs-lookup"><span data-stu-id="5436a-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="5436a-117">Введенный IP-адрес — это единственный IP-адрес, который будут отвечать для размещенных служб.</span><span class="sxs-lookup"><span data-stu-id="5436a-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="5436a-118">Определение **IP-адрес ТСОП** , когда на сервер-посредник является совмещенным на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="5436a-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="5436a-119">Выберите **Включить IPv6,** Чтобы включить IPv6 на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="5436a-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="5436a-120">**Директоров**</span><span class="sxs-lookup"><span data-stu-id="5436a-120">**Director server**</span></span>
  
- <span data-ttu-id="5436a-121">Полное доменное имя нового сервера как оно определяется в DNS.</span><span class="sxs-lookup"><span data-stu-id="5436a-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="5436a-122">Выберите **использовать все настроенные IP-адреса**, что означает, что будет использоваться любой IP-адрес, определенные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5436a-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="5436a-123">Кроме того выберите **ограничьте использование службы выбранных IP-адресов** и введите определенный IP-адрес на новом сервере.</span><span class="sxs-lookup"><span data-stu-id="5436a-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="5436a-124">Введенный IP-адрес — это единственный IP-адрес, который будут отвечать для размещенных служб.</span><span class="sxs-lookup"><span data-stu-id="5436a-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="5436a-125">**Сервер-посредник**</span><span class="sxs-lookup"><span data-stu-id="5436a-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="5436a-126">Полное доменное имя нового сервера как оно определяется в DNS.</span><span class="sxs-lookup"><span data-stu-id="5436a-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="5436a-127">Выберите **использовать все настроенные IP-адреса**, что означает, что можно использовать любой IP-адрес, определенные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5436a-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="5436a-128">Кроме того установите **ограничение использования службы выбранных IP-адресов** и ввод определенный IP-адрес на новый сервер основной IP-адрес и введите IP-адрес для IP-адреса телефонной сети (общего пользования PSTN).</span><span class="sxs-lookup"><span data-stu-id="5436a-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="5436a-129">Введенные IP-адреса — это единственный IP-адрес, который будут отвечать для указанной службы.</span><span class="sxs-lookup"><span data-stu-id="5436a-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5436a-130">Для сервера-посредника IP-адрес для основного IP-адреса и PSTN IP-адрес совпадает с по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5436a-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="5436a-131">IP-адресов, может быть определен отдельно при использовании выделенной сетевых интерфейсов или отдельных IP-адресов на один и тот же интерфейс сети.</span><span class="sxs-lookup"><span data-stu-id="5436a-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="5436a-132">Если у вас есть два сетевых интерфейсов, одно для подключения по локальной сети, а другое для PSTN-соединение, необходимо назначить разные IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="5436a-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="5436a-133">**Сервер аудио-и видеоконференций**</span><span class="sxs-lookup"><span data-stu-id="5436a-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="5436a-134">Полное доменное имя нового сервера как оно определяется в DNS.</span><span class="sxs-lookup"><span data-stu-id="5436a-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="5436a-135">Выберите **использовать все настроенные IP-адреса**, что означает, что можно использовать любой IP-адрес, определенные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5436a-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="5436a-136">Кроме того можно выбрать **ограничьте использование службы выбранных IP-адресов** и введите определенный адрес на новом сервере.</span><span class="sxs-lookup"><span data-stu-id="5436a-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="5436a-137">Введенный IP-адрес — это единственный IP-адрес, который будут отвечать для размещенных служб.</span><span class="sxs-lookup"><span data-stu-id="5436a-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="5436a-138">**Серверов доверенных приложений.**</span><span class="sxs-lookup"><span data-stu-id="5436a-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="5436a-139">Полное доменное имя нового сервера как оно определяется в DNS.</span><span class="sxs-lookup"><span data-stu-id="5436a-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

