---
title: Служба элемента для панели мониторинга качества звонков (CQD)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: ': Сводка сведения о службе элемента, который является частью API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.'
ms.openlocfilehash: 28a705d488519e439a0fd4c9c9345b1d540fd949
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217819"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="16d97-104">Служба элемента для панели мониторинга качества звонков (CQD)</span><span class="sxs-lookup"><span data-stu-id="16d97-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="16d97-105">**Сводка:** Сведения о службе элемента, который является частью API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="16d97-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="16d97-106">Панель мониторинга качества звонков — это средство для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="16d97-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="16d97-107">Служба элемент является частью API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="16d97-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="16d97-108">Служба элемента</span><span class="sxs-lookup"><span data-stu-id="16d97-108">Item Service</span></span>

<span data-ttu-id="16d97-109">API репозитория предлагает службы простое управление содержимым, известных как службы элемента, который может использоваться для хранения содержимого определенного приложения для пользователей.</span><span class="sxs-lookup"><span data-stu-id="16d97-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="16d97-110">Компоненты системы владеет пользователь системы и общие для всех пользователей с доступом только для чтения.</span><span class="sxs-lookup"><span data-stu-id="16d97-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="16d97-111">Содержимое выделенного пользователя принадлежат обычных пользователей только владельцы сайтов могут изменять или удалять их, а все пользователи по-прежнему имеют доступ только для чтения к ним.</span><span class="sxs-lookup"><span data-stu-id="16d97-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="16d97-112">В этой документации API охватывает только для чтения operations API репозитория.</span><span class="sxs-lookup"><span data-stu-id="16d97-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="16d97-113">Панель мониторинга качества звонков сохраняет отчеты и запросы как элементы в базе данных репозитория.</span><span class="sxs-lookup"><span data-stu-id="16d97-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="16d97-114">Элемент может содержать необязательные вложенные элементы и панель мониторинга качества звонков собирает отчеты и запросы в иерархической структуры, с помощью функции дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="16d97-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="16d97-115">Элемент Служба включает в себя следующие понятия:</span><span class="sxs-lookup"><span data-stu-id="16d97-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="16d97-116">**Элемент** - основных элементов репозитория.</span><span class="sxs-lookup"><span data-stu-id="16d97-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="16d97-117">Каждый элемент принадлежит только один пользователь.</span><span class="sxs-lookup"><span data-stu-id="16d97-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="16d97-118">**Дочерний элемент** — основной организационной механизм репозитория.</span><span class="sxs-lookup"><span data-stu-id="16d97-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="16d97-119">Элемент может иметь нулевую, одну или несколько подчиненных элементов.</span><span class="sxs-lookup"><span data-stu-id="16d97-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="16d97-120">**Элемент предков** - списка элементов "," Приступая к работе с элемент верхнего уровня, который используется по умолчанию элемента пользователя, приводя к данного элемента.</span><span class="sxs-lookup"><span data-stu-id="16d97-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="16d97-121">**Содержимое элемента** - содержимого конкретного приложения, хранимых в элементах.</span><span class="sxs-lookup"><span data-stu-id="16d97-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="16d97-122">Панель мониторинга качества звонков сохраняет JSON представлений отчетов и запросов в содержимое.</span><span class="sxs-lookup"><span data-stu-id="16d97-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="16d97-123">В следующей таблице включены операции REST.</span><span class="sxs-lookup"><span data-stu-id="16d97-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="16d97-124">**Операция**</span><span class="sxs-lookup"><span data-stu-id="16d97-124">**Operation**</span></span>|<span data-ttu-id="16d97-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="16d97-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="16d97-126">Получение элементов</span><span class="sxs-lookup"><span data-stu-id="16d97-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="16d97-127">Получение элементов возвращает все элементы в репозитории.</span><span class="sxs-lookup"><span data-stu-id="16d97-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="16d97-128">Получение элемента</span><span class="sxs-lookup"><span data-stu-id="16d97-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="16d97-129">Получение элемента возвращает конкретный элемент.</span><span class="sxs-lookup"><span data-stu-id="16d97-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="16d97-130">Получение вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="16d97-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="16d97-131">Получите вложенные элементы возвращает конкретный элемент вложенные элементы.</span><span class="sxs-lookup"><span data-stu-id="16d97-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="16d97-132">Получить родительских элементов</span><span class="sxs-lookup"><span data-stu-id="16d97-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="16d97-133">Элемент предков Get возвращает конкретный элемент предков.</span><span class="sxs-lookup"><span data-stu-id="16d97-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="16d97-134">Обновление элемента</span><span class="sxs-lookup"><span data-stu-id="16d97-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="16d97-135">Обновления определенного элемента в репозитории.</span><span class="sxs-lookup"><span data-stu-id="16d97-135">Update a specific item in the repository.</span></span>  <br/> |
   

