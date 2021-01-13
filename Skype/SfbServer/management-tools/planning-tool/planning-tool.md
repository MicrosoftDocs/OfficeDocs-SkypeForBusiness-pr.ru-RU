---
title: Средство планирования Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: aef46fac65ba1d5651cada81bc79cfc21021bf54
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832389"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="bd8fe-103">Средство планирования Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="bd8fe-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="bd8fe-104">Руководство по использованию средства планирования Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bd8fe-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="bd8fe-105">Средство планирования Skype для бизнеса Server 2015 — это инструмент, управляемый мастером и похожий на собеседование, который задает вопросы о проектной топологии Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bd8fe-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="bd8fe-106">Средство планирования использует предоставленную информацию в сочетании с предпочтительными методиками проектирования топологии и емкости, чтобы представить рекомендуемую топологию на основе предоставленных ответов.</span><span class="sxs-lookup"><span data-stu-id="bd8fe-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="bd8fe-107">Вы можете скачать средство планирования [из средства планирования Skype для бизнеса Server 2015.](https://go.microsoft.com/fwlink/p/?LinkID=282725)</span><span class="sxs-lookup"><span data-stu-id="bd8fe-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="bd8fe-108">В конечном счете цель средства планирования — упростить разработку полной топологии Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bd8fe-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="bd8fe-109">Это средство также предоставляет контекстные ссылки на документацию по планированию и развертыванию в средстве при условии, что для подключения к веб-сайту Майкрософт доступно подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="bd8fe-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="bd8fe-110">После настройки топологии с помощью TCP/IP-адресов инфраструктуры и полного доменного имени (FQDNs) средство планирования создает серию отчетов, в которых освещаются имена службы доменных имен (DNS), правила брандмауэра, сертификаты и т. д.</span><span class="sxs-lookup"><span data-stu-id="bd8fe-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="bd8fe-111">Использование этого средства является первым этапом планирования реализации.</span><span class="sxs-lookup"><span data-stu-id="bd8fe-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="bd8fe-112">Следующим шагом будет ввод сведений о сайте в калькулятор емкости Skype для бизнеса [Server 2015,](https://www.microsoft.com/download/details.aspx?id=51196)настройка при необходимости, а затем использование средства Stress and Performance Skype для бизнеса [Server 2015 для](https://www.microsoft.com/download/details.aspx?id=50367) моделирования и проверки того, что реализация будет обслуживать ваши потребности.</span><span class="sxs-lookup"><span data-stu-id="bd8fe-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="bd8fe-113">Средство планирования также предоставляет возможность экспорта информации в двух форматах:</span><span class="sxs-lookup"><span data-stu-id="bd8fe-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="bd8fe-114">Microsoft Excel (таблица XML)</span><span class="sxs-lookup"><span data-stu-id="bd8fe-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="bd8fe-115">Microsoft Visio (VDX)</span><span class="sxs-lookup"><span data-stu-id="bd8fe-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="bd8fe-116">В следующих темах подробно и подробно приводится средство планирования.</span><span class="sxs-lookup"><span data-stu-id="bd8fe-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="bd8fe-117">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="bd8fe-117">In this section</span></span>

- [<span data-ttu-id="bd8fe-118">Установка средства планирования в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="bd8fe-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="bd8fe-119">Необязательное программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="bd8fe-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="bd8fe-120">Навигация по средству планирования в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="bd8fe-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="bd8fe-121">Создание начального проекта топологии для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="bd8fe-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="bd8fe-122">Изменение топологии в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="bd8fe-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="bd8fe-123">Изменение схемы конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="bd8fe-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="bd8fe-124">Просмотр отчетов администратора в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="bd8fe-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="bd8fe-125">См. также</span><span class="sxs-lookup"><span data-stu-id="bd8fe-125">See also</span></span>

[<span data-ttu-id="bd8fe-126">Установка Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="bd8fe-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="bd8fe-127">Планирование обмена мгновенными сообщениями и присутствия в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="bd8fe-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
