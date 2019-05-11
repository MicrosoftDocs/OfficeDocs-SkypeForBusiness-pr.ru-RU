---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: Таблица tblLastInviteId содержит последний код приглашения, созданного (и используемый в таблице tblPrincipalInvites) для каждого пользователя.
ms.openlocfilehash: f57ca67a91b71b9245644a53eb3e5c5771ca6fb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929905"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="c7921-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="c7921-103">tblLastInviteId</span></span>
 
<span data-ttu-id="c7921-104">Таблица tblLastInviteId содержит последний код приглашения, созданного (и используемый в таблице tblPrincipalInvites) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="c7921-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="c7921-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="c7921-105">**Columns**</span></span>

|<span data-ttu-id="c7921-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c7921-106">**Column**</span></span>|<span data-ttu-id="c7921-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="c7921-107">**Type**</span></span>|<span data-ttu-id="c7921-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c7921-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c7921-109">prinID</span><span class="sxs-lookup"><span data-stu-id="c7921-109">prinID</span></span>  <br/> |<span data-ttu-id="c7921-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="c7921-110">int, not null</span></span>  <br/> |<span data-ttu-id="c7921-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="c7921-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="c7921-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="c7921-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="c7921-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="c7921-113">int, not null</span></span>  <br/> |<span data-ttu-id="c7921-114">Последний использованный код приглашения.</span><span class="sxs-lookup"><span data-stu-id="c7921-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="c7921-115">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="c7921-115">**Keys**</span></span>

|<span data-ttu-id="c7921-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c7921-116">**Column**</span></span>|<span data-ttu-id="c7921-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c7921-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c7921-118">prinID</span><span class="sxs-lookup"><span data-stu-id="c7921-118">prinID</span></span>  <br/> |<span data-ttu-id="c7921-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="c7921-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c7921-120">prinID</span><span class="sxs-lookup"><span data-stu-id="c7921-120">prinID</span></span>  <br/> |<span data-ttu-id="c7921-121">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="c7921-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c7921-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c7921-122">See also</span></span>

[<span data-ttu-id="c7921-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="c7921-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
