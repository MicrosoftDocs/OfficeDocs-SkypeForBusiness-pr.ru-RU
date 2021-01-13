---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.
ms.openlocfilehash: aed7720a9b74483a34704c0009958ea91a786fc1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809889"
---
# <a name="tbladminlock"></a><span data-ttu-id="c6ccc-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="c6ccc-103">tblAdminLock</span></span>
 
<span data-ttu-id="c6ccc-104">tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.</span><span class="sxs-lookup"><span data-stu-id="c6ccc-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="c6ccc-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="c6ccc-105">**Columns**</span></span>

|<span data-ttu-id="c6ccc-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c6ccc-106">**Column**</span></span>|<span data-ttu-id="c6ccc-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="c6ccc-107">**Type**</span></span>|<span data-ttu-id="c6ccc-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c6ccc-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c6ccc-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="c6ccc-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="c6ccc-110">datetime, не null</span><span class="sxs-lookup"><span data-stu-id="c6ccc-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="c6ccc-p101">Дата и время истечения срока блокировки. Владелец может периодически продлевать этот срок.</span><span class="sxs-lookup"><span data-stu-id="c6ccc-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="c6ccc-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="c6ccc-113">lockServerID</span></span>  <br/> |<span data-ttu-id="c6ccc-114">int, не null</span><span class="sxs-lookup"><span data-stu-id="c6ccc-114">int, not null</span></span>  <br/> |<span data-ttu-id="c6ccc-115">Идентификатора сервера, которому принадлежит блокировка.</span><span class="sxs-lookup"><span data-stu-id="c6ccc-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="c6ccc-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="c6ccc-116">lockActorID</span></span>  <br/> |<span data-ttu-id="c6ccc-117">int, не null</span><span class="sxs-lookup"><span data-stu-id="c6ccc-117">int, not null</span></span>  <br/> |<span data-ttu-id="c6ccc-118">Идентификатора участника, которому принадлежит блокировка.</span><span class="sxs-lookup"><span data-stu-id="c6ccc-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

