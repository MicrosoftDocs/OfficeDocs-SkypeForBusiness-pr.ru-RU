---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: Тбладминлокк содержит блокировку администратора, которая необходима для выполнения некоторых команд администратора.
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814697"
---
# <a name="tbladminlock"></a><span data-ttu-id="c4154-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="c4154-103">tblAdminLock</span></span>
 
<span data-ttu-id="c4154-104">Тбладминлокк содержит блокировку администратора, которая необходима для выполнения некоторых команд администратора.</span><span class="sxs-lookup"><span data-stu-id="c4154-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="c4154-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="c4154-105">**Columns**</span></span>

|<span data-ttu-id="c4154-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c4154-106">**Column**</span></span>|<span data-ttu-id="c4154-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="c4154-107">**Type**</span></span>|<span data-ttu-id="c4154-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c4154-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c4154-109">локкекспирестиме</span><span class="sxs-lookup"><span data-stu-id="c4154-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="c4154-110">DateTime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="c4154-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="c4154-111">Заблокируйте дату и время окончания срока действия.</span><span class="sxs-lookup"><span data-stu-id="c4154-111">Lock expiration date and time.</span></span> <span data-ttu-id="c4154-112">Владелец может периодически увеличивать это значение.</span><span class="sxs-lookup"><span data-stu-id="c4154-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="c4154-113">локксерверид</span><span class="sxs-lookup"><span data-stu-id="c4154-113">lockServerID</span></span>  <br/> |<span data-ttu-id="c4154-114">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="c4154-114">int, not null</span></span>  <br/> |<span data-ttu-id="c4154-115">Идентификатор сервера, владеющего блокировкой.</span><span class="sxs-lookup"><span data-stu-id="c4154-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="c4154-116">локкакторид</span><span class="sxs-lookup"><span data-stu-id="c4154-116">lockActorID</span></span>  <br/> |<span data-ttu-id="c4154-117">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="c4154-117">int, not null</span></span>  <br/> |<span data-ttu-id="c4154-118">Идентификатор участника, владеющего блокировкой.</span><span class="sxs-lookup"><span data-stu-id="c4154-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

