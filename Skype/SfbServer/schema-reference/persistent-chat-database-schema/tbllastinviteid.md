---
title: tblLastInviteId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: Таблица tblLastInviteId содержит последний код приглашения, созданного (и используемый в таблице tblPrincipalInvites) для каждого пользователя.
ms.openlocfilehash: 977911150992b2e90b7dc344af0550a25ad77221
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212560"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="4059b-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="4059b-103">tblLastInviteId</span></span>
 
<span data-ttu-id="4059b-104">Таблица tblLastInviteId содержит последний код приглашения, созданного (и используемый в таблице tblPrincipalInvites) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="4059b-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="4059b-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="4059b-105">**Columns**</span></span>

|<span data-ttu-id="4059b-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4059b-106">**Column**</span></span>|<span data-ttu-id="4059b-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="4059b-107">**Type**</span></span>|<span data-ttu-id="4059b-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4059b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4059b-109">prinID</span><span class="sxs-lookup"><span data-stu-id="4059b-109">prinID</span></span>  <br/> |<span data-ttu-id="4059b-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="4059b-110">int, not null</span></span>  <br/> |<span data-ttu-id="4059b-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="4059b-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="4059b-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="4059b-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="4059b-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="4059b-113">int, not null</span></span>  <br/> |<span data-ttu-id="4059b-114">Последний использованный код приглашения.</span><span class="sxs-lookup"><span data-stu-id="4059b-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="4059b-115">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="4059b-115">**Keys**</span></span>

|<span data-ttu-id="4059b-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4059b-116">**Column**</span></span>|<span data-ttu-id="4059b-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4059b-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4059b-118">prinID</span><span class="sxs-lookup"><span data-stu-id="4059b-118">prinID</span></span>  <br/> |<span data-ttu-id="4059b-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="4059b-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="4059b-120">prinID</span><span class="sxs-lookup"><span data-stu-id="4059b-120">prinID</span></span>  <br/> |<span data-ttu-id="4059b-121">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="4059b-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4059b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4059b-122">See also</span></span>

[<span data-ttu-id="4059b-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="4059b-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
