---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.
ms.openlocfilehash: ea1cff137e58ef65eda172a9c09e5dd38e66d8a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929814"
---
# <a name="tbladminlock"></a><span data-ttu-id="f1f50-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="f1f50-103">tblAdminLock</span></span>
 
<span data-ttu-id="f1f50-104">tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.</span><span class="sxs-lookup"><span data-stu-id="f1f50-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="f1f50-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="f1f50-105">**Columns**</span></span>

|<span data-ttu-id="f1f50-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f1f50-106">**Column**</span></span>|<span data-ttu-id="f1f50-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f1f50-107">**Type**</span></span>|<span data-ttu-id="f1f50-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f1f50-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f1f50-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="f1f50-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="f1f50-110">DateTime, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f1f50-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="f1f50-111">Блокировка срока действия.</span><span class="sxs-lookup"><span data-stu-id="f1f50-111">Lock expiration date and time.</span></span> <span data-ttu-id="f1f50-112">Владелец можно расширить это значение периодически.</span><span class="sxs-lookup"><span data-stu-id="f1f50-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="f1f50-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="f1f50-113">lockServerID</span></span>  <br/> |<span data-ttu-id="f1f50-114">int, не null</span><span class="sxs-lookup"><span data-stu-id="f1f50-114">int, not null</span></span>  <br/> |<span data-ttu-id="f1f50-115">Идентификатор сервера, которому принадлежит блокировка.</span><span class="sxs-lookup"><span data-stu-id="f1f50-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="f1f50-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="f1f50-116">lockActorID</span></span>  <br/> |<span data-ttu-id="f1f50-117">int, не null</span><span class="sxs-lookup"><span data-stu-id="f1f50-117">int, not null</span></span>  <br/> |<span data-ttu-id="f1f50-118">Идентификатор участника, которому принадлежит блокировка.</span><span class="sxs-lookup"><span data-stu-id="f1f50-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

