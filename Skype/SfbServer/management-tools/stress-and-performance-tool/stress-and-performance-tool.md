---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Средство "стресс и производительность" в Skype для бизнеса Server 2015 используется при планировании мощности и настройке производительности в непроизводственных и тестовых средах.
ms.openlocfilehash: d82d5ed33e6dca1303aed9f49150dd6b56fc4e1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299518"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="c17f0-103">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="c17f0-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="c17f0-104">Средство "стресс и производительность" в Skype для бизнеса Server 2015 используется при планировании мощности и настройке производительности в непроизводственных и тестовых средах.</span><span class="sxs-lookup"><span data-stu-id="c17f0-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="c17f0-105">Средство "стресс и производительность" в Skype для бизнеса Server 2015 включает инструменты, упрощающие планирование производственных мощностей для Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c17f0-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="c17f0-106">С помощью средства "стресс и производительность" Skype для бизнеса Server 2015 вы можете:</span><span class="sxs-lookup"><span data-stu-id="c17f0-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="c17f0-107">Упростите планирование оборудования для сервера Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c17f0-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="c17f0-108">Расширенные знания и рекомендации по настройке производительности</span><span class="sxs-lookup"><span data-stu-id="c17f0-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="c17f0-109">Измерение производительности развертывания сервера Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c17f0-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="c17f0-110">Обычно это средство используется после использования [средства планирования Skype для бизнеса server 2015](../../management-tools/planning-tool/planning-tool.md) для создания топологии и уточнения топологии с помощью [калькулятора планирования производительности Skype для бизнеса Server 2015](../../management-tools/capacity-planning-calculator.md).</span><span class="sxs-lookup"><span data-stu-id="c17f0-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="c17f0-111">Это средство не будет обновляться для Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c17f0-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="c17f0-112">Тесты</span><span class="sxs-lookup"><span data-stu-id="c17f0-112">Tests</span></span>

<span data-ttu-id="c17f0-113">С помощью средства "стресс и производительность" можно смоделировать эти типы пользовательской нагрузки:</span><span class="sxs-lookup"><span data-stu-id="c17f0-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c17f0-114">Обмен мгновенными сообщениями и присутствие</span><span class="sxs-lookup"><span data-stu-id="c17f0-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="c17f0-115">Голосовые конференции</span><span class="sxs-lookup"><span data-stu-id="c17f0-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="c17f0-116">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="c17f0-116">Application sharing</span></span>  <br/> |<span data-ttu-id="c17f0-117">Голосовая связь по протоколу IP (VoIP), включая эмуляцию коммутируемой телефонной сети (ОКТС)</span><span class="sxs-lookup"><span data-stu-id="c17f0-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="c17f0-118">Конференции на клиентах веб-доступа к Интернету</span><span class="sxs-lookup"><span data-stu-id="c17f0-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="c17f0-119">Автоматический секретарь Конференции</span><span class="sxs-lookup"><span data-stu-id="c17f0-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="c17f0-120">Группы ответа</span><span class="sxs-lookup"><span data-stu-id="c17f0-120">Response Groups</span></span>  <br/> |<span data-ttu-id="c17f0-121">Развертывание списка рассылки</span><span class="sxs-lookup"><span data-stu-id="c17f0-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="c17f0-122">Запрос на загрузку и адресную книгу в адресной книге</span><span class="sxs-lookup"><span data-stu-id="c17f0-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="c17f0-123">Расширенные звонки 911 (E911) и профиль местоположения (абонентская группа)</span><span class="sxs-lookup"><span data-stu-id="c17f0-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="c17f0-124">Многорежимный Просмотр</span><span class="sxs-lookup"><span data-stu-id="c17f0-124">MultiView</span></span>  <br/> |<span data-ttu-id="c17f0-125">Совместная работа с данными</span><span class="sxs-lookup"><span data-stu-id="c17f0-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="c17f0-126">Мобильность</span><span class="sxs-lookup"><span data-stu-id="c17f0-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="c17f0-127">Приложения и файлы, входящие в состав средства "стресс и производительность" в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c17f0-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="c17f0-128">Эти приложения входят в состав средства "стресс и производительность" сервера Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c17f0-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="c17f0-129">**Средств**</span><span class="sxs-lookup"><span data-stu-id="c17f0-129">**Tool**</span></span>|<span data-ttu-id="c17f0-130">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c17f0-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c17f0-131">Усерпровисионингтул. exe</span><span class="sxs-lookup"><span data-stu-id="c17f0-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="c17f0-132">Это средство используется для создания пользователей и контактов.</span><span class="sxs-lookup"><span data-stu-id="c17f0-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="c17f0-133">Усерпрофилеженератор. exe</span><span class="sxs-lookup"><span data-stu-id="c17f0-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="c17f0-134">Используется для настройки характеристик пользовательской нагрузки, которую вы имитируете.</span><span class="sxs-lookup"><span data-stu-id="c17f0-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="c17f0-135">Линкперфтул. exe</span><span class="sxs-lookup"><span data-stu-id="c17f0-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="c17f0-136">Инструмент, имитирующий нагрузку пользователей.</span><span class="sxs-lookup"><span data-stu-id="c17f0-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="c17f0-137">Default. тмкс</span><span class="sxs-lookup"><span data-stu-id="c17f0-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="c17f0-138">Требуется для использования средства ведения журнала в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c17f0-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="c17f0-139">Примеры сценариев подготовки</span><span class="sxs-lookup"><span data-stu-id="c17f0-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="c17f0-140">Используется для настройки топологии для выполняющихся нагрузочных тестов в соответствии с конкретными сценариями.</span><span class="sxs-lookup"><span data-stu-id="c17f0-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="c17f0-141">Вам, возможно, потребуется изменить их, чтобы они были важны для конкретной среды.</span><span class="sxs-lookup"><span data-stu-id="c17f0-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="c17f0-142">Темы в этом разделе</span><span class="sxs-lookup"><span data-stu-id="c17f0-142">Topics in this section</span></span>

<span data-ttu-id="c17f0-143">Если вам нужно получить дополнительные сведения, ознакомьтесь со следующими статьями.</span><span class="sxs-lookup"><span data-stu-id="c17f0-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="c17f0-144">Необходимые компоненты и настройка для средства Stress and Performance Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c17f0-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="c17f0-145">Сценарии производительности для средства "стресс и производительность" в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c17f0-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="c17f0-146">Подготовка топологии для запуска загрузки в сценариях нагрузки и производительности</span><span class="sxs-lookup"><span data-stu-id="c17f0-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="c17f0-147">Настройка политик для средства нагрузки и производительности Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c17f0-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="c17f0-148">Использование средства "стресс и производительность" в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c17f0-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="c17f0-149">Вопросы и ответы о средстве работы и производительности Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c17f0-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

