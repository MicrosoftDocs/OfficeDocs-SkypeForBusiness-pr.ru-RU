---
title: Определение требований для экстренных вызовов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: В этой статье описаны действия, необходимые для включения E9-1-1 в Skype для бизнеса Server Enterprise, в зависимости от того, есть ли у вас служба магистральной магистрали E9-1-1 или шлюз Елин.
ms.openlocfilehash: ffda7796390fea6c44d943770c9b4af6d299549a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803089"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="6f6d6-103">Определение требований для экстренных вызовов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="6f6d6-104">В этой статье описаны действия, необходимые для включения E9-1-1 в Skype для бизнеса Server Enterprise, в зависимости от того, есть ли у вас служба магистральной магистрали E9-1-1 или шлюз Елин.</span><span class="sxs-lookup"><span data-stu-id="6f6d6-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="6f6d6-105">Прежде чем приступить к установке Skype для бизнеса Server E9-1-1, вы должны получить ответы на вопросы, описанные в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="6f6d6-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="6f6d6-106">Необходимое планирование зависит от типа решения E9-1-1, которое планируется разворачивать — канал SIP для подключения к поставщику услуг E9-1-1 или шлюз ELIN.</span><span class="sxs-lookup"><span data-stu-id="6f6d6-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="6f6d6-107">В следующей таблице указаны разделы в этой книге планирования, которые необходимо просмотреть для каждого из этих решений.</span><span class="sxs-lookup"><span data-stu-id="6f6d6-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="6f6d6-108">**Этапы планирования типа решения E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="6f6d6-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="6f6d6-109">**Поставщик услуг по каналу SIP**</span><span class="sxs-lookup"><span data-stu-id="6f6d6-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="6f6d6-110">**Шлюз ELIN**</span><span class="sxs-lookup"><span data-stu-id="6f6d6-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="6f6d6-111">Определение области развертывания E9-1-1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="6f6d6-112">Определение области развертывания E9-1-1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="6f6d6-113">Определение сетевых элементов, используемых для определения местоположения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="6f6d6-114">Определение сетевых элементов, используемых для определения местоположения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="6f6d6-115">Включение пользователей для E9-1-1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="6f6d6-116">Включение пользователей для E9-1-1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="6f6d6-117">Управление разположениями для провайдеров услуг магистральной магистрали SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="6f6d6-118">Управление расположением для шлюзов Елин в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="6f6d6-119">Определение взаимодействия с пользователем при получении местоположения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="6f6d6-120">Определение взаимодействия с пользователем при получении местоположения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="6f6d6-121">Проектирование магистральной магистрали SIP для E9-1-1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="6f6d6-122">Включите службу безопасности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="6f6d6-123">Включите службу безопасности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="6f6d6-124">Планирование политик местоположения для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="6f6d6-125">Выбор поставщика услуг E9-1-1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="6f6d6-126">Назначение области политики местоположения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="6f6d6-127">Планирование политик местоположения для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="6f6d6-128">Назначение области политики местоположения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f6d6-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

