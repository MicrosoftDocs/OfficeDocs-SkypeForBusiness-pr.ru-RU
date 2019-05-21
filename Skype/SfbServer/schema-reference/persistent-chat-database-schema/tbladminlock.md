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
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: Тбладминлокк содержит блокировку администратора, которая необходима для выполнения некоторых команд администратора.
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295526"
---
# <a name="tbladminlock"></a><span data-ttu-id="ef43f-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="ef43f-103">tblAdminLock</span></span>
 
<span data-ttu-id="ef43f-104">Тбладминлокк содержит блокировку администратора, которая необходима для выполнения некоторых команд администратора.</span><span class="sxs-lookup"><span data-stu-id="ef43f-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="ef43f-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="ef43f-105">**Columns**</span></span>

|<span data-ttu-id="ef43f-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ef43f-106">**Column**</span></span>|<span data-ttu-id="ef43f-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="ef43f-107">**Type**</span></span>|<span data-ttu-id="ef43f-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ef43f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ef43f-109">Локкекспирестиме</span><span class="sxs-lookup"><span data-stu-id="ef43f-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="ef43f-110">DateTime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="ef43f-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="ef43f-111">Заблокируйте дату и время окончания срока действия.</span><span class="sxs-lookup"><span data-stu-id="ef43f-111">Lock expiration date and time.</span></span> <span data-ttu-id="ef43f-112">Владелец может периодически увеличивать это значение.</span><span class="sxs-lookup"><span data-stu-id="ef43f-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="ef43f-113">Локксерверид</span><span class="sxs-lookup"><span data-stu-id="ef43f-113">lockServerID</span></span>  <br/> |<span data-ttu-id="ef43f-114">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="ef43f-114">int, not null</span></span>  <br/> |<span data-ttu-id="ef43f-115">Идентификатор сервера, владеющего блокировкой.</span><span class="sxs-lookup"><span data-stu-id="ef43f-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="ef43f-116">Локкакторид</span><span class="sxs-lookup"><span data-stu-id="ef43f-116">lockActorID</span></span>  <br/> |<span data-ttu-id="ef43f-117">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="ef43f-117">int, not null</span></span>  <br/> |<span data-ttu-id="ef43f-118">Идентификатор участника, владеющего блокировкой.</span><span class="sxs-lookup"><span data-stu-id="ef43f-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

