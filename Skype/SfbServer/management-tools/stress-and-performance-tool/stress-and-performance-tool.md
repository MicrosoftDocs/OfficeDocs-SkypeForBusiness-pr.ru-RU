---
title: Skype для бизнеса Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Средство "Нагрузка и производительность Skype для бизнеса Server 2015" используется при планировании емкости и настройке производительности в непроизводивых или тестовых средах.
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814929"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="51eff-103">Skype для бизнеса Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="51eff-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="51eff-104">Средство "Нагрузка и производительность Skype для бизнеса Server 2015" используется при планировании емкости и настройке производительности в непроизводивых или тестовых средах.</span><span class="sxs-lookup"><span data-stu-id="51eff-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="51eff-105">Skype для бизнеса Server 2015 Stress and Performance Tool включает средства, которые упростят планирование емкости для Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="51eff-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="51eff-106">Skype для бизнеса Server 2015 Stress and Performance Tool поможет вам:</span><span class="sxs-lookup"><span data-stu-id="51eff-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="51eff-107">Упрощение планирования оборудования для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="51eff-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="51eff-108">Повышение знаний и лучшие методики настройки производительности</span><span class="sxs-lookup"><span data-stu-id="51eff-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="51eff-109">Измерение производительности развертывания Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="51eff-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="51eff-110">Обычно это средство используется после использования средства планирования Skype для бизнеса [Server 2015](../../management-tools/planning-tool/planning-tool.md) для разработки топологии и уточнения топологии с помощью калькулятора планирования мощности Skype для бизнеса [Server 2015.](../../management-tools/capacity-planning-calculator.md)</span><span class="sxs-lookup"><span data-stu-id="51eff-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="51eff-111">Это средство не будет обновлено для Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="51eff-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="51eff-112">Тесты</span><span class="sxs-lookup"><span data-stu-id="51eff-112">Tests</span></span>

<span data-ttu-id="51eff-113">Средство Stress and Performance может имитировать эти типы пользовательской нагрузки:</span><span class="sxs-lookup"><span data-stu-id="51eff-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="51eff-114">Обмен мгновенными сообщениями и присутствие</span><span class="sxs-lookup"><span data-stu-id="51eff-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="51eff-115">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="51eff-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="51eff-116">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="51eff-116">Application sharing</span></span>  <br/> |<span data-ttu-id="51eff-117">VoIP, в том числе имитация телефонной сети общего перейти на телефонную сеть (ТСТС)</span><span class="sxs-lookup"><span data-stu-id="51eff-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="51eff-118">Клиентская веб-трансляция</span><span class="sxs-lookup"><span data-stu-id="51eff-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="51eff-119">Автоконференции</span><span class="sxs-lookup"><span data-stu-id="51eff-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="51eff-120">Группы ответа</span><span class="sxs-lookup"><span data-stu-id="51eff-120">Response Groups</span></span>  <br/> |<span data-ttu-id="51eff-121">Расширение списка рассылки</span><span class="sxs-lookup"><span data-stu-id="51eff-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="51eff-122">Запрос на скачивание адресной книги и адресную книгу</span><span class="sxs-lookup"><span data-stu-id="51eff-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="51eff-123">Вызовы Enhanced 911 (E911) и профиль местоположения (dial plan)</span><span class="sxs-lookup"><span data-stu-id="51eff-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="51eff-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="51eff-124">MultiView</span></span>  <br/> |<span data-ttu-id="51eff-125">Совместная работа с данными</span><span class="sxs-lookup"><span data-stu-id="51eff-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="51eff-126">Мобильность</span><span class="sxs-lookup"><span data-stu-id="51eff-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="51eff-127">Приложения и файлы, включенные в средство Stress and Performance Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="51eff-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="51eff-128">Эти приложения являются частью средства Skype для бизнеса Server Stress and Performance Tool:</span><span class="sxs-lookup"><span data-stu-id="51eff-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="51eff-129">**Средство**</span><span class="sxs-lookup"><span data-stu-id="51eff-129">**Tool**</span></span>|<span data-ttu-id="51eff-130">**Описание**</span><span class="sxs-lookup"><span data-stu-id="51eff-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="51eff-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="51eff-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="51eff-132">Это средство используется для создания пользователей и контактов.</span><span class="sxs-lookup"><span data-stu-id="51eff-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="51eff-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="51eff-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="51eff-134">Используется для настройки характеристик пользовательской нагрузки, которая имитируется.</span><span class="sxs-lookup"><span data-stu-id="51eff-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="51eff-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="51eff-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="51eff-136">Средство для имитации пользовательской нагрузки.</span><span class="sxs-lookup"><span data-stu-id="51eff-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="51eff-137">Default.tmx</span><span class="sxs-lookup"><span data-stu-id="51eff-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="51eff-138">Требуется для использования средства ведения журнала Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="51eff-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="51eff-139">Примеры сценариев предоставления</span><span class="sxs-lookup"><span data-stu-id="51eff-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="51eff-140">Используется для настройки топологии для запуска нагрузок в зависимости от конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="51eff-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="51eff-141">Скорее всего, вам потребуется изменить их, чтобы сделать их релевантными для конкретной среды.</span><span class="sxs-lookup"><span data-stu-id="51eff-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="51eff-142">Разделы в этом разделе</span><span class="sxs-lookup"><span data-stu-id="51eff-142">Topics in this section</span></span>

<span data-ttu-id="51eff-143">Если вам нужно узнать больше, просмотрите следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="51eff-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="51eff-144">Необходимые условия и настройка средства "Нагрузка и производительность Skype для шин"</span><span class="sxs-lookup"><span data-stu-id="51eff-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="51eff-145">Сценарии производительности для средства "Нагрузка и производительность Skype для бизнеса Server 2015"</span><span class="sxs-lookup"><span data-stu-id="51eff-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="51eff-146">Подготовка топологии для запуска нагрузки в сценариях stress и Performance</span><span class="sxs-lookup"><span data-stu-id="51eff-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="51eff-147">Настройка политик для средства "Нагрузка и производительность Skype для бизнеса Server 2015"</span><span class="sxs-lookup"><span data-stu-id="51eff-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="51eff-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="51eff-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="51eff-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="51eff-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

