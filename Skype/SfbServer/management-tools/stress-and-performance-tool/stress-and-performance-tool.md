---
title: Скайп для Business Server 2015 Stress and Performance Tool
ms.author: heidip
author: microsoftheidi
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Скайп для Business Server 2015 Stress and Performance Tool используется при планировании мощности и производительности, помощник по настройке в тестовой или тестовой среды.
ms.openlocfilehash: 0a0a5b17a6e45b2e8944e0e0dd4b3840fc62e102
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="0bbbe-103">Скайп для Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="0bbbe-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="0bbbe-104">Скайп для Business Server 2015 Stress and Performance Tool используется при планировании мощности и производительности, помощник по настройке в тестовой или тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="0bbbe-105">Скайп для Business Server 2015 Stress and Performance Tool включает средства, упрощающие вашей планирование мощности для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="0bbbe-106">Скайп для Business Server 2015 Stress and Performance Tool приведены инструкции по:</span><span class="sxs-lookup"><span data-stu-id="0bbbe-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="0bbbe-107">Упростить планирование для Business Server Скайп оборудования</span><span class="sxs-lookup"><span data-stu-id="0bbbe-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="0bbbe-108">Присвойте увеличено знания и практические советы по оптимизации производительности</span><span class="sxs-lookup"><span data-stu-id="0bbbe-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="0bbbe-109">Измерение производительности вашей Скайп для развертываний Business Server</span><span class="sxs-lookup"><span data-stu-id="0bbbe-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="0bbbe-110">Проектирование топологии и оптимизация топологии с [Скайп для бизнеса 2015 калькулятор емкости Server планирования](../../management-tools/capacity-planning-calculator.md)с помощью [Скайп для средство планирования Business Server 2015](../../management-tools/planning-tool/planning-tool.md) обычно используется это средство.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 
  
## <a name="tests"></a><span data-ttu-id="0bbbe-111">Тесты</span><span class="sxs-lookup"><span data-stu-id="0bbbe-111">Tests</span></span>

<span data-ttu-id="0bbbe-112">Stress and Performance Tool можно смоделировать эти типы пользовательской нагрузки:</span><span class="sxs-lookup"><span data-stu-id="0bbbe-112">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0bbbe-113">Мгновенного обмена Мгновенными сообщениями и присутствия</span><span class="sxs-lookup"><span data-stu-id="0bbbe-113">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="0bbbe-114">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="0bbbe-114">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="0bbbe-115">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="0bbbe-115">Application sharing</span></span>  <br/> |<span data-ttu-id="0bbbe-116">Голосовой связи по протоколу IP (VoIP), включая телефонной сети общего пользования моделирования (PTSN)</span><span class="sxs-lookup"><span data-stu-id="0bbbe-116">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="0bbbe-117">Веб-конференции клиентского доступа</span><span class="sxs-lookup"><span data-stu-id="0bbbe-117">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="0bbbe-118">Автосекретарь конференции</span><span class="sxs-lookup"><span data-stu-id="0bbbe-118">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="0bbbe-119">Группы ответа</span><span class="sxs-lookup"><span data-stu-id="0bbbe-119">Response Groups</span></span>  <br/> |<span data-ttu-id="0bbbe-120">Раскрытие списка рассылки</span><span class="sxs-lookup"><span data-stu-id="0bbbe-120">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="0bbbe-121">Загрузка адресной книги и запросов адресной книги</span><span class="sxs-lookup"><span data-stu-id="0bbbe-121">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="0bbbe-122">Enhanced экстренные вызовы (службы E911) и профиля расположения (абонентской группы)</span><span class="sxs-lookup"><span data-stu-id="0bbbe-122">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="0bbbe-123">MultiView</span><span class="sxs-lookup"><span data-stu-id="0bbbe-123">MultiView</span></span>  <br/> |<span data-ttu-id="0bbbe-124">Совместная работа с данными</span><span class="sxs-lookup"><span data-stu-id="0bbbe-124">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="0bbbe-125">Мобильность</span><span class="sxs-lookup"><span data-stu-id="0bbbe-125">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="0bbbe-126">Приложения и файлы, включенные в состав Скайп для Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="0bbbe-126">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="0bbbe-127">Эти приложения являются частью Скайп для Business Server Stress and Performance Tool:</span><span class="sxs-lookup"><span data-stu-id="0bbbe-127">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="0bbbe-128">**Средство**</span><span class="sxs-lookup"><span data-stu-id="0bbbe-128">**Tool**</span></span>|<span data-ttu-id="0bbbe-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0bbbe-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0bbbe-130">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="0bbbe-130">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="0bbbe-131">Это средство используется для создания пользователей и контактов.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-131">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="0bbbe-132">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="0bbbe-132">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="0bbbe-133">Используется для настройки характеристики нагрузки, в случае моделирования.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-133">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="0bbbe-134">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="0bbbe-134">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="0bbbe-135">Средство, которая моделирует пользовательской нагрузки.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-135">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="0bbbe-136">Default.tmx</span><span class="sxs-lookup"><span data-stu-id="0bbbe-136">Default.tmx</span></span>  <br/> |<span data-ttu-id="0bbbe-137">Для использования Скайп средство ведения журнала 2015 Business Server требуется.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-137">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="0bbbe-138">Подготовка примеры сценариев</span><span class="sxs-lookup"><span data-stu-id="0bbbe-138">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="0bbbe-139">Используется для настройки топологии для запуска нагрузочных тестов, в зависимости от конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-139">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="0bbbe-140">Скорее всего, вам потребуется изменить их, чтобы они соответствовали для используемой среды.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-140">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="0bbbe-141">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="0bbbe-141">Topics in this section</span></span>

<span data-ttu-id="0bbbe-142">Если вам нужно знать более следует ознакомиться со следующими статьями:</span><span class="sxs-lookup"><span data-stu-id="0bbbe-142">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="0bbbe-143">Необходимые условия и программы установки для Скайп для бизнес-Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="0bbbe-143">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="0bbbe-144">Сценарии производительности для Скайп для Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="0bbbe-144">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="0bbbe-145">Подготовка топологии для запуска нагрузки в сценарии нагрузка и производительность</span><span class="sxs-lookup"><span data-stu-id="0bbbe-145">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="0bbbe-146">Настройка политик для Скайп для Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="0bbbe-146">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="0bbbe-147">С помощью Скайп for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="0bbbe-147">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="0bbbe-148">Вопросы и ответы по Скайп для Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="0bbbe-148">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

