---
title: Служба элементов для панели мониторинга качества вызовов (CQD)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: Сводка. Сведения о службе элементов, которая входит в API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: b904f814a837af13e4015af5fbaca924739b8997
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827709"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="6ae23-104">Служба элементов для панели мониторинга качества вызовов (CQD)</span><span class="sxs-lookup"><span data-stu-id="6ae23-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="6ae23-105">**Сводка:** Узнайте о службе item, которая является частью API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="6ae23-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="6ae23-106">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6ae23-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="6ae23-107">Служба элементов является частью API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="6ae23-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="6ae23-108">Служба элемента</span><span class="sxs-lookup"><span data-stu-id="6ae23-108">Item Service</span></span>

<span data-ttu-id="6ae23-109">API репозитория предлагает простую службу управления контентом, которая называется службой элементов, которая может использоваться для хранения любого контента, определенного приложением, для пользователей.</span><span class="sxs-lookup"><span data-stu-id="6ae23-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="6ae23-110">Содержимое системы принадлежит системным пользователям и совместное для всех пользователей с доступом только для чтения.</span><span class="sxs-lookup"><span data-stu-id="6ae23-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="6ae23-111">Содержимое выделенного пользователя принадлежит обычным пользователям, и только владельцы могут изменять или удалять их, но все пользователи по-прежнему имеют доступ только для чтения.</span><span class="sxs-lookup"><span data-stu-id="6ae23-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6ae23-112">Эта документация по API охватывает операции API репозитория только для чтения.</span><span class="sxs-lookup"><span data-stu-id="6ae23-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="6ae23-113">Панель мониторинга качества вызовов сохраняет отчеты и запросы в качестве элементов в базе данных репозитория.</span><span class="sxs-lookup"><span data-stu-id="6ae23-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="6ae23-114">Элемент может иметь необязательные подустанавли, а панель мониторинга качества вызовов упорядожит отчеты и запросы в иерархической структуре с помощью функции в субстантов.</span><span class="sxs-lookup"><span data-stu-id="6ae23-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="6ae23-115">Служба элементов включает следующие понятия:</span><span class="sxs-lookup"><span data-stu-id="6ae23-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="6ae23-116">**Item** — базовый элемент репозитория.</span><span class="sxs-lookup"><span data-stu-id="6ae23-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="6ae23-117">Каждый элемент принадлежит только одному пользователю.</span><span class="sxs-lookup"><span data-stu-id="6ae23-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="6ae23-118">**Sub-Item** — базовая организационная механика репозитория.</span><span class="sxs-lookup"><span data-stu-id="6ae23-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="6ae23-119">Элемент может иметь ноль, один или несколько подчиненных элементов.</span><span class="sxs-lookup"><span data-stu-id="6ae23-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="6ae23-120">**"Предки элементов"** — список элементов, начиная с самого верхнего элемента, который является элементом пользователя по умолчанию, что приводит к заданным элементам.</span><span class="sxs-lookup"><span data-stu-id="6ae23-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="6ae23-121">**Контент элементов** — контент, хранимый в элементах для конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="6ae23-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="6ae23-122">Панель мониторинга качества вызовов сохраняет представления отчетов и запросов в содержимом в JSON.</span><span class="sxs-lookup"><span data-stu-id="6ae23-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="6ae23-123">Операции REST включены в следующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="6ae23-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="6ae23-124">**Операция**</span><span class="sxs-lookup"><span data-stu-id="6ae23-124">**Operation**</span></span>|<span data-ttu-id="6ae23-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6ae23-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="6ae23-126">Получение элементов</span><span class="sxs-lookup"><span data-stu-id="6ae23-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="6ae23-127">При этом возвращаются все элементы в репозитории.</span><span class="sxs-lookup"><span data-stu-id="6ae23-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="6ae23-128">Получение элемента</span><span class="sxs-lookup"><span data-stu-id="6ae23-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="6ae23-129">Get Item returns a specific Item.</span><span class="sxs-lookup"><span data-stu-id="6ae23-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="6ae23-130">Получение вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="6ae23-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="6ae23-131">При Sub-Items возвращается подгруппа определенного элемента.</span><span class="sxs-lookup"><span data-stu-id="6ae23-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="6ae23-132">Получить родительских элементов</span><span class="sxs-lookup"><span data-stu-id="6ae23-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="6ae23-133">Get Item Ancestors returns a specific Item's ancestors.</span><span class="sxs-lookup"><span data-stu-id="6ae23-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="6ae23-134">Обновление элемента</span><span class="sxs-lookup"><span data-stu-id="6ae23-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="6ae23-135">Обновление определенного элемента в репозитории.</span><span class="sxs-lookup"><span data-stu-id="6ae23-135">Update a specific item in the repository.</span></span>  <br/> |
   

