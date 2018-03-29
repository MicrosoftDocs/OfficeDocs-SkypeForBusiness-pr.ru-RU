---
title: Таблица tblLastInviteId
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
ms.openlocfilehash: 55eb9d9f5edbb3cc0e8c786b650e51cdc1e3d141
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastinviteid"></a><span data-ttu-id="c38e4-103">Таблица tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="c38e4-103">tblLastInviteId</span></span>
 
<span data-ttu-id="c38e4-104">Таблица tblLastInviteId содержит последний код приглашения, созданного (и используемый в таблице tblPrincipalInvites) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="c38e4-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="c38e4-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="c38e4-105">**Columns**</span></span>

|<span data-ttu-id="c38e4-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c38e4-106">**Column**</span></span>|<span data-ttu-id="c38e4-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="c38e4-107">**Type**</span></span>|<span data-ttu-id="c38e4-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c38e4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c38e4-109">prinID</span><span class="sxs-lookup"><span data-stu-id="c38e4-109">prinID</span></span>  <br/> |<span data-ttu-id="c38e4-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="c38e4-110">int, not null</span></span>  <br/> |<span data-ttu-id="c38e4-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="c38e4-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="c38e4-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="c38e4-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="c38e4-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="c38e4-113">int, not null</span></span>  <br/> |<span data-ttu-id="c38e4-114">Последний использованный код приглашения.</span><span class="sxs-lookup"><span data-stu-id="c38e4-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="c38e4-115">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="c38e4-115">**Keys**</span></span>

|<span data-ttu-id="c38e4-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c38e4-116">**Column**</span></span>|<span data-ttu-id="c38e4-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c38e4-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c38e4-118">prinID</span><span class="sxs-lookup"><span data-stu-id="c38e4-118">prinID</span></span>  <br/> |<span data-ttu-id="c38e4-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="c38e4-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c38e4-120">prinID</span><span class="sxs-lookup"><span data-stu-id="c38e4-120">prinID</span></span>  <br/> |<span data-ttu-id="c38e4-121">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="c38e4-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c38e4-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c38e4-122">See also</span></span>

#### 

[<span data-ttu-id="c38e4-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="c38e4-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)

