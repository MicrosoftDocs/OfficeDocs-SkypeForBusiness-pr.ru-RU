---
title: Служба элементов для панели мониторинга качества звонков (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Сводка: сведения о службе элементов, которая входит в API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 585ba97d9dedbfcbbd572069a792a121e6156afe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274613"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="80034-104">Служба элементов для панели мониторинга качества звонков (CQD)</span><span class="sxs-lookup"><span data-stu-id="80034-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="80034-105">**Сводка:** Сведения о службе элементов, которая входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="80034-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="80034-106">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="80034-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="80034-107">Служба item входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="80034-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="80034-108">Служба элемента</span><span class="sxs-lookup"><span data-stu-id="80034-108">Item Service</span></span>

<span data-ttu-id="80034-109">API репозитория — это простая служба управления содержимым, называемая "служба элемента", которая может использоваться для хранения любого содержимого, определенного приложением, для пользователей.</span><span class="sxs-lookup"><span data-stu-id="80034-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="80034-110">Содержимое системы принадлежит пользователю системы и предоставляется всем пользователям, у которых есть доступ только для чтения.</span><span class="sxs-lookup"><span data-stu-id="80034-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="80034-111">Выделенные пользователи принадлежат обычным пользователям, а только владельцы могут изменять или удалять их, но все пользователи по-прежнему имеют доступ к ним только для чтения.</span><span class="sxs-lookup"><span data-stu-id="80034-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="80034-112">Эта документация по API охватывает операции, предназначенные только для чтения, для API репозитория.</span><span class="sxs-lookup"><span data-stu-id="80034-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="80034-113">Панель мониторинга качества звонка сохраняет отчеты и запросы как элементы в базе данных репозитория.</span><span class="sxs-lookup"><span data-stu-id="80034-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="80034-114">Элемент может иметь необязательные дочерние элементы, а панель мониторинга качества вызова упорядочивает отчеты и запросы в иерархической структуре с помощью функции вложенных элементов.</span><span class="sxs-lookup"><span data-stu-id="80034-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="80034-115">Служба номенклатуры включает следующие основные понятия:</span><span class="sxs-lookup"><span data-stu-id="80034-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="80034-116">**Item** — базовый элемент репозитория.</span><span class="sxs-lookup"><span data-stu-id="80034-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="80034-117">Каждый элемент принадлежит только одному пользователю.</span><span class="sxs-lookup"><span data-stu-id="80034-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="80034-118">**Дочерний элемент** — базовый стратегический механизм репозитория.</span><span class="sxs-lookup"><span data-stu-id="80034-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="80034-119">Элемент может иметь ноль, один или несколько подчиненных элементов.</span><span class="sxs-lookup"><span data-stu-id="80034-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="80034-120">**Родительский** элемент — список элементов, начиная с самого верхнего элемента, который является элементом по умолчанию для пользователя, что приводит к заданному элементу.</span><span class="sxs-lookup"><span data-stu-id="80034-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="80034-121">**Содержимое элемента** — содержимое, зависящее от приложения, которое хранится в элементах.</span><span class="sxs-lookup"><span data-stu-id="80034-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="80034-122">Информационная панель "качество звонка" позволяет экономить представления отчетов и запросов в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="80034-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="80034-123">Операции RESTFUL включены в таблицу ниже.</span><span class="sxs-lookup"><span data-stu-id="80034-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="80034-124">**Операция**</span><span class="sxs-lookup"><span data-stu-id="80034-124">**Operation**</span></span>|<span data-ttu-id="80034-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="80034-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="80034-126">Получение элементов</span><span class="sxs-lookup"><span data-stu-id="80034-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="80034-127">Функция Get Items возвращает все элементы в репозитории.</span><span class="sxs-lookup"><span data-stu-id="80034-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="80034-128">Получение элемента</span><span class="sxs-lookup"><span data-stu-id="80034-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="80034-129">Функция Get Item возвращает определенный элемент.</span><span class="sxs-lookup"><span data-stu-id="80034-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="80034-130">Получение вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="80034-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="80034-131">Функция "получить вложенные элементы" Возвращает вложенные элементы определенного элемента.</span><span class="sxs-lookup"><span data-stu-id="80034-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="80034-132">Получить родительских элементов</span><span class="sxs-lookup"><span data-stu-id="80034-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="80034-133">Получение предков элемента возвращает предков определенного элемента.</span><span class="sxs-lookup"><span data-stu-id="80034-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="80034-134">Обновление элемента</span><span class="sxs-lookup"><span data-stu-id="80034-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="80034-135">Обновление определенного элемента в репозитории.</span><span class="sxs-lookup"><span data-stu-id="80034-135">Update a specific item in the repository.</span></span>  <br/> |
   

