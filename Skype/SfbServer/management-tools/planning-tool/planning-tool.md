---
title: Средство планирования Skype для бизнеса Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: Руководство по использованию Скайп для средство планирования 2015 Business Server.
ms.openlocfilehash: 6780e69c5a547a96ca9b1b9dc2b3ee54386f1b9b
ms.sourcegitcommit: 1b4e93727f65b120068a74064b4144f0117f230c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2018
ms.locfileid: "19691233"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="4574f-103">Средство планирования Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="4574f-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="4574f-104">Руководство по использованию Скайп для средство планирования 2015 Business Server.</span><span class="sxs-lookup"><span data-stu-id="4574f-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="4574f-105">Скайп для средство планирования 2015 Business Server — мастер на основе механизмов, аналогичные собеседования средство, которое запрашивает Business Server 2015 топологии, который вы разрабатываете вопросы о Скайп.</span><span class="sxs-lookup"><span data-stu-id="4574f-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="4574f-106">Средство планирования использования, предоставленные сведения в сочетании с предпочитаемый и рекомендации по топологии и емкость, чтобы представить рекомендуемые топологии, основываясь на ответах указано.</span><span class="sxs-lookup"><span data-stu-id="4574f-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="4574f-107">Средство планирования можно загрузить из [Скайп для средство планирования 2015 Business Server](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span><span class="sxs-lookup"><span data-stu-id="4574f-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="4574f-108">В конечном счете цель средство планирования — с помощью потенциальных аспектов разработки завершения Скайп для топологии Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4574f-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="4574f-109">Это средство также предоставляет контекстные ссылки на внутреннюю документацию по планированию и развертыванию при условии, что доступно подключение к сети Интернет для доступа на веб-сайт TechNet корпорации Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4574f-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>
  
<span data-ttu-id="4574f-110">После настройки топологии с адресами TCP/IP инфраструктуры и полные доменные имена (FQDN), средство планирования становится доступным ряд отчетов, которые охватывают именования доменных имен (DNS), правила брандмауэра, сертификатов и др.</span><span class="sxs-lookup"><span data-stu-id="4574f-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="4574f-111">Использование этого инструмента — первый этап планирования реализации.</span><span class="sxs-lookup"><span data-stu-id="4574f-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="4574f-112">Следующим шагом будет быть особенности сведения вашего сайта на вход [Скайп для калькулятор емкости Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=51196), при необходимости измените, а затем использовать [Скайп для Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) для имитации и проверка реализация будет использован потребностями.</span><span class="sxs-lookup"><span data-stu-id="4574f-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="4574f-113">Средство планирования также предоставляет возможность экспортировать сведения из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="4574f-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="4574f-114">Microsoft Excel (таблица .xml)</span><span class="sxs-lookup"><span data-stu-id="4574f-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="4574f-115">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="4574f-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="4574f-116">В следующих разделах описываются и сведений о средство планирования.</span><span class="sxs-lookup"><span data-stu-id="4574f-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="4574f-117">Содержание</span><span class="sxs-lookup"><span data-stu-id="4574f-117">In this section</span></span>

- [<span data-ttu-id="4574f-118">Установите средство планирования в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4574f-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="4574f-119">Optional Software</span><span class="sxs-lookup"><span data-stu-id="4574f-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="4574f-120">Выберите средство планирования в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4574f-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="4574f-121">Создание проекта начальные топологии Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4574f-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="4574f-122">Изменение топологии в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4574f-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="4574f-123">Edit the network configuration diagram</span><span class="sxs-lookup"><span data-stu-id="4574f-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="4574f-124">Просмотрите отчеты администратора в Скайп for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4574f-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="4574f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="4574f-125">See also</span></span>

[<span data-ttu-id="4574f-126">Установка Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4574f-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="4574f-127">Планирование для обмена мгновенными сообщениями и присутствия в Скайп Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4574f-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)