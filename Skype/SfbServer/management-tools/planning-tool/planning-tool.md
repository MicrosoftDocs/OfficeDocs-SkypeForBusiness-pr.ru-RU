---
title: Средство планирования Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: Руководство по использованию средства планирования Skype для бизнеса Server 2015.
ms.openlocfilehash: 8eec7865b74640cf6dfe4f5a5122f4c7091cc5ae
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050101"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="97c97-103">Средство планирования Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="97c97-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="97c97-104">Руководство по использованию средства планирования Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="97c97-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="97c97-105">Средство планирования Skype для бизнеса Server 2015 — это средство, которое управляется мастером, которое запрашивает вопросы о создаваемой вами топологии Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="97c97-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="97c97-106">В средстве планирования используются предоставленные сведения, которые связаны с рекомендуемыми рекомендациями по проектированию и емкости топологии, чтобы представить рекомендуемую топологию на основе предоставленных ответов.</span><span class="sxs-lookup"><span data-stu-id="97c97-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="97c97-107">Средство планирования можно скачать с помощью [средства планирования Skype для бизнеса Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span><span class="sxs-lookup"><span data-stu-id="97c97-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="97c97-108">В конечном итоге, цель средства планирования заключается в том, чтобы упростить разработку полной топологии Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="97c97-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="97c97-109">Средство также предоставляет контекстные ссылки на документацию по планированию и развертыванию в средстве, при условии, что подключение к Интернету доступно для подключения к веб-сайту Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="97c97-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="97c97-110">После настройки топологии с использованием TCP/IP-адресов и полных доменных имен в инфраструктуре средство планирования предоставляет доступ к ряду отчетов, которые охватывают имена DNS, правила брандмауэра, сертификаты и многое другое.</span><span class="sxs-lookup"><span data-stu-id="97c97-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="97c97-111">Использование этого средства является первым шагом при планировании реализации.</span><span class="sxs-lookup"><span data-stu-id="97c97-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="97c97-112">Следующий шаг заключается в вводе сведений о сайте в [Калькулятор емкости Skype для бизнеса server 2015](https://www.microsoft.com/download/details.aspx?id=51196), при необходимости используя [средство нагрузочного тестирования и производительности Skype для бизнеса Server 2015](https://www.microsoft.com/download/details.aspx?id=50367) для моделирования и проверки реализации.</span><span class="sxs-lookup"><span data-stu-id="97c97-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="97c97-113">Средство планирования также предоставляет возможность экспорта данных в двух форматах:</span><span class="sxs-lookup"><span data-stu-id="97c97-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="97c97-114">Microsoft Excel (электронная таблица XML)</span><span class="sxs-lookup"><span data-stu-id="97c97-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="97c97-115">Microsoft Visio (. vdx)</span><span class="sxs-lookup"><span data-stu-id="97c97-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="97c97-116">В следующих разделах описываются и подробно рассматриваются средства планирования.</span><span class="sxs-lookup"><span data-stu-id="97c97-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="97c97-117">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="97c97-117">In this section</span></span>

- [<span data-ttu-id="97c97-118">Установка средства планирования в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="97c97-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="97c97-119">Дополнительное программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="97c97-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="97c97-120">Навигация в средстве планирования в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="97c97-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="97c97-121">Создание первоначальной структуры топологии для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="97c97-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="97c97-122">Изменение топологии в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="97c97-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="97c97-123">Изменение схемы конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="97c97-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="97c97-124">Просмотр отчетов администратора в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="97c97-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="97c97-125">См. также</span><span class="sxs-lookup"><span data-stu-id="97c97-125">See also</span></span>

[<span data-ttu-id="97c97-126">Установка Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="97c97-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="97c97-127">Планирование обмена мгновенными сообщениями и сведений о присутствии в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="97c97-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
