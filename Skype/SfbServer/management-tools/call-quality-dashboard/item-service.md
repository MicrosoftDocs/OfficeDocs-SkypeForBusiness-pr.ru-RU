---
title: Служба элементов для панели мониторинга качества звонков (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Сводка: сведения о службе элементов, которая входит в API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 5fdf2aedcb1a5e8d7d1929d7af70c5911cae46f0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816718"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="05281-104">Служба элементов для панели мониторинга качества звонков (CQD)</span><span class="sxs-lookup"><span data-stu-id="05281-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="05281-105">**Сводка:** Сведения о службе элементов, которая входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="05281-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="05281-106">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="05281-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="05281-107">Служба item входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="05281-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="05281-108">Служба элемента</span><span class="sxs-lookup"><span data-stu-id="05281-108">Item Service</span></span>

<span data-ttu-id="05281-109">API репозитория — это простая служба управления содержимым, называемая "служба элемента", которая может использоваться для хранения любого содержимого, определенного приложением, для пользователей.</span><span class="sxs-lookup"><span data-stu-id="05281-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="05281-110">Содержимое системы принадлежит пользователю системы и предоставляется всем пользователям, у которых есть доступ только для чтения.</span><span class="sxs-lookup"><span data-stu-id="05281-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="05281-111">Выделенные пользователи принадлежат обычным пользователям, а только владельцы могут изменять или удалять их, но все пользователи по-прежнему имеют доступ к ним только для чтения.</span><span class="sxs-lookup"><span data-stu-id="05281-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="05281-112">Эта документация по API охватывает операции, предназначенные только для чтения, для API репозитория.</span><span class="sxs-lookup"><span data-stu-id="05281-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="05281-113">Панель мониторинга качества звонка сохраняет отчеты и запросы как элементы в базе данных репозитория.</span><span class="sxs-lookup"><span data-stu-id="05281-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="05281-114">Элемент может иметь необязательные дочерние элементы, а панель мониторинга качества вызова упорядочивает отчеты и запросы в иерархической структуре с помощью функции вложенных элементов.</span><span class="sxs-lookup"><span data-stu-id="05281-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="05281-115">Служба номенклатуры включает следующие основные понятия:</span><span class="sxs-lookup"><span data-stu-id="05281-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="05281-116">**Item** — базовый элемент репозитория.</span><span class="sxs-lookup"><span data-stu-id="05281-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="05281-117">Каждый элемент принадлежит только одному пользователю.</span><span class="sxs-lookup"><span data-stu-id="05281-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="05281-118">**Дочерний элемент** — базовый стратегический механизм репозитория.</span><span class="sxs-lookup"><span data-stu-id="05281-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="05281-119">Элемент может иметь ноль, один или несколько подчиненных элементов.</span><span class="sxs-lookup"><span data-stu-id="05281-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="05281-120">**Родительский** элемент — список элементов, начиная с самого верхнего элемента, который является элементом по умолчанию для пользователя, что приводит к заданному элементу.</span><span class="sxs-lookup"><span data-stu-id="05281-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="05281-121">**Содержимое элемента** — содержимое, зависящее от приложения, которое хранится в элементах.</span><span class="sxs-lookup"><span data-stu-id="05281-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="05281-122">Информационная панель "качество звонка" позволяет экономить представления отчетов и запросов в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="05281-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="05281-123">Операции RESTFUL включены в таблицу ниже.</span><span class="sxs-lookup"><span data-stu-id="05281-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="05281-124">**Операция**</span><span class="sxs-lookup"><span data-stu-id="05281-124">**Operation**</span></span>|<span data-ttu-id="05281-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="05281-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="05281-126">Получение элементов</span><span class="sxs-lookup"><span data-stu-id="05281-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="05281-127">Функция Get Items возвращает все элементы в репозитории.</span><span class="sxs-lookup"><span data-stu-id="05281-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="05281-128">Получение элемента</span><span class="sxs-lookup"><span data-stu-id="05281-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="05281-129">Функция Get Item возвращает определенный элемент.</span><span class="sxs-lookup"><span data-stu-id="05281-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="05281-130">Получение вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="05281-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="05281-131">Функция "получить вложенные элементы" Возвращает вложенные элементы определенного элемента.</span><span class="sxs-lookup"><span data-stu-id="05281-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="05281-132">Получить родительских элементов</span><span class="sxs-lookup"><span data-stu-id="05281-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="05281-133">Получение предков элемента возвращает предков определенного элемента.</span><span class="sxs-lookup"><span data-stu-id="05281-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="05281-134">Обновление элемента</span><span class="sxs-lookup"><span data-stu-id="05281-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="05281-135">Обновление определенного элемента в репозитории.</span><span class="sxs-lookup"><span data-stu-id="05281-135">Update a specific item in the repository.</span></span>  <br/> |
   

