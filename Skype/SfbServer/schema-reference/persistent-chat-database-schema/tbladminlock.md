---
title: tblAdminLock
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.
ms.openlocfilehash: bf7537b7d1081bd415ff2e8fe3615864c71f593a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212665"
---
# <a name="tbladminlock"></a><span data-ttu-id="bbf1e-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="bbf1e-103">tblAdminLock</span></span>
 
<span data-ttu-id="bbf1e-104">tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="bbf1e-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-105">**Columns**</span></span>

|<span data-ttu-id="bbf1e-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-106">**Column**</span></span>|<span data-ttu-id="bbf1e-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-107">**Type**</span></span>|<span data-ttu-id="bbf1e-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bbf1e-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="bbf1e-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="bbf1e-110">DateTime, не может быть null</span><span class="sxs-lookup"><span data-stu-id="bbf1e-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="bbf1e-111">Блокировка срока действия.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-111">Lock expiration date and time.</span></span> <span data-ttu-id="bbf1e-112">Владелец можно расширить это значение периодически.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="bbf1e-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="bbf1e-113">lockServerID</span></span>  <br/> |<span data-ttu-id="bbf1e-114">int, не null</span><span class="sxs-lookup"><span data-stu-id="bbf1e-114">int, not null</span></span>  <br/> |<span data-ttu-id="bbf1e-115">Идентификатор сервера, которому принадлежит блокировка.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="bbf1e-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="bbf1e-116">lockActorID</span></span>  <br/> |<span data-ttu-id="bbf1e-117">int, не null</span><span class="sxs-lookup"><span data-stu-id="bbf1e-117">int, not null</span></span>  <br/> |<span data-ttu-id="bbf1e-118">Идентификатор участника, которому принадлежит блокировка.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

