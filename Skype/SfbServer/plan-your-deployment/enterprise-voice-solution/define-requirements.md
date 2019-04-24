---
title: Определение требований для экстренных вызовов в Скайп для Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: Представлены действия, необходимые для включения E9-1-1 в Скайп Business Server корпоративной голосовой связи, в зависимости от того, есть ли у поставщика услуг E9-1-1 магистрали SIP или шлюз ELIN.
ms.openlocfilehash: 3ddcb25b86689f29831872f24a1893d5ff2f1f4c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206980"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="64984-103">Определение требований для экстренных вызовов в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="64984-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="64984-104">Представлены действия, необходимые для включения E9-1-1 в Скайп Business Server корпоративной голосовой связи, в зависимости от того, есть ли у поставщика услуг E9-1-1 магистрали SIP или шлюз ELIN.</span><span class="sxs-lookup"><span data-stu-id="64984-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="64984-105">Прежде чем начать Скайп для развертывания сервера Business E9-1-1, сначала можно ответить на вопросы, описанные в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="64984-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="64984-106">Необходимое планирование зависит от типа решения E9-1-1, которое планируется разворачивать — канал SIP для подключения к поставщику услуг E9-1-1 или шлюз ELIN.</span><span class="sxs-lookup"><span data-stu-id="64984-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="64984-107">В следующей таблице указаны разделы в этой книге планирования, который необходимо просмотреть для каждого из этих решений.</span><span class="sxs-lookup"><span data-stu-id="64984-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="64984-108">**Этапы планирования типа решения E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="64984-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="64984-109">**Поставщик услуг по каналу SIP**</span><span class="sxs-lookup"><span data-stu-id="64984-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="64984-110">**Шлюз ELIN**</span><span class="sxs-lookup"><span data-stu-id="64984-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="64984-111">Определение области развертывания E9-1-1 в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="64984-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="64984-112">Определение области развертывания E9-1-1 в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="64984-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="64984-113">Определение сетевых элементов, используемых для определения местоположения в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="64984-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="64984-114">Определение сетевых элементов, используемых для определения местоположения в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="64984-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="64984-115">Включение пользователей для E9-1-1 в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="64984-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="64984-116">Включение пользователей для E9-1-1 в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="64984-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="64984-117">Управление расположениями для поставщиков услуг каналов SIP в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="64984-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="64984-118">Управление расположениями для шлюзов ELIN в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="64984-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="64984-119">Определение пользовательского интерфейса для получения местоположения в Скайп для Business Server вручную</span><span class="sxs-lookup"><span data-stu-id="64984-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="64984-120">Определение пользовательского интерфейса для получения местоположения в Скайп для Business Server вручную</span><span class="sxs-lookup"><span data-stu-id="64984-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="64984-121">Проектирование канала SIP для E9-1-1 в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="64984-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="64984-122">Включить службу безопасности в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="64984-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="64984-123">Включить службу безопасности в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="64984-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="64984-124">Планирование политик расположения Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="64984-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="64984-125">Выбор поставщика услуг E9-1-1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="64984-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="64984-126">Назначение области политики расположения в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="64984-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="64984-127">Планирование политик расположения Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="64984-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="64984-128">Назначение области политики расположения в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="64984-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

