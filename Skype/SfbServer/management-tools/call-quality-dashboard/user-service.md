---
title: Служба пользователей для CQD
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: ': Сводка сведения о службе пользователя, которая является частью API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.'
ms.openlocfilehash: 4ee4594e86b14655c94472b516b9e04da674e3f0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217644"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="2f453-104">Служба пользователей для CQD</span><span class="sxs-lookup"><span data-stu-id="2f453-104">User Service for CQD</span></span>
 
<span data-ttu-id="2f453-105">**Сводка:** Сведения о службе пользователя, которая является частью API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="2f453-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="2f453-106">Панель мониторинга качества звонков — это средство для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="2f453-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="2f453-107">Служба пользователей является частью API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="2f453-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="2f453-108">Пользовательская служба</span><span class="sxs-lookup"><span data-stu-id="2f453-108">User Service</span></span>

<span data-ttu-id="2f453-109">API репозитория предоставляет упрощенный пользовательская модель управления, где подготовки (создание новых учетных записей пользователей) выполняется автоматически и неявные.</span><span class="sxs-lookup"><span data-stu-id="2f453-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="2f453-110">Когда пользователь для выполнения запроса с API репозитория в первый раз, репозиторий создает новую запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="2f453-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="2f453-111">Вызов, панель мониторинга качества автоматически создает пользователя выделенных элементов для нового пользователя.</span><span class="sxs-lookup"><span data-stu-id="2f453-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="2f453-112">Новые элементы выделенных пользователей, завершения копирует элементы системы пользователя.</span><span class="sxs-lookup"><span data-stu-id="2f453-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="2f453-113">Таким образом, пользователи начать с их копиями собственные отчеты и запросы, что они могут немедленно начать настройку.</span><span class="sxs-lookup"><span data-stu-id="2f453-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2f453-114">С помощью панели мониторинга качества звонков, пользователи могут сбросить свои выделенные элементы в любое время.</span><span class="sxs-lookup"><span data-stu-id="2f453-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="2f453-115">**Идентификаторы специального пользователя**</span><span class="sxs-lookup"><span data-stu-id="2f453-115">**Special User IDs**</span></span>
  
<span data-ttu-id="2f453-116">API репозитория включает в себя коды URI API REST, требующей целое значение для указания конкретного пользователя.</span><span class="sxs-lookup"><span data-stu-id="2f453-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="2f453-117">Пример: `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span><span class="sxs-lookup"><span data-stu-id="2f453-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="2f453-118">Здесь {userId} следует заменить целое значение 0, 1, и т.д.</span><span class="sxs-lookup"><span data-stu-id="2f453-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="2f453-119">Кроме того API репозитория будет принимать два специальных пользовательских идентификаторы в {userId} в URI.</span><span class="sxs-lookup"><span data-stu-id="2f453-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="2f453-120">*по умолчанию* — представляет пользователя, который в данный момент взаимодействует с использованием интерфейса API.</span><span class="sxs-lookup"><span data-stu-id="2f453-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="2f453-121">Это позволяет приложениям для доступа к контенту текущего пользователя не позволяет отслеживать их значение идентификатора пользователя.</span><span class="sxs-lookup"><span data-stu-id="2f453-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="2f453-122">Пример: ` https://<portal>/QoERepositoryService/repository/user/default`.</span><span class="sxs-lookup"><span data-stu-id="2f453-122">Example: ` https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="2f453-123">*Система* — представляет пользователя в системе.</span><span class="sxs-lookup"><span data-stu-id="2f453-123">*system*  - represents the system user.</span></span> <span data-ttu-id="2f453-124">Это позволяет приложениям для доступа к контенту пользователя системы неизвестны значение идентификатора пользователя.</span><span class="sxs-lookup"><span data-stu-id="2f453-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="2f453-125">Пример: `https://<portal>/QoERepositoryService/repository/user/system`.</span><span class="sxs-lookup"><span data-stu-id="2f453-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="2f453-126">Если не указано иное, специальные идентификаторы пользователей можно использовать в {userId} в URI.</span><span class="sxs-lookup"><span data-stu-id="2f453-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="2f453-127">В следующей таблице включены операции REST.</span><span class="sxs-lookup"><span data-stu-id="2f453-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="2f453-128">**Операция**</span><span class="sxs-lookup"><span data-stu-id="2f453-128">**Operation**</span></span>|<span data-ttu-id="2f453-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2f453-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2f453-130">Получение пользователей</span><span class="sxs-lookup"><span data-stu-id="2f453-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="2f453-131">Возвращает список пользователей в репозитории.</span><span class="sxs-lookup"><span data-stu-id="2f453-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="2f453-132">Получение пользователя</span><span class="sxs-lookup"><span data-stu-id="2f453-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="2f453-133">Возвращает запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="2f453-133">Returns a user record.</span></span>  <br/> |
   

