---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: Таблица tblLastInviteId содержит последний код приглашения, созданного (и используемого в таблице tblPrincipalInvites) для каждого пользователя.
ms.openlocfilehash: 9d5ec67a4f5c3db8558c58834582d489fde00ab6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815969"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="90538-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="90538-103">tblLastInviteId</span></span>
 
<span data-ttu-id="90538-104">Таблица tblLastInviteId содержит последний код приглашения, созданного (и используемого в таблице tblPrincipalInvites) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="90538-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="90538-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="90538-105">**Columns**</span></span>

|<span data-ttu-id="90538-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="90538-106">**Column**</span></span>|<span data-ttu-id="90538-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="90538-107">**Type**</span></span>|<span data-ttu-id="90538-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="90538-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="90538-109">prinID</span><span class="sxs-lookup"><span data-stu-id="90538-109">prinID</span></span>  <br/> |<span data-ttu-id="90538-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="90538-110">int, not null</span></span>  <br/> |<span data-ttu-id="90538-111">Код участника.</span><span class="sxs-lookup"><span data-stu-id="90538-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="90538-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="90538-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="90538-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="90538-113">int, not null</span></span>  <br/> |<span data-ttu-id="90538-114">Последний использованный код приглашения.</span><span class="sxs-lookup"><span data-stu-id="90538-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="90538-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="90538-115">**Keys**</span></span>

|<span data-ttu-id="90538-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="90538-116">**Column**</span></span>|<span data-ttu-id="90538-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="90538-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="90538-118">prinID</span><span class="sxs-lookup"><span data-stu-id="90538-118">prinID</span></span>  <br/> |<span data-ttu-id="90538-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="90538-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="90538-120">prinID</span><span class="sxs-lookup"><span data-stu-id="90538-120">prinID</span></span>  <br/> |<span data-ttu-id="90538-121">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="90538-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="90538-122">См. также</span><span class="sxs-lookup"><span data-stu-id="90538-122">See also</span></span>

[<span data-ttu-id="90538-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="90538-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
