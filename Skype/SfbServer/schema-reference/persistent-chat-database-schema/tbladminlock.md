---
title: tblAdminLock
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
ms.openlocfilehash: 919ead84ed9baab859e1e85eb2f30f5ff6902531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tbladminlock"></a><span data-ttu-id="714ff-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="714ff-103">tblAdminLock</span></span>
 
<span data-ttu-id="714ff-104">tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.</span><span class="sxs-lookup"><span data-stu-id="714ff-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="714ff-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="714ff-105">**Columns**</span></span>

|<span data-ttu-id="714ff-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="714ff-106">**Column**</span></span>|<span data-ttu-id="714ff-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="714ff-107">**Type**</span></span>|<span data-ttu-id="714ff-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="714ff-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="714ff-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="714ff-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="714ff-110">DateTime, не может быть null</span><span class="sxs-lookup"><span data-stu-id="714ff-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="714ff-111">Блокировка срока действия.</span><span class="sxs-lookup"><span data-stu-id="714ff-111">Lock expiration date and time.</span></span> <span data-ttu-id="714ff-112">Владелец можно расширить это значение периодически.</span><span class="sxs-lookup"><span data-stu-id="714ff-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="714ff-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="714ff-113">lockServerID</span></span>  <br/> |<span data-ttu-id="714ff-114">int, не null</span><span class="sxs-lookup"><span data-stu-id="714ff-114">int, not null</span></span>  <br/> |<span data-ttu-id="714ff-115">Идентификатор сервера, которому принадлежит блокировка.</span><span class="sxs-lookup"><span data-stu-id="714ff-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="714ff-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="714ff-116">lockActorID</span></span>  <br/> |<span data-ttu-id="714ff-117">int, не null</span><span class="sxs-lookup"><span data-stu-id="714ff-117">int, not null</span></span>  <br/> |<span data-ttu-id="714ff-118">Идентификатор участника, которому принадлежит блокировка.</span><span class="sxs-lookup"><span data-stu-id="714ff-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

