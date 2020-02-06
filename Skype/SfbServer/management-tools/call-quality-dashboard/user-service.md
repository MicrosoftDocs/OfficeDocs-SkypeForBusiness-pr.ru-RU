---
title: Пользовательская служба для CQD
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
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Сводка: сведения о службе пользователя, которая является частью API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 439df99c1c9d66547e681fdea90b33c6295344db
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816658"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="91ef7-104">Пользовательская служба для CQD</span><span class="sxs-lookup"><span data-stu-id="91ef7-104">User Service for CQD</span></span>
 
<span data-ttu-id="91ef7-105">**Сводка:** Узнайте о службе пользователей, которая входит в состав API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="91ef7-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="91ef7-106">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="91ef7-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="91ef7-107">Служба User входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="91ef7-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="91ef7-108">Пользовательская служба</span><span class="sxs-lookup"><span data-stu-id="91ef7-108">User Service</span></span>

<span data-ttu-id="91ef7-109">API репозитория предоставляет упрощенную модель управления пользователями, в которой подготовка пользователей (создание новых учетных записей пользователей) выполняется автоматически и неявным образом.</span><span class="sxs-lookup"><span data-stu-id="91ef7-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="91ef7-110">Когда пользователь впервые создает запрос для API репозитория, в репозитории создается новая запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="91ef7-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="91ef7-111">Кроме того, панель мониторинга качества звонка автоматически создает выделенные пользователем элементы для нового пользователя.</span><span class="sxs-lookup"><span data-stu-id="91ef7-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="91ef7-112">Новые пользовательские элементы — это полные клоны элементов системного пользователя.</span><span class="sxs-lookup"><span data-stu-id="91ef7-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="91ef7-113">Таким образом, пользователи запускаются с помощью собственных копий отчетов и запросов, которые можно сразу же приступить к настройке.</span><span class="sxs-lookup"><span data-stu-id="91ef7-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="91ef7-114">С помощью панели мониторинга качества звонков пользователи могут в любое время сбросить их выделенные элементы.</span><span class="sxs-lookup"><span data-stu-id="91ef7-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="91ef7-115">**Особые идентификаторы пользователей**</span><span class="sxs-lookup"><span data-stu-id="91ef7-115">**Special User IDs**</span></span>
  
<span data-ttu-id="91ef7-116">API репозитория содержат API-интерфейсы оставшейся части, которые ожидают целочисленное значение для указания определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="91ef7-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="91ef7-117">Пример: `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span><span class="sxs-lookup"><span data-stu-id="91ef7-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="91ef7-118">Здесь {userId} следует заменить целым числом, таким как 0, 1 и т. д.</span><span class="sxs-lookup"><span data-stu-id="91ef7-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="91ef7-119">Кроме того, API репозитория будут допускать два специальных идентификатора пользователя в {userId} в URI.</span><span class="sxs-lookup"><span data-stu-id="91ef7-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="91ef7-120">*по умолчанию* — пользователь, который в данный момент взаимодействует с API.</span><span class="sxs-lookup"><span data-stu-id="91ef7-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="91ef7-121">Это позволяет приложениям получать доступ к содержимому текущего пользователя без учета значения фактического идентификатора пользователя.</span><span class="sxs-lookup"><span data-stu-id="91ef7-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="91ef7-122">Пример: `https://<portal>/QoERepositoryService/repository/user/default`.</span><span class="sxs-lookup"><span data-stu-id="91ef7-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="91ef7-123">*система* — представляет пользователя системы.</span><span class="sxs-lookup"><span data-stu-id="91ef7-123">*system*  - represents the system user.</span></span> <span data-ttu-id="91ef7-124">Это позволяет приложениям получать доступ к содержимому системного пользователя, не зная фактического идентификатора пользователя.</span><span class="sxs-lookup"><span data-stu-id="91ef7-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="91ef7-125">Пример: `https://<portal>/QoERepositoryService/repository/user/system`.</span><span class="sxs-lookup"><span data-stu-id="91ef7-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="91ef7-126">Если не указано иное, коды специальных пользователей можно использовать в идентификаторах URI в {userId}.</span><span class="sxs-lookup"><span data-stu-id="91ef7-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="91ef7-127">Операции RESTFUL включены в таблицу ниже.</span><span class="sxs-lookup"><span data-stu-id="91ef7-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="91ef7-128">**Операция**</span><span class="sxs-lookup"><span data-stu-id="91ef7-128">**Operation**</span></span>|<span data-ttu-id="91ef7-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="91ef7-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="91ef7-130">Получение пользователей</span><span class="sxs-lookup"><span data-stu-id="91ef7-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="91ef7-131">Возвращает список пользователей в репозитории.</span><span class="sxs-lookup"><span data-stu-id="91ef7-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="91ef7-132">Получение пользователя</span><span class="sxs-lookup"><span data-stu-id="91ef7-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="91ef7-133">Возвращает запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="91ef7-133">Returns a user record.</span></span>  <br/> |
   

