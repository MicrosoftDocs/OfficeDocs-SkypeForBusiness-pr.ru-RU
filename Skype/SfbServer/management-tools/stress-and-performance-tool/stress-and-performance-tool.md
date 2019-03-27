---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
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
ms.openlocfilehash: 801a18b4c2cb31cad52cf2d57a661361788844f0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875027"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="e4f05-103">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="e4f05-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="e4f05-104">Скайп для Business Server 2015 Stress and Performance Tool используется при планировании мощности и производительности, помощник по настройке в тестовой или тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="e4f05-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="e4f05-105">Скайп для Business Server 2015 Stress and Performance Tool включает средства, упрощающие вашей планирование мощности для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e4f05-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="e4f05-106">Скайп для Business Server 2015 Stress and Performance Tool приведены инструкции по:</span><span class="sxs-lookup"><span data-stu-id="e4f05-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="e4f05-107">Упростить планирование для Business Server Скайп оборудования</span><span class="sxs-lookup"><span data-stu-id="e4f05-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="e4f05-108">Присвойте увеличено знания и практические советы по оптимизации производительности</span><span class="sxs-lookup"><span data-stu-id="e4f05-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="e4f05-109">Измерение производительности вашей Скайп для развертываний Business Server</span><span class="sxs-lookup"><span data-stu-id="e4f05-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="e4f05-110">Проектирование топологии и оптимизация топологии с [Скайп для бизнеса 2015 калькулятор емкости Server планирования](../../management-tools/capacity-planning-calculator.md)с помощью [Скайп для средство планирования Business Server 2015](../../management-tools/planning-tool/planning-tool.md) обычно используется это средство.</span><span class="sxs-lookup"><span data-stu-id="e4f05-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="e4f05-111">Это средство не будет обновляться для Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4f05-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="e4f05-112">Тесты</span><span class="sxs-lookup"><span data-stu-id="e4f05-112">Tests</span></span>

<span data-ttu-id="e4f05-113">Stress and Performance Tool можно смоделировать эти типы пользовательской нагрузки:</span><span class="sxs-lookup"><span data-stu-id="e4f05-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e4f05-114">Мгновенного обмена Мгновенными сообщениями и присутствия</span><span class="sxs-lookup"><span data-stu-id="e4f05-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="e4f05-115">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="e4f05-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="e4f05-116">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="e4f05-116">Application sharing</span></span>  <br/> |<span data-ttu-id="e4f05-117">Голосовой связи по протоколу IP (VoIP), включая телефонной сети общего пользования моделирования (PTSN)</span><span class="sxs-lookup"><span data-stu-id="e4f05-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="e4f05-118">Веб-конференции клиентского доступа</span><span class="sxs-lookup"><span data-stu-id="e4f05-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="e4f05-119">Автосекретарь конференции</span><span class="sxs-lookup"><span data-stu-id="e4f05-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="e4f05-120">Группы ответа</span><span class="sxs-lookup"><span data-stu-id="e4f05-120">Response Groups</span></span>  <br/> |<span data-ttu-id="e4f05-121">Раскрытие списка рассылки</span><span class="sxs-lookup"><span data-stu-id="e4f05-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="e4f05-122">Загрузка адресной книги и запросов адресной книги</span><span class="sxs-lookup"><span data-stu-id="e4f05-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="e4f05-123">Enhanced экстренные вызовы (службы E911) и профиля расположения (абонентской группы)</span><span class="sxs-lookup"><span data-stu-id="e4f05-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="e4f05-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="e4f05-124">MultiView</span></span>  <br/> |<span data-ttu-id="e4f05-125">Совместная работа с данными</span><span class="sxs-lookup"><span data-stu-id="e4f05-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="e4f05-126">Мобильность</span><span class="sxs-lookup"><span data-stu-id="e4f05-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="e4f05-127">Приложения и файлы, включенные в состав Скайп для Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="e4f05-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="e4f05-128">Эти приложения являются частью Скайп для Business Server Stress and Performance Tool:</span><span class="sxs-lookup"><span data-stu-id="e4f05-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="e4f05-129">**Средство**</span><span class="sxs-lookup"><span data-stu-id="e4f05-129">**Tool**</span></span>|<span data-ttu-id="e4f05-130">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="e4f05-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e4f05-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="e4f05-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="e4f05-132">Это средство используется для создания пользователей и контактов.</span><span class="sxs-lookup"><span data-stu-id="e4f05-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="e4f05-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="e4f05-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="e4f05-134">Используется для настройки характеристики нагрузки, в случае моделирования.</span><span class="sxs-lookup"><span data-stu-id="e4f05-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="e4f05-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="e4f05-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="e4f05-136">Средство, которая моделирует пользовательской нагрузки.</span><span class="sxs-lookup"><span data-stu-id="e4f05-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="e4f05-137">Default.tmx</span><span class="sxs-lookup"><span data-stu-id="e4f05-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="e4f05-138">Для использования Скайп средство ведения журнала 2015 Business Server требуется.</span><span class="sxs-lookup"><span data-stu-id="e4f05-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="e4f05-139">Подготовка примеры сценариев</span><span class="sxs-lookup"><span data-stu-id="e4f05-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="e4f05-140">Используется для настройки топологии для запуска нагрузочных тестов, в зависимости от конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="e4f05-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="e4f05-141">Скорее всего, вам потребуется изменить их, чтобы они соответствовали для используемой среды.</span><span class="sxs-lookup"><span data-stu-id="e4f05-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="e4f05-142">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e4f05-142">Topics in this section</span></span>

<span data-ttu-id="e4f05-143">Если вам нужно знать более следует ознакомиться со следующими статьями:</span><span class="sxs-lookup"><span data-stu-id="e4f05-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="e4f05-144">Необходимые компоненты и настройка для средства Stress and Performance Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e4f05-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="e4f05-145">Сценарии производительности для Скайп для Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="e4f05-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="e4f05-146">Подготовка топологии для запуска нагрузки в сценарии нагрузка и производительность</span><span class="sxs-lookup"><span data-stu-id="e4f05-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="e4f05-147">Настройка политик для Скайп для Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="e4f05-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="e4f05-148">С помощью Скайп for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="e4f05-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="e4f05-149">Вопросы и ответы по Скайп для Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="e4f05-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

