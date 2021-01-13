---
title: Служба пользователей для CQD
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
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: Сводка. Сведения о службе обслуживания пользователей, которая входит в API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: d9f4b771a1bf5efeece4f8fb87195d8567f0426e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803079"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="81235-104">Служба пользователей для CQD</span><span class="sxs-lookup"><span data-stu-id="81235-104">User Service for CQD</span></span>
 
<span data-ttu-id="81235-105">**Сводка:** Узнайте о службе пользователей, которая является частью API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="81235-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="81235-106">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="81235-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="81235-107">Служба пользователей является частью API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="81235-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="81235-108">Пользовательская служба</span><span class="sxs-lookup"><span data-stu-id="81235-108">User Service</span></span>

<span data-ttu-id="81235-109">API репозитория предоставляет упрощенную модель управления пользователями, в которой подготовка пользователей (создание новых учетных записей пользователей) является автоматической и неявной.</span><span class="sxs-lookup"><span data-stu-id="81235-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="81235-110">Когда пользователь впервые запрашивает API репозитория, репозиторий создает новую запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="81235-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="81235-111">Панель мониторинга качества вызовов также автоматически создает выделенные пользователем элементы для нового пользователя.</span><span class="sxs-lookup"><span data-stu-id="81235-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="81235-112">Новые выделенные пользователем элементы являются полными клонами элементов системного пользователя.</span><span class="sxs-lookup"><span data-stu-id="81235-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="81235-113">Таким образом, пользователи начинают со своих собственных копий отчетов и запросов, которые они могут сразу же приступить к настройке.</span><span class="sxs-lookup"><span data-stu-id="81235-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="81235-114">С помощью панели мониторинга качества вызовов пользователи могут в любое время сбросить выделенные элементы.</span><span class="sxs-lookup"><span data-stu-id="81235-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="81235-115">**Специальные ИД пользователей**</span><span class="sxs-lookup"><span data-stu-id="81235-115">**Special User IDs**</span></span>
  
<span data-ttu-id="81235-116">API репозитория включает YPI REST API, которые ожидают, что для указания конкретного пользователя будет указано значение, определенное в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="81235-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="81235-117">Пример:  `https://<portal>/QoERepositoryService/repository/user/{userId}` .</span><span class="sxs-lookup"><span data-stu-id="81235-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="81235-118">Здесь {userId} следует заменить на значение, например 0, 1 и т. д.</span><span class="sxs-lookup"><span data-stu-id="81235-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="81235-119">Кроме того, API репозитория будет принимать два специальных пользовательских ИД в {userId} в URIS.</span><span class="sxs-lookup"><span data-stu-id="81235-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="81235-120">*по*  умолчанию представляет пользователя, который в настоящее время взаимодействует с API.</span><span class="sxs-lookup"><span data-stu-id="81235-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="81235-121">Это позволяет приложениям получать доступ к содержимому текущего пользователя, не отслеживая фактическое значение ИД пользователя.</span><span class="sxs-lookup"><span data-stu-id="81235-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="81235-122">Пример: `https://<portal>/QoERepositoryService/repository/user/default`.</span><span class="sxs-lookup"><span data-stu-id="81235-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="81235-123">*system*  — представляет системного пользователя.</span><span class="sxs-lookup"><span data-stu-id="81235-123">*system*  - represents the system user.</span></span> <span data-ttu-id="81235-124">Это позволяет приложениям получать доступ к содержимому системного пользователя, не зная фактического значения пользовательского ИД.</span><span class="sxs-lookup"><span data-stu-id="81235-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="81235-125">Пример: `https://<portal>/QoERepositoryService/repository/user/system`.</span><span class="sxs-lookup"><span data-stu-id="81235-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="81235-126">Если не указано иное, специальные ИД пользователей можно использовать в {userId} в URIS.</span><span class="sxs-lookup"><span data-stu-id="81235-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="81235-127">Операции REST включены в следующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="81235-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="81235-128">**Операция**</span><span class="sxs-lookup"><span data-stu-id="81235-128">**Operation**</span></span>|<span data-ttu-id="81235-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="81235-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="81235-130">Получение пользователей</span><span class="sxs-lookup"><span data-stu-id="81235-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="81235-131">Возвращает список пользователей в репозитории.</span><span class="sxs-lookup"><span data-stu-id="81235-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="81235-132">Получение пользователя</span><span class="sxs-lookup"><span data-stu-id="81235-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="81235-133">Возвращает запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="81235-133">Returns a user record.</span></span>  <br/> |
   

