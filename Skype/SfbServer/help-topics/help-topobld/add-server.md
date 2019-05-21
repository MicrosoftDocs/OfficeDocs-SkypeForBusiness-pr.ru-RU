---
title: Добавление сервера
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: Чтобы добавить новый сервер в существующий пул серверов, выберите один из указанных ниже вариантов.
ms.openlocfilehash: 32033d7d758528fc925c5c228971c040828bd654
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290508"
---
# <a name="add-server"></a><span data-ttu-id="d3cfb-103">Добавление сервера</span><span class="sxs-lookup"><span data-stu-id="d3cfb-103">Add Server</span></span>
 
<span data-ttu-id="d3cfb-104">Чтобы добавить новый сервер в существующий пул серверов, выберите один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="d3cfb-105">Сервер переднего плана Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="d3cfb-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="d3cfb-106">Режиссер (сервер)</span><span class="sxs-lookup"><span data-stu-id="d3cfb-106">Director server</span></span>
    
- <span data-ttu-id="d3cfb-107">посредник</span><span class="sxs-lookup"><span data-stu-id="d3cfb-107">Mediation Server</span></span>
    
- <span data-ttu-id="d3cfb-108">Сервер голосовой связи и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="d3cfb-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="d3cfb-109">Доверенный сервер приложений</span><span class="sxs-lookup"><span data-stu-id="d3cfb-109">Trusted Application server</span></span>
    
<span data-ttu-id="d3cfb-110">У каждого нового сервера пула есть другие требования.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="d3cfb-111">В следующих разделах находятся тип сервера, который вы добавите в существующий пул, и укажите необходимые сведения, как оно определено для каждого типа сервера.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="d3cfb-112">Вы предоставляете необходимые данные для определения нового сервера пула.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="d3cfb-113">**Сервер переднего плана Enterprise Edition**</span><span class="sxs-lookup"><span data-stu-id="d3cfb-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="d3cfb-114">Полное доменное имя (FQDN) нового сервера, как оно определено в системе доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="d3cfb-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="d3cfb-115">Выберите параметр **использовать все настроенные IP-адреса**, что означает, что вы можете использовать любые IP-адреса, определенные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="d3cfb-116">Кроме того, вы можете выбрать параметр **ограничить использование службы указанными IP-адресами** и ввести определенный адрес на новом сервере.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="d3cfb-117">Введенный IP-адрес является единственным IP-адресом, который будет отвечать за размещенные службы.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="d3cfb-118">Определите **IP-адрес PSTN** , если на сервере переднего плана размещен сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="d3cfb-119">Выберите **Включить IPv6** , чтобы включить IPv6 для этого сервера.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="d3cfb-120">**Режиссер (сервер)**</span><span class="sxs-lookup"><span data-stu-id="d3cfb-120">**Director server**</span></span>
  
- <span data-ttu-id="d3cfb-121">Полное доменное имя нового сервера, заданное в DNS.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="d3cfb-122">Выберите параметр **использовать все настроенные IP-адреса**, то есть будут использоваться любые IP-адреса, определенные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="d3cfb-123">Кроме того, вы можете выбрать параметр **ограничить использование услуг до выбранных IP-адресов** и ввести определенный IP-адрес на новом сервере.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="d3cfb-124">Введенный IP-адрес является единственным IP-адресом, который будет отвечать за размещенные службы.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="d3cfb-125">**Сервер-посредник**</span><span class="sxs-lookup"><span data-stu-id="d3cfb-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="d3cfb-126">Полное доменное имя нового сервера, заданное в DNS.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="d3cfb-127">Выберите параметр **использовать все настроенные IP-адреса**, что означает, что вы можете использовать любые IP-адреса, определенные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="d3cfb-128">Кроме того, вы можете выбрать параметр **ограничить использование услуг до выбранных IP-адресов** и ввести определенный IP-адрес на новом сервере в качестве основного IP-адреса, а затем ввести IP-адрес для сетевого адреса общественной коммутируемой телефонной сети (КТСОП).</span><span class="sxs-lookup"><span data-stu-id="d3cfb-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="d3cfb-129">Введенные IP-адреса являются единственным IP-адресом, который будет отвечать за указанные службы.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d3cfb-130">IP-адрес, введенный для основного IP-адреса и IP-адреса PSTN, используется по умолчанию для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="d3cfb-131">IP-адреса можно определять отдельно, если вы используете выделенные сетевые интерфейсы или отдельные IP-адреса в одном и том же сетевом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="d3cfb-132">Если у вас есть два интерфейса сети, для подключения по локальной сети и для подключения по протоколу PSTN, необходимо назначить разные IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="d3cfb-133">**Сервер голосовой связи и видеоконференции**</span><span class="sxs-lookup"><span data-stu-id="d3cfb-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="d3cfb-134">Полное доменное имя нового сервера, заданное в DNS.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="d3cfb-135">Выберите параметр **использовать все настроенные IP-адреса**, что означает, что вы можете использовать любые IP-адреса, определенные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="d3cfb-136">Кроме того, вы можете выбрать параметр **ограничить использование службы указанными IP-адресами** и ввести определенный адрес на новом сервере.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="d3cfb-137">Введенный IP-адрес является единственным IP-адресом, который будет отвечать за размещенные службы.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="d3cfb-138">**Доверенный сервер приложений**</span><span class="sxs-lookup"><span data-stu-id="d3cfb-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="d3cfb-139">Полное доменное имя нового сервера, заданное в DNS.</span><span class="sxs-lookup"><span data-stu-id="d3cfb-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

