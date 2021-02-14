---
title: Определение требований к экстренным вызовам в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: Суммирует действия, необходимые для включения E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь в зависимости от того, есть ли у вас поставщик услуг E9-1-1 магистрали SIP или шлюз ELIN.
ms.openlocfilehash: 8efd38657a80bee1ecd979e8730feacfb980053e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825819"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="511a5-103">Определение требований к экстренным вызовам в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="511a5-104">Суммирует действия, необходимые для включения E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь в зависимости от того, есть ли у вас поставщик услуг E9-1-1 магистрали SIP или шлюз ELIN.</span><span class="sxs-lookup"><span data-stu-id="511a5-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="511a5-105">Прежде чем приступить к развертыванию Skype для бизнеса Server E9-1-1, необходимо сначала ответить на вопросы, которые подробно описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="511a5-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="511a5-106">Необходимое планирование зависит от типа решения E9-1-1, которое планируется разворачивать — канал SIP для подключения к поставщику услуг E9-1-1  или шлюз ELIN.</span><span class="sxs-lookup"><span data-stu-id="511a5-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="511a5-107">В следующей таблице указаны разделы в этой книге планирования, которые необходимо просмотреть для каждого из этих решений.</span><span class="sxs-lookup"><span data-stu-id="511a5-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="511a5-108">**Этапы планирования типа решения E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="511a5-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="511a5-109">**Поставщик услуг по каналу SIP**</span><span class="sxs-lookup"><span data-stu-id="511a5-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="511a5-110">**Шлюз ELIN**</span><span class="sxs-lookup"><span data-stu-id="511a5-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="511a5-111">Определение области развертывания E9-1-1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="511a5-112">Определение области развертывания E9-1-1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="511a5-113">Определение элементов сети, используемых для определения расположения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="511a5-114">Определение элементов сети, используемых для определения расположения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="511a5-115">Enable users for E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="511a5-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="511a5-116">Enable users for E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="511a5-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="511a5-117">Управление расположениями для поставщиков услуг магистрали SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="511a5-118">Управление расположениями для шлюзов ELIN в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="511a5-119">Определение пользовательского интерфейса для получения расположения вручную в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="511a5-120">Определение пользовательского интерфейса для получения расположения вручную в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="511a5-121">Разработка магистрали SIP для E9-1-1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="511a5-122">Включить службу безопасности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="511a5-123">Включить службу безопасности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="511a5-124">Планирование политик расположения для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="511a5-125">Выбор поставщика услуг E9-1-1 для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="511a5-126">Назначение области политики расположения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="511a5-127">Планирование политик расположения для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="511a5-128">Назначение области политики расположения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="511a5-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

